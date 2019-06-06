---
title: "A Sharpe ratio analysis of my portfolio"
date: 2019-06-06T10:37:54-05:00
slug: a-sharpe-ratio-analysis-of-my-portfolio
tags: ["Investing"]
toc: true
draft: true
---

In [a previous post]({{< ref "post/deep-dive-into-the-past-performance-of-my-portfolio.md" >}}), I analyzed
the historical performance of my portfolio of index funds. I calculated that it
achieved a 6.4% average annual return rate for the period between 2000 and 2015.
Looking solely at the returns of a portfolio only gives a partial picture of its
performance though. Some investments, such as cryptocurrencies, can yield very
high returns but also carry a lot of risk due to their wild fluctations.

The Sharpe ratio is a measure that incorporates the notion of risk in its
calculation. It provides a means to compare the performance of a portfolio while
taking into account risk.

In this post, I analyze the Sharpe ratio of my portfolio and compare it against
benchmarks such as the S&P 500 and the MSCI World index.

## What is the Sharpe ratio?
The Sharpe ratio is a means to measure the performance of a portfolio by
incorporating the notion of risk. **In essence, the Sharpe ratio of an
investment is its return divided by the risk taken to achieve that return:**

$$
S = \frac{return}{risk}
$$

By adding the Sharpe ratio to our toolbox, we are getting a more complete
understanding of the performance of a portfolio.

## How is it calculated?
Using the formula above, we need to calculate both the return and its risk of
the portfolio. It's easy to calculate the average return, but how we can
translate an abstract notion such as risk into a number?

The Sharpe ratio finds its origins in the capital asset pricing model (CAPM).
This model says that the risk of an investment equals to its volatility. And
from statistics, we know that we can compute the volatility using the standard
deviation.

We now come to the formula for the Sharpe ratio:

$$
S = \frac{E[R - R_f]}{\sigma(R - R_f)}
$$

That's a lot of math! Let's explain each part one by one.

