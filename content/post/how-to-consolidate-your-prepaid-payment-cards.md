---
title: "How to consolidate your prepaid payment cards"
date: 2019-04-29T21:17:59-05:00
slug: how-to-consolidate-your-prepaid-payment-cards
tags: ["Life hack"]
description: "Have you ever found yourself stuck with various prepaid credit cards? I found a solution to get the value from all those cards onto my bank account."
---

Have you ever found yourself stuck with various $10 prepaid credit cards, not
knowing how to spend them? You can't combine cards for a single payment and you
end up with small change on each card. I found a solution to get the value from
all those cards onto my bank account.

During my search on the web, I didn't find a resource describing a solution. I
hope to fill this gap with this article!

## Writing reviews for $10
Over the past few months, I've written a couple of reviews on
websites that award gift cards, such as [Capterra](https://www.capterra.com/)
and [G2](https://www.g2.com/). They're for services that we use at
[Sutori](https://www.sutori.com) and [Curvo](https://curvo.eu), so each review
only takes me a couple of minutes to write. In exchange, they award you $10 in
the form of an Amazon gift card or a prepaid Visa card.

I've always chosen the prepaid Visa card because I don't want to be forced to
buy only on Amazon. I soon ran into two problems though:

* **Online merchants can't split a payment across multiple cards.** This means
  that I can't combine more than one card to make purchases above $10.
* **I ended up with small change on each card.** If I buy an item for $9.50, I'm
  then stuck with $0.50 left on that card. Good luck finding an item
  that costs less than $0.50, including shipping.

I was hopeful when I read that it was possible to [consolidate credit cards with Google Wallet](https://lifehacker.com/consolidate-your-credit-card-gift-cards-with-google-wa-1603229714).
Unfortunately, that service [was discontinued in 2015](https://www.reddit.com/r/beermoney/comments/33e5qd/combine_visa_cards_to_create_a_larger_single/).

So I had to find another solution to **spend the money on the prepaid cards
without restrictions**.

## Consolidating the cards with Stripe
The best solution I came up with was to **pretend to be a merchant and purchase
imaginary products from myself**. For that, I created an account on
[Stripe](https://www.stripe.com), a payment processor that enables merchants to
receive payments online. Using Stripe's web interface, I created payments using
the prepaid cards to my Stripe account.

The account is linked to your bank account and after you receive a payment,
Stripe automatically transfers the amount to your bank account.

They take a small fee of $0.59 for each $10 payment, but that's a small price to
pay to fully unlock the value on the prepaid cards.

_Note that you can probably apply a similar trick with PayPal. We use Stripe at
[Sutori](https://www.sutori.com) and since I'm familiar with the interface, it
didn't take me long to set up._

## Conclusion
With a simple trick, I managed to get the value from all my prepaid cards onto
my bank account while losing only a little bit on fees.
