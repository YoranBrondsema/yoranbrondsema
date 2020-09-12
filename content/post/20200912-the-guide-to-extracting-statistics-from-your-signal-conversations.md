---
title: "The guide to extracting statistics from your Signal conversations"
date: 2020-09-12T10:23:58+02:00
slug: the-guide-to-extracting-statistics-from-your-signal-conversations
tags: ["Computer things"]
toc: true
---

To be able to visit each other during these strange Covid-19 times, my
girlfriend and I have to "prove" our relationship to my country of residence.
One of the pieces of evidence is the messages that we've been sending each
other over the years that we've been together. [Signal](https://signal.org/) is
our main medium of communication for messaging, calls, and video, and we send
each other tens of messages daily. So to add weight to our application, we
wanted to add statistics around the number of messages that we've sent each
other throughout our relationship.

This guide is the result of my explorations into how to extract statistics from
our Signal conversations. Beware, it is quite technical.

## About Signal
Signal differentiates itself from other messaging apps like WhatsApp and
Messenger by its focus on privacy. It was created by Moxie Marlinspike, who is
a highly regarded computer security expert and cryptographer. Its list of
testimonials are among the most powerful I've ever seen: Edward Snowden, Laura
Poitras, Bruce Schneier, all recommend Signal. It's open-source and the company
behind it is a non-profit.

Because of its focus on privacy, Signal does not store any messages on its
servers. So the only way to access your messages for analysis is through your
local copy in the Android, iOS, or desktop apps that Signal provides. Each
requires a different method to analyze the messages and extract statistics.

## From the Android app
### 1. Create a backup
The Signal Android app can create an encrypted backup of the messages stored on
your device. I refer to the [instructions on the Signal website](https://support.signal.org/hc/en-us/articles/360007059752-Backup-and-Restore-Messages#android_restore)
on how to do so.

### 2. Transfer the backup to your computer
To analyze the messages, we need to send the backup from your phone to your
computer. I simply uploaded the encrypted backup to Google Drive which I then
downloaded to my computer. But you can use any other means of transferring
files between your phone and computer.

### 3. Decrypt the backup
We can't access any messages in the backup until we decrypt it. Fortunately,
someone built a tool for that called
[signal-back](https://github.com/xeals/signal-back). Simply [download a binary](https://github.com/xeals/signal-back/releases) and run:

```sh
$ signal-back format -f CSV -o backup-android.csv <signal-XXX.backup>
```

It will ask for the 36-digit passcode that Signal gave you when creating the
backup in step 1. After running this command, `backup-android.csv` will contain
a history of your messages in CSV format.

### 4. Extract statistics from the CSV
Now that we have our messages in CSV, we can analyze it. I wrote a small Ruby
script that parses the file and extracts a count of messages in a particular
conversation, grouped by year.

```ruby
# analyze-signal-android.rb

require 'csv'

# Link to the backup CSV.
filepath = ARGV[0]
# Thread ID the conversation you want to get stats from.
thread_id = ARGV[1]

messages = []
CSV.foreach(filepath, headers: true) do |row|
  if row['THREAD_ID'] == thread_id
    messages << {
      date_sent: Time.at(row['DATE_SENT'].to_i / 1000)
    }
  end
end

messages
  .group_by { |message| message[:date_sent].year }
  .each { |year, msgs| puts "#{year}: #{msgs.count} messages" }

puts "Total number of messages: #{messages.count}"
puts "Earliest date: #{messages[0][:date_sent].strftime('%B %e, %Y')}"
```

To run it:

```bash
$ ruby analyze-signal-android.rb backup-android.csv 1
2018: 12676 messages
2019: 22225 messages
2020: 13381 messages
Total number of messages: 48282
Earliest date: May 2, 2018
```

The first argument to the script is the path to the backup CSV. The second is
the Signal thread ID for which you want to get the statistics. For instance,
the conversation with my girlfriend is assigned ID `1`. I suggest you look into
the CSV to find out the ID of the thread that you're interested in.

## From the desktop app
The Signal desktop application is built on Electron and it stores the messages
in an SQLite database.

### 1. Get the SQLite database
Depending on whether you're on Linux, Mac, or Windows, the SQLite database is
located in a different folder:

* Linux: `~/.config/Signal/sql/db.sqlite`
* Mac: `~/Library/Application Support/Signal/sql/db.sqlite`
* Windows: `C:\Users\<YourName>\AppData\Roaming\Signal\sql\db.sqlite` (not tested)

### 2. Decrypt and convert the SQLite database to CSV
The Signal SQLite database is encrypted using SQLCipher. So we need to decrypt
it and convert it to CSV before we can analyze it.

```bash
# sqlite-to-csv.sh

# From https://unix.stackexchange.com/a/505009/413853
sigBase="${HOME}/.config/Signal/";
key=$( /usr/bin/jq -r '."key"' ${sigBase}config.json );
db="${HOME}/.config/Signal/sql/db.sqlite";
clearTextMsgs="${sigBase}backup-desktop.csv";

/usr/bin/sqlcipher -list -noheader "$db" "PRAGMA key = \"x'"$key"'\";select json from messages;" > "$clearTextMsgs";
```

To run this script:

```bash
$ bash sqlite-to-csv.sh
```

You'll need to install a sufficient recent version of
[sqlcipher](https://github.com/sqlcipher/sqlcipher). I first ran it with
sqlcipher 3.15.2 but I got an error `Error: file is encrypted or is not a
database` when running the script. It worked when using sqlcipher 3.31.0 that I
built from source.

The file `backup-desktop.csv` now contains a CSV of the messages stored in the
Signal desktop application.

### 3. Extract statistics from the CSV
The format of the CSV from the desktop application is different than the one
generated from the Android app. Another Ruby script does the job to extract the
statistics:

```ruby
require 'json'

# Link to the backup CSV.
filepath = ARGV[0]
# Number of the person you want to analyze your conversations of.
number = ARGV[1]

messages = []
File.foreach(filepath) do |line|
  begin
    json = JSON.parse(line)

    if json["delivered_to"] == [number] || json["source"] == number
      messages << {
        date_sent: Time.at(json['sent_at'].to_i / 1000)
      }
    end
  rescue
  end
end

messages
  .group_by { |message| message[:date_sent].year }
  .each { |year, msgs| puts "#{year}: #{msgs.count} messages" }

puts "Total number of messages: #{messages.count}"
puts "Earliest date: #{messages[0][:date_sent].strftime('%B %e, %Y')}"
```

To run it:

```bash
$ ruby analyze-signal-desktop.rb signal-desktop.csv <phone-number>
2018: 8318 messages
2019: 22258 messages
2020: 13381 messages
Total number of messages: 43957
Earliest date: July 28, 2018
```

The first argument is the decrypted SQLite database in CSV and the second
argument is the phone number of the person with whom you want to analyze your
conversations with.

## From iOS
I haven't looked into this because I don't use an iPhone.

## Source code
The source code snippets in this article are also on
[GitHub](https://github.com/YoranBrondsema/signal-stats).