$R$ is the return of our portfolio and $R_f$ is the risk-free return. A
risk-free investment is one where it's impossible to make a loss. For example, a
savings account is a risk-free investment, because the interest rate that the
bank offers will never be negative.However, your bank can still go bankrupt so
it's not as risk-free as we think. So to calculate the Sharpe ratio, we
typically use the returns on short-dated government bonds. In particular, we use
the Effective Federal Funds Rate set by the US government. The explanation of
what that is is a bit too technical so I refer you to this [article on
Investopedia](https://www.investopedia.com/terms/f/federalfundsrate.asp) to
learn more.

Knowing this, we can interpret $R - R_f$ as the return of our portfolio adjusted
for the risk-free rate. We call this the **excess return**: it's the return that
we make on top of the return that we get if we don't take any risk at all.

$E[X]$ is the mathematical notation to denote the average. In our case, $E[R - R_f]$ is the average of the excess return of our portfolio.

Finally, $\sigma$ is the mathematical notation for the standard deviation. As
we mentioned before, we use the standard deviation as a measure for the risk of
our portfolio. $\sigma(R - R_f)$ is the standard deviation of our excess
return.

There we have it! We can now plug it into our simulator.

## What does the Sharpe ratio tell us?
A high Sharpe ratio means that we achieve a high return without taking too much
risk. Alternatively, we can say then that our high returns are because of smart
investment decisions rather than because of excessive risks. So a higher Sharpe
ratio is better.

We can increase the Sharpe ratio of our investments by either attaining a higher
ratio or reducing the volatility.

## Calculating the Sharpe ratio on our portfolio
### The portfolio
The table below shows my portfolio, which is the one that I'll be analyzing.

Type               | ETF                                                                                                 | Allocation
-------------------|-----------------------------------------------------------------------------------------------------|----
Government bonds   | [Xtrackers Global Sovereign](https://www.justetf.com/en/etf-profile.html?isin=%20LU0908508731)      | 18%
Developed markets  | [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | 49%
Small cap          | [iShares MSCI World Small Cap](https://www.justetf.com/en/etf-profile.html?isin=IE00BF4RFH31)       | 14%
Emerging markets   | [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | 10%
REIT               | [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | 9%

### The simulator
I looked for tools that I could use to run this analysis but I couldn't find one
that suited exactly my needs. So I used my software engineering skills to build
my own. All the numbers and charts that follow come directly from the results of
the [the simulation software](https://portfolio-simulator.netlify.com/sharpe-ratio/yoran).

I made its source code
[available on GitHub](https://github.com/YoranBrondsema/portfolio-simulator),
together with some explanation on how to run it on your own computer. I also
included the links to the sources for the historical data used for the analysis.

### Show me the results
**The Sharpe ratio of my portfolio is 0.34** for the period from 2000 to 2015.
However, this doesn't tell us very much on its own. It's more helpful to compare
it against benchmarks. The standard benchmark to use is the S&P 500 index.

Next, I was interested to see how our portfolio compared to the MSCI World
index. Almost half of my portfolio consists of the MSCI World index and making
the comparison will tell us whether or not our diversification strategy works.

The results are in the table below.

|Name|Average annual return|Standard deviation|Sharpe ratio|
|--- |--- |--- |--- |
|Yoran's Portfolio|6.8%|20.2|0.34|
|S&P 500|5.4%|18.6|0.29|
|MSCI World|5.4%|23.0|0.24|

**The Sharpe ratio of my portfolio beats that of both the S&P 500 and the MSCI
World index**. This is a confirmation that diversification works! Our volatility
is a bit higher than that of the S&P 500 but it's compensated with a higher
return. Furthermore, our diversified portfolio performs better than the MSCI
World index on its own, both in terms of returns and volatility.

### Evolution of the Sharpe ratio over time
Next, I was interested in the evolution of the Sharpe ratio over time. Does it
vary year to year? It turns out it does.

{{< figure src="/images/sharpe-ratio-evolution.png" caption="Evolution of the Sharpe ratio year to year." >}}

We can see that it seems to follow the trend of the markets as a whole. This
makes sense, as the Sharpe ratio is based on the returns after all. For
instance, during the financial crisis of 2007-2008, the Sharpe ratio was
negative because the markets were down by almost 50%.

For the past few years, both the S&P 500 and the MSCI World index have had a
better Sharpe ratio than my portfolio. I think it's because the other funds in
the portfolio, i.e. emerging markets, small cap, real-estate and bonds, haven't
been performing as well as the stocks in the developed markets. Overall though,
as we've seen in the previous analysis, our portfolio still performs better over
a longer period of time.

## The Sharpe ratios of top funds
Finally, let's conclude with a look at the Sharpe ratios of the best actively
managed funds.

Let's start with Berkshire Hathaway, Warren Buffett's "fund". Because it's a
publicly traded company, the historical data is available on [Yahoo Finance](https://finance.yahoo.com/quote/BRK-A/history?period1=322120800&period2=1559883600&interval=1mo&filter=history&frequency=1mo).
For the period that we are looking at, from 2000 to 2015, its **Sharpe ratio was
0.46** for an annual average return of **8.5%** and a standard deviation of
18.5. This is better than the Sharpe ratio of my portfolio at 0.34. What
else can you expect from one of the most successful investors of the past
decades!

Another legendary fund is the Medallion Fund. It's managed by Renaissance
Technologies, the hedge fund founded by the mathematician James Simons. Unlike
Berkshire Hathaway, I could not run my own analysis because hedge funds are not
required to publicly disclose their returns. However, I did find a [Quora answer](https://www.quora.com/What-kind-of-Sharpe-ratio-does-Renaissance-Technologies-have/answer/Vladimir-Novakovski)
that sheds some light on the Sharpe ratio they are achieving. It's very
impressive to say the least:

> The Medallion fund, around since 1988, had a Sharpe ratio around 2 for a
> while, then after the mid-90s, they made a number of improvements (and rolled
> an equities strategy into the fund that was previously only futures /
> currencies), bringing the Sharpe up to 4 or so. Beyond 2000, they made further
> improvements that brought up the Sharpe ratio to levels of 10 or higher[...]

Both Berkshire Hathaway and Renaissance Technologies are amongst the top
actively managed funds, so it's not a surprise that they achieve higher Sharpe
ratios than our portfolio, which is just based on index funds. However, [the majority of actively managed funds are outperformed by the S&P 500](https://www.spglobal.com/en/research-insights/articles/SPIVA-US-Scorecard).
Because the top funds are not accessible to "normal" people like you and me,
passive investing is the best strategy that we can follow.

## Limitations of the analysis
As with any analysis, there are limitations to its validity.

### Longer-time horizon
I calculated the Sharpe ratio for the period from 2000 to 2015 because it's the
only data that I have available. Ideally, I'd like to extend the duration of the
simulation so I'm constantly keeping an eye out for sources where I can find
historical data outside of this period.

### Weaknesses of the Sharpe ratio
The Sharpe ratio comes from the capital asset pricing model, which, like any
other scientific model, is only an approximation and not a complete
representation of reality. Let's look at some of the assumptions underlying the
Sharpe ratio that may not be entirely accurate.

#### Negative Sharpe ratios have no meaning
We saw in the chart above that Sharpe ratios become negative during bear
markets. In those situations, the formula says that we can bring the Sharpe
ratio closer to zero by increasing volatility. Simple logic tells us that this
is not a good thing to do. So during periods of negative returns, the Sharpe
ratio is a bad tool for analysis.

#### Returns of real investments are not normally distributed
In order to use the standard deviation to calculate the volatility of an
investment, the returns of the investment must be distributed according to the
normal distribution. However, in reality this is not the case. Instead, the
returns of investments in financial markets have fatter tails, meaning that
outliers happen more frequently than the normal distribution would dictate.
Instead, they are more accurately described by the Cauchy distribution.

This means that the standard deviation is not an entirely accurate way to
calculate the volatility of our portfolio and that the "real" Sharpe ratio,
calculated for the Cauchy distribution, would be different.

#### Upside volatility is not necessarily bad
The Sharpe ratio treats all volatility the same. However, you can argue that
upside volatility is not as bad as downside volatility. In fact, upside
volatility is required to achieve high returns. The Sortino ratio is an
improvement on the Sharpe ratio that only takes into account downside
volatility.

## Conclusion
After having solely analyzed the [returns of my portfolio]({{< ref "post/deep-dive-into-the-past-performance-of-my-portfolio.md" >}}), this post is
a second step in gaining a deeper understanding by introducing the notion of
risk. Despite its limitations, the Sharpe ratio is a useful tool with which we
can compare the risk-adjusted performance of my portfolio to benchmarks such as
the S&P 500 or the MSCI World index.

The results of the analysis show that the Sharpe ratio of our portfolio beats
that of the benchmarks. This is an indication that our diversification strategy
works and it gives me confidence in the future performance of the portfolio.
