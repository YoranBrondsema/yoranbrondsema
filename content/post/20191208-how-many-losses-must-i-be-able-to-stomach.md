---
title: "How many losses must I be able to stomach?"
date: 2019-12-08T16:03:16+01:00
slug: how-many-losses-must-i-be-able-to-stomach
tags: ["Investing"]
toc: true
description: "Downturns are scary. Using the histogram of monthly returns and drawdown analysis, I analyze how bad downturns have impacted my portfolio over the last 20 years in order to be better prepared for the future."
---

It's been a couple of years that people have predicted the impending doom, the
end of the bull run that the markets have been in since the end of the
financial crisis. This got me thinking: how bad will the next downturn affect
my portfolio? What kind of fluctuations in its value will I see? After all,
I've never experienced a downturn since I started investing.

The only way at my disposal to answer this question is look at the past. By
diving back in history, I can see how bad returns got and get a feeling of how
bad they can be. Has my portfolio seen months with drops of 20%, or even 30%?
Or has 10% been the worst it's seen?

In this article, I will answer these questions by looking at the distribution
of monthly returns of my portfolio. Furthermore, I am going to investigate the
length and depth of the drawdown periods, i.e. periods where my portfolio has
been at a loss.

## My portfolio
To set the context, below is my portfolio as it is at the time of writing. It's
the portfolio that I will be analyzing. It's fairly classic for the passive
investor, consisting of a mix of stocks, bonds and REITs (real-estate).

| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 49%        
| [iShares MSCI World Small Cap](https://www.justetf.com/en/etf-profile.html?isin=IE00BF4RFH31)       | Stocks      | 14%        
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        
| [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | Real-estate | 9%         

## Histogram of the monthly returns
Let's look at the histogram of the monthly returns between December 2000 and
November 2019.

{{< figure src="/images/histogram-of-monthly-returns.svg" caption="Histogram of monthly returns of my portfolio between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2019-11&periodStart=2000-12))" >}}

To calculate this chart, we divided all the monthly returns in the period into
buckets: the returns between -10% and -8% go into one bucket, those between -8%
and -6% in another, and so on. Then we simply compute the number of months in
each bucket. Furthermore, we assumed that we invested only a lump sum of
€10,000 at the beginning of the period, without any later investments.

From the figure, we can deduce that **my portfolio lost value for 38% of the
months**. That's more than a third of the time, and much higher than I
expected!

The worst months were:

- **October 2009: -10.0%**
- September 2001: -8.5%
- June 2002: -8.3%

On the other hand, the best months were:

- **April 2009: 11.3%**
- January 2019: 6.9%
- October 2015: 6.9%

So -10.0% is the worst return in a single month that my portfolio has seen over
the last 19 years. **I think I can handle that, but time will tell.**

In a way, the histogram is a different way of looking at the volatility of a
portfolio. The standard deviation, which I used to calculate the Sharpe ratio in [Analyzing the Sharpe ratio of my portfolio]({{< ref "post/20190610-sharpe-ratio-analysis-of-my-portfolio.md" >}}), is another metric
used to analyze the volatility. But I do believe that the
histogram is much more intuitive and yields a more complete picture. In the
end, the standard deviation is just a number and doesn't mean much to us unless
it's compared to the standard deviation of other portfolios.

## Longest drawdown period
The histogram gives us an idea of what kind of monthly returns we can expect
and their frequency. But it doesn't tell us how long periods of negative
returns occur. For this, we need to look at the drawdown chart.

{{< figure src="/images/drawdown.svg" caption="Drawdown chart of my portfolio between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2019-11&periodStart=2000-12))" >}}

A drawdown starts when the value of a portfolio goes down. The time between
reaching a peak and its recovery is the drawdown period.

Let's look at the longest drawdown period in our simulation period. In May
2001, the portfolio reached a peak before going downhill. **It took 4 years for
the portfolio to recover**, in June 2005. In the meantime, **it had lost 32.5% of
its value** at the lowest point.

This was the longest drawdown period but not the deepest. That occurred during
the 2007-2008 financial crisis. **Between May 2007 and December 2010, the
portfolio lost 41.2% of its value.**

These are quite severe downturns. **Intuitively, I know that I will have less
problems with the severity of a downturn than with its duration.** Losing 41.2%
of the portfolio over a short period of time doesn't feel "too bad" because I
have the belief that it will recover in a similar amount of time.  But not
seeing any gains for four years in a row feels much harder mentally.

## Comparison with other portfolios
One of the goals of diversification is to soften the ride by reducing
volatility. For that purpose, I am performing the same analysis for two extreme
portfolios:

1. **100% stocks.** The portfolio tracks the MSCI World index.
2. **100% bonds.** The portfolio tracks the FTSE World Government Bond (EUR
   Hedged) index. This is a global index of government bonds of developed
   countries but hedged to Euro to get rid of the volatility due to currency
   exchange rates.

We expect the MSCI World portfolio to see much more extreme monthly returns.
Also, it will exhibit longer and deeper drawdown periods. In contrast, the
portfolio of bonds should be an easy ride!

### 100% stocks
{{< figure src="/images/histogram-of-monthly-returns-msci-world.svg" caption="Histogram of monthly returns of MSCI World between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgsgygwgkgBAdQPYCcA2ATEAaYoAyAqgIwDsAHMQKwAsxZAnDsQLptA?periodEnd=2019-11&periodStart=2000-12))" >}}

Indeed, We can see that the monthly returns are more extreme. The worst months
are:

- September 2002: -11.7%
- June 2002: -11.1%
- October 2008: -10.2%

Remember that my portfolio's worst month was -10.0%. The best performing months
are:

- April 2009: 11.5%
- October 2015: 9.1%
- January 2019: 7.4%

{{< figure src="/images/drawdown-msci-world.svg" caption="Drawdown chart of MSCI World between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgsgygwgkgBAdQPYCcA2ATEAaYoAyAqgIwDsAHMQKwAsxZAnDsQLptA?periodEnd=2019-11&periodStart=2000-12))" >}}

The worst drawdown period is also more extreme. **The longest and deepest
drawdown period lasted for 6 years and 3 months** and was between January 2001
and May 2007. That's 2 years longer than the longest drawdown period of my
portfolio. During that time, **it lost up to 46.8% of its value**.

### 100% bonds
{{< figure src="/images/histogram-of-monthly-returns-ftse-wgbi-hedged-eur.svg" caption="Histogram of monthly returns of FTSE World Government Bond (Hedged EUR) between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgYgKgygogBAdQPYCcA2ATOBxJA3AUxQDsBbA4gFzgCElisBaOAEQMLSQAcCsBZAIYoA1gUoBnOAAoAErwDmvODACqAJQCUIADTBQAGRUAGAMwB2ABwWAjDZPWd1gLougA?periodEnd=2019-11&periodStart=2000-12))" >}}

As expected, the returns are far less extreme. The worst months are:

- November 2016: -1.8%
- July 2003: -1.8%
- January 2009: -1.6%

Those are easy peasy! Of course, there's no free lunch. The low negative
returns mean that the positive returns are much lower:

- November 2008: 3.1%
- August 2019: 2.7%
- June 2016: 2.3%

Interestingly, **the bond index has had some of its best months when stocks
weren't performing**, for instance in November 2008. That shows that there
are times when the correlation between bonds and stocks is very low.

{{< figure src="/images/drawdown-ftse-wgbi-hedged-eur.svg" caption="Drawdown chart of FTSE World Government Bond (Hedged EUR) between Dec 2000 and Nov 2019 (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgYgKgygogBAdQPYCcA2ATOBxJA3AUxQDsBbA4gFzgCElisBaOAEQMLSQAcCsBZAIYoA1gUoBnOAAoAErwDmvODACqAJQCUIADTBQAGRUAGAMwB2ABwWAjDZPWd1gLougA?periodEnd=2019-11&periodStart=2000-12))" >}}

As expected, the drawdown chart also looks less extreme. **The longest drawdown
period lasted for 2 years and 11 months between July 2016 and July
2019. It reached a trough of -6.0%.**

### Conclusion
The charts show that stocks and bonds exhibit very different behaviours in
terms of volatility. You must be able to stomach wild extremes if your
portfolio only consists of stocks. Diversifying with for instance bonds can
soften the extremes.

## Softening the ride through periodic investing
In the previous simulations, we performed an initial investment of €10,000 and
didn't do any follow-up investments. But that is not the pattern that most
investors follow. Instead, people tend to make recurrent investments, for
instance every month, as it follows their income pattern. I currently
contribute €200 every month to my investment account.

What is the effect of periodic investing as opposed to investing a one-off lump
sum? The theory says that it should reduce volatility. Let's see if that's the
case for us!

{{< figure src="/images/histogram-of-monthly-returns-recurrent-investments.svg" caption="Histogram of monthly returns of my portfolio between Dec 2000 and Nov 2019 with a €200 monthly investment (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2019-11&periodStart=2000-12))" >}}

Worst months:

- October 2008: -10.0%
- September 2001: -8.5%
- June 2002: -8.3%

Best months:

- April 2009: 11.3%
- January 2019: 6.9%
- October 2015: 6.9%

The distribution of monthly returns did not change. This makes sense as
a €200 investment is negligible compared to the value of the total portfolio.

{{< figure src="/images/drawdown-recurrent-investments.svg" caption="Drawdown chart of my portfolio between Dec 2000 and Nov 2019 with a €200 monthly investment (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2019-11&periodStart=2000-12))" >}}

However, we see that the recurrent investment pattern has significantly
improved the drawdown behaviour. When we invested a lump sum, our longest
drawdown period was 4 years. **It halved to 2 years when investing
periodically!** Also, **the deepest trough is -30.9% instead of -41.2%**. So
investing regularly eases the ride.

What is the intuition behind this? When you invest regularly, you actually
profit from the downturns. Investing at the lowest moments of a downturn
accelerates recovery because you buy when prices are at its cheapest.

**Investing a lump sum also makes you much more sensitive to the timing of your
investment.** For instance, compare the average return of my portfolio for a
one-off €10,000 investment for the following two 10-year periods:

- May 2007 to May 2017: 5.89% (from [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2017-06&periodStart=2007-05))
- February 2009 to February 2019: 12.96% (from [Backtest](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA?periodEnd=2019-03&periodStart=2009-02))

**The periods are less than two years apart yet the average annual return rate
is more than twice the difference!** The reason is that in the first scenario,
we invested our €10,000 right before the financial crisis. And in the second
scenario, we invested right in the middle of the crisis, when prices were
lowest. This sensitivity to timing is much less pronounced when investing
regularly.

## Perform your own analysis with Backtest
Finally, **you can run the same analysis for your own portfolio using
[Backtest](https://backtest.curvo.eu)**, a free tool made by us at
[Curvo](https://curvo.eu). We are building Backtest specifically for European
passive investors because a similar tool did not exist. Simply [add your portfolio](https://backtest.curvo.eu/portfolio/new) and see what comes out!

## Key takeaways
We looked at the histogram of monthly returns and the drawdown chart of my
portfolio for the last 19 years. Then, we compared them to two extreme
portfolios: one of 100% stocks and one of 100% bonds. We also looked at the
impact of periodic investments on the volatility. My key takeaways are from the
analysis are:

1. **At 38%, the ratio of negative monthly returns is higher than I expected.**
   On average, more than one third of the months have a negative return.
2. **The long drawdown periods of the past scare me.** I plan on keeping my
   investments until retirement, in 30 years or so. Given that time horizon,
   one or more downturns are bound to happen. Being at a loss for many years in
   a row will be mentally challenging. I hope that in those times, my ratio
   will be victorious over my psyche!
3. **Diversification softens extremes.** Diversification results in lower
   extremes and shorter drawdown periods.
4. **Periodic investing is the way to go.** Spreading out your investments
   over time reduces the sensitivity to market conditions at the time of
   investment. Plus, it reduces drawdown periods because you speed up
   recovery by investing during downturns. This is a non-negligible effect.
