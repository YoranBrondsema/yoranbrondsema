---
title: "Portfolio performance report Q3 2020"
date: 2020-11-23T21:12:43-05:00
slug: portfolio-performance-report-q3-2020
tags: ["Investing"]
toc: true
description: "2020 Q3 results of my passive investing portfolio."
---

## Late report
The report for this quarter comes very late. It's already been almost a month
and a half since the quarter ended! However, I have found myself extremely busy
working on three projects at the same time, each demanding their share of time:

- [Curvo](https://curvo.eu). We've finally passed the regulatory obstacle,
  meaning that we're currently getting ready for launch. For me, that means
  that I'm trying to focus as much time as possible on the development of the
  mobile app that Curvo customers will use to invest and keep track of their
  portfolio.
- [Backtest](https://curvo.eu/backtest). Since we launched Backtest in July of
  last year, its usage has increased to 250 daily users. It's not a huge number
  but it's growing fairly steadily. We were at 100 users per day only 3 months
  ago. I've been trying to keep up with the rate of funds that users have been
  requesting but I haven't done a great job at it. The backlog is quite long!
  But every week I'm finding time to add a couple of new funds, so eventually
  we'll get there.
- [Sutori](https://www.sutori.com). And I'm also still the CTO of Sutori, a
  online learning tool used by over 1.5 million teachers and students globally.
  With many schools switching to online learning, we've been one of the lucky
  companies who've actually "benefited" from the pandemic. Our growth has been
  pretty spectacular these past few months.

This also means that I haven't had time to do any more analyses on my portfolio
and writing them up on this blog. It was necessary for me to make choices in
order not to drown in work.

## My investments as of October 1st 2020
### Composition
In the first quarter of 2020, I simplified my portfolio from 5 funds to 3 funds (see why I removed the [small-cap fund]({{< ref "post/20200516-simplifying-my-portfolio-pt-1-questioning-the-small-cap-fund.md" >}}) and the [REIT fund]({{< ref "post/20200628-simplifiying-my-portfolio-pt-2-what-about-reits.md" >}})). I haven't changed the composition of my portfolio since last quarter.

My current portfolio looks as follows:

| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 72%
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        

### Growth of the portfolio
{{< figure src="/images/2020-q3-portfolio-growth.svg" caption="Portfolio performance as of October 1st 2020." >}}

Markets recovered a little during the summer. My 6.3% return of last quarter
turned into a 9.8% return. This means that as of October 1st, I have a profit
of €3,383 with a total portfolio value of **€37,909**.

Another piece of good news is that I increased my monthly investments by 50% in
August. So I expect my portfolio to grow faster over the next year, simply
because I will be able to save more.

### Performance per asset
{{< figure src="/images/2020-q3-performance-per-asset.svg" caption="Performance per asset in my portfolio as of October 1st 2020." >}}

Not much to say here except that the stock markets have recovered a little bit
over the summer. Note how bonds have maintained their value all throughout the
corona-crisis!

## What I learned this quarter
I have taken an interest in **factor investing**. I first got introduced to it
through the [Rational Reminder podcast](https://rationalreminder.ca/), hosted
by Benjamin Felix (who else!) and Cameron Passmore. In a traditional market-cap
weighted index portfolio, you have exposure to one of the factors, market beta.
However, there are other factors that have proven to achieve a higher return
than market beta with a similar risk:
- the size factor (small cap vs large cap stocks)
- the value factor (high book-to-market vs low book-to-market)
- the profitability factor (robust profitability vs weak profitability)

I find factor investing interesting because it has been proved academically,
across different time periods and also across multiple countries. So it's not
just an American or European phenomenon.

The results are quite impressive in theory. A factor-optimized portfolio can
achieve a 1%-2% better yearly return than a traditional passive portfolio, with
a similar volatility. Note that it's still passive investing. We're not trying
to time the markets. It's just that the composition of the indexes is done on
different criteria than market-cap.

However, there's unfortunately a large difference between theory and practice.
I found that it's almost impossible to replicate the portfolios used in the
academic research in a real portfolio, using the financial products available
to us. Especially in Europe, where the choice of funds is (still) limited to
what's available in the US.

So I'd like to explore the practical implementations of factor investing for
European index investors over the next few months. Because a great theoretical
result is useless for investors if we can't put it into practice!
