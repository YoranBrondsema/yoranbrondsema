---
title: "Deep dive into the past performance of my portfolio"
date: 2018-12-27T09:41:20+01:00
slug: deep-dive-into-the-past-performance-of-my-portfolio
tags: ["Investing"]
toc: true
---

When I set up my portfolio about a year ago, I based its composition on the
recommendations laid out in Richard Ferri's excellent book [All About Asset Allocation](https://www.goodreads.com/book/show/9316522-all-about-asset-allocation).
Once I knew what percentages I wanted to assign to bonds, equities from
developed markets, emerging markets, etc... it was a matter of finding the
matching funds on [justETF](https://www.justetf.com).

However, I never bothered to actually test the past performance of the portfolio
before investing my money. Although unlikely, maybe Richard Ferri is just saying
a bunch of bollocks and his recommendations aren't actually any good? It's time
to find this out myself and answer the important question: **how has my
portfolio performed in the past?**

Read on to find out the answer.

## Composition of my portfolio

For reasons I described in [an earlier post]({{< ref "post/an-intro-to-passive-investing.md" >}}), my portfolio is composed of solely
index funds:

| ETF                                                                                                 | Allocation | Index
|-----------------------------------------------------------------------------------------------------|------------|----
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | 48%        | MSCI World
| [iShares MSCI World Small Cap](https://www.justetf.com/en/etf-profile.html?isin=IE00BF4RFH31)       | 14%        | MSCI World Small Cap
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | 10%        | MSCI Emerging Markets
| [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | 9%         | FTSE EPRA/NAREIT
| [Xtrackers Global Sovereign](https://www.justetf.com/en/etf-profile.html?isin=%20LU0908508731)      | 19%        | FTSE World Government Bond Index

## Getting the historical data
The first step is to get the historical values of the funds that make up the
portfolio. For instance, we can go to Yahoo Finance and the historical data for
[iShares Core MSCI World](https://finance.yahoo.com/quote/IWDA.AS/history?period1=1255384800&period2=1546124400&interval=1mo&filter=history&frequency=1mo).
However, the issue is that the funds are usually much younger than the indexes
that they track. According to the
[factsheet](https://www.justetf.com/servlet/download?isin=IE00B4L5Y983&documentType=MR&country=DE&lang=en),
this particular fund was created in 2009. However, the MSCI World index exists
since 1986!

Most indexes in the portfolio are actually pretty old:

* MSCI World: 1986
* MSCI World Small Cap: 2001
* MSCI Emerging Markets: 2001
* FTSE EPRA/NAREIT: 2005
* FTSE World Government Bond Index: 1986

To increase the validity of our simulation, we want to go back in time as far as
possible. So our assignment is to find the historical values for the indexes in
the portfolio, rather than the funds themselves.

### MSCI
MSCI Inc. is the company behind the MSCI indexes. It wasn't to hard to find the
historical data for these indexes as their website has a page dedicated to
[historical data](https://www.msci.com/end-of-day-data-search).
You do have to launch a very outdated Flash application but you can then
download an Excel spreadsheet with the wanted data[^2].

An interesting observation is that the historical data goes back further than
the inception date of the index. For instance, the data for MSCI World starts in
1970 whereas the index was only created in 1986. To do this, they apply
back-testing, meaning that they calculate how the index might have performed had
it existed.

### FTSE EPRA/NAREIT
This data was a bit harder to find. After a long search, I found a 66MB Zip file
on the EPRA website that contains the data for all their indexes[^1]. I just had
to extract the one I needed.

The data for this index starts in 1990. It's therefore not as old as some of the
MSCI indexes but this is still far enough in time for our purposes.

### FTSE World Government Bond Index
Finding the data for the bond index was the most frustrating. It seems to only
be made available by [The Yield Book](https://yieldbook.com) but it's behind a
paywall. Apparently, selling the historical data of their indexes is part of
their business model.

Instead, I opted to find the historical data for a fund that tracks the index.
However, also here I had no luck in finding a fund that was old enough.

As a last resort, I decided to use another bond index as a proxy for WGBI. After
all, it's important that a bond index is included in the analysis due to its
stabilizing effect on the entire portfolio. I settled on the JP Morgan
Government Bond Index, mainly because it was the closest bond index that I could
find that had sufficient historical data available for free.

It's a US-only bond whereas WGBI is global. Also, the correlation between the
two indexes for the past 5 years is 0.90[^3]. This is not ideal but it will have
to do.

## Preparing the data
Now that have the raw data, we have to make it ready for analysis. First, we
have to find the common time period between all the datasets. It turns out that
we all the data necessary to perform the simulation **from February 1993 to
December 2015**. That's almost 23 years in total, which gives us sufficient
validation for how our portfolio behaves during both bull
and bear markets.

Secondly, we need to convert all five datasets into the same CSV format[^4].

## The simulation
We are now ready to start the simulation: **if we had invested €1,000 in February
1993, how much would we have had in December 2015?**

Instead of running the simulation in a spreadsheet, I implemented it as a small
website called [Yoran's Portfolio Simulator](https://portfolio-simulator.netlify.com/). Developing web
applications is my day job so it was easier for me to do it this way. Also, a
website is more shareable than a spreadsheet and easier to make it visually more
appealing (which it isn't yet). The entire source code of the application is
available on [GitHub](https://github.com/YoranBrondsema/portfolio-simulator).

### No rebalancing
First, I ran the simulation without any rebalancing strategy. This resulted in a
total of €3,375 or a **5.47% average annual return rate (AARR)**.

### Yearly rebalancing
In reality, we would use a rebalancing strategy.  Therefore, I did a second run
where the portfolio is rebalanced every year. As expected, this improved the
performance and we ended up with €3,881 or an **AARR of 6.12%**.

{{< figure src="/images/portfolio-simulation-yearly-rebalance.png" caption="Performance of the portfolio when rebalancing yearly." >}}

## Limitations of the analysis
We made several simplifications in our model that have an impact on the accuracy
of the outcome:

1. Due to a lack of availability of data, I had to use a **proxy index** for the
   FTSE World Government Bond Index. We calculated that for the last 5 years,
   the correlation between the two indexes was 0.90. They are therefore fairly
   closely connected but having the data for the actual index would make the
   simulations more accurate.
2. I did not include **dividend payments**. Each of the funds in the portfolio
   pays out dividends, which are reinvested. Including these gains in the
   analysis would result in a positive impact on the return.
3. I did not include losses due to **taxes and trading fees**. These are highly
   time- and country-dependent and would make the analysis very complicated.
   However, they would negatively impact the return if included.
4. The model assumes that it is possible to buy **fractional parts of an
   index**. In reality, ETFs are traded like shares and only purchaseable as
   whole units, i.e. you can't buy 0.4 of an ETF. However, this effect becomes
   negligible when investing sufficiently large amounts so it doesn't really
   affect the validity of the result.

## Conclusion

| Rebalancing strategy | Average annual return rate (AARR)
|----------------------|---------------------------------
| No rebalancing       | 5.47%
| Yearly rebalancing   | 6.12%

Past performance is not a guarantee for future performance. However, it can give
a good indication. The most important result of our simulation is that our
portfolio has given an average return of **around 6%** during a period of 23
years. It's fair to assume that the performance for the following years will be
similar.

## Topics for future articles
After having done this research, there are two topics that I want to explore
further in a next post:

* **impact of rebalancing strategies**. We already saw here that rebalancing has
  a big impact on the total return of a portfolio. Are any strategies better
  than other? Is it better to rebalance monthly, quarterly, yearly or even
  two-yearly?
* **optimal weightings for the portfolio**. What would be the optimal allocation
  if we want to maximize returns? What if we instead wish to maximize the Sharpe
  ratio or Calmar ratio? What would be the effect of reducing or increasing the
  allocation of bonds in the portfolio?

## My questions to you
I am still keeping my eyes out for the data that I couldn't find. Therefore, if
you have access to:

1. the historical data for the FTSE World Government Bond Index,
2. the historical data for the FTSE EPRA/NAREIT index for 2016 and onwards,

please let me know! You can contact me at [@YoranBrondsema](https://twitter.com/YoranBrondsema) or at <yoran.brondsema@gmail.com>.

[^1]: http://www.epra.com/indexes/historical-zips
[^2]: Links for the data: [MSCI World](https://app2.msci.com/products/indexes/performance/regional_chart.html?asOf=Dec%2026,%202018&size=36&scope=R&style=C&currency=15&priceLevel=0&indexId=106#), [MSCI World Small Cap](https://app2.msci.com/products/indexes/performance/regional_chart.html?asOf=Dec%2026,%202018&size=39&scope=R&style=C&currency=15&priceLevel=0&indexId=3335), [MSCI Emerging Markets](https://app2.msci.com/products/indexes/performance/regional_chart.html?asOf=Dec%2026,%202018&size=36&scope=R&style=C&currency=15&priceLevel=0&indexId=13). 
[^3]: <https://github.com/YoranBrondsema/portfolio-simulator/blob/3cf88c09bba432e9f2cd46c5cf30d03b9668441e/documents/Correlation%20between%20FTSE%20WGBI%20and%20JP%20Morgan%20GBI.ods>
[^4]: <https://github.com/YoranBrondsema/portfolio-simulator/tree/3cf88c09bba432e9f2cd46c5cf30d03b9668441e/public/data>
