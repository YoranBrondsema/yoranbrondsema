---
title: "Choosing the right rebalancing strategy for your portfolio"
date: 2019-07-18T17:40:36+02:00
toc: true
slug: 'choosing-the-right-rebalancing-strategy-for-your-portfolio'
description: "What is the best rebalancing strategy to adopt for maximal returns? Quarterly? Yearly? I ran experiments using historical data going back to 1987 for portfolios that are common for EU investors to find out the answer."
---

## What's rebalancing?
The first step for any passive investor is to define the [allocation]({{< ref "post/my-asset-allocation.md" >}}) of his
portfolio. What portion of the portfolio should be bonds? What portion
should be equity?

Once the allocation is defined and the funds have been purchased, it must be
maintained. After all, the funds in the portfolio will evolve differently. Some
funds may go up while others go down, and over time the portfolio will
increasingly diverge from the intended allocation.

This changes the risk level of your portfolio and it may no longer reflect your
risk tolerance. For instance, suppose that your initial allocation consists of
50% bonds and 50% equity. After some time, this may have shifted to 30% bonds
and 70% equity, because stocks have been doing particularly well. In terms of
risk, your portfolio has become very different than the one that you originally
set up.

Therefore, from time to time, **the portfolio must be rebalanced to its
intended allocation**. Funds that are over-represented are sold and
under-represented funds are bought.

**When should you rebalance?** That is the question that we answer in this
article.

## Different types of rebalancing
The rebalancing strategies that we will analyze can be put in two categories:

- **Calendar rebalancing**. In this type of strategy, we are going to rebalance
  at fixed intervals, for example every quarter, every year, every two years,...
- **Percentage-of-portfolio rebalancing**. Here, we are going to define a
  tolerance corridor for our assets, for example 5%. When one of our assets
  deviates 5% or more from its intended allocation, we are going to rebalance
  the entire portfolio. If we have a portfolio that is composed of 20% bonds and 80% equity, we
  are going to rebalance when the bonds fund goes lower than 15% or higher than
  25% (or when the equity fund reaches 75% or 85%).

## Which rebalancing strategy works best?
The best tool to evaluate which strategy works best, is to look at the
historical performance of a portfolio for the different rebalancing strategies.

We are going to perform three simulations:

1. First, **we are not going to model transaction fees** that are charged by the
   broker whenever we buy or sell an asset.
2. In the second simulation, we are going to make it **more realistic by
   introducing transaction fees** and see how it affects the different
   rebalancing strategies.
3. Finally, we are going to run the second simulation with a different
   portfolio. The goal of this simulation is to find out how much the
   performance of the different rebalancing strategies varies across
   portfolios.

Furthermore, we are making the following assumptions for our simulation.

* We are simulating for the period **from December 1987 to June 2019**. That is
  the period for which we have historical data.
* We are making an **initial investment of €10,000** and are not making any further
  contributions.
* We are working directly with the index prices and not with the historical
  data of a fund that tracks the index. The total expense ratio, the fee that
  fund providers charge to manage the fund, is therefore not included in the
  simulation. This won't affect the comparison between the
  rebalancing strategies though.

The simulations are run using [Backtest](https://backtest.curvo.eu), the
custom back-testing tool that I wrote.

### Simulation 1: no transaction fees
First, we are going to simulate a portfolio that is common and works well for the
European investor. The blog "Index Fund (European) Investor" [recommends a similar portfolio](https://indexfundinvestor.eu/2019/07/18/simple-portfolio-for-european-investors/).
It consists of 20% bonds and 80% equity, the latter divided over developed
markets and emerging markets.

| Index                                                       | Allocation |
|-------------------------------------------------------------|------------|
| FTSE World Government Bond - Developed Markets (Hedged EUR) | 20%        |
| MSCI World                                                  | 64%        |
| MSCI Emerging Markets                                       | 16%        |

The table below summarizes the results. It ranks the strategies in terms of performance from best to worst.

| Strategy                      | Annual return rate | Difference with max |
|-------------------------------|----------------------------|---------------------|
| 10% tolerance per asset       | 8.86%                      | 0.00%               |
| Every three years rebalancing | 8.79%                      | -0.08%              |
| Yearly rebalancing            | 8.68%                      | -0.18%              |
| Every two years rebalancing   | 8.57%                      | -0.29%              |
| 5% tolerance per asset        | 8.55%                      | -0.32%              |
| Semesterly rebalancing        | 8.52%                      | -0.35%              |
| Quarterly rebalancing         | 8.49%                      | -0.37%              |
| 20% tolerance per asset       | 8.46%                      | -0.40%              |
| Monthly rebalancing           | 8.39%                      | -0.47%              |
| 15% tolerance per asset       | 8.33%                      | -0.54%              |
| No rebalancing                | 8.27%                      | -0.59%              |

We can make the following observations:

* As a general rule, **it's better to rebalance less frequently than too often**.
  Rebalancing yearly, every two years or every three years yield amongst the
  best returns. Of all the calendar rebalancing strategies, rebalancing every
  three years works the best! Intuitively, it can be explained. Once an asset
  is going up, it will likely continue going up for some time. Rebalancing too
  often causes us to sell parts of this rising asset with "momentum" too soon.
  So it's best to keep that asset for a longer period, than say a month. 
* **Percentage-of-portfolio strategies are not worth the extra complexity.**
  It looks like they're very hit-or-miss. Using a 10% tolerance yields the best
  returns, but 15% is one of the worst. The performances of the various
  tolerances are all over the place and it's hard to pick the right tolerance
  for your portfolio.
* Overall, **the effect of rebalancing on the final return is moderate**. The
  maximum difference between the optimal strategy that we tested and no
  rebalancing is less than 0.6%. This isn't negligible but not dramatic either.
  The difference between rebalancing yearly or every three years is 0.1% so
  it's not something to fuss too much about.

### Simulation 2: modeling transaction fees
In the previous simulation, we didn't take into account transaction fees. In
reality, brokers charge a commission fee on every transaction (the exception
being DeGiro for certain funds). To make our model more realistic, I extended
the software to **charge a €6.00 commission fee for every transaction**. So if
a rebalancing operation involves all three assets in the fund, the entire
operation will cost €18.00. I chose this fee because it's the one I pay at
Lynx, my broker.

By introducing transaction fees, we expect strategies that rebalance often to
be penalized. The results are shown in the table below:

| Strategy                      | Average annual return rate | Difference with max |
|-------------------------------|----------------------------|---------------------|
| 10% tolerance per asset       | 8.84%                      | 0.00%               |
| Every three years rebalancing | 8.76%                      | -0.08%              |
| Yearly rebalancing            | 8.62%                      | -0.22%              |
| Every two years rebalancing   | 8.54%                      | -0.31%              |
| 5% tolerance per asset        | 8.51%                      | -0.33%              |
| 20% tolerance per asset       | 8.45%                      | -0.39%              |
| Semesterly rebalancing        | 8.40%                      | -0.45%              |
| 15% tolerance per asset       | 8.31%                      | -0.53%              |
| No rebalancing                | 8.26%                      | -0.58%              |
| Quarterly rebalancing         | 8.25%                      | -0.60%              |
| Monthly rebalancing           | 7.61%                      | -1.23%              |

Indeed, now the monthly and quarterly rebalancing strategies become
particularly unattractive. The top of the table didn't change much compared to
the previous simulation. Indeed, the best rebalancing strategies aren't
rebalancing often anyway.

Below, the results of the first two simulations are shown visually.

{{< figure src="/images/comparison-of-rebalancing-strategies.svg" caption="Comparison of the returns for the various rebalancing strategies." >}}

### Simulation 3: measuring the effect of a different portfolio
Here, we are going to run the simulation with a different portfolio. This way,
we can see whether the results are consistent across different portfolios.
 
We are going to simplify the previous portfolio by replacing the MSCI World and
MSCI Emerging Markets funds with a combined MSCI ACWI fund. The ratio of equity
to bonds remains the same.

| Index                                                       | Allocation |
|-------------------------------------------------------------|------------|
| FTSE World Government Bond - Developed Markets (Hedged EUR) | 20%        |
| MSCI ACWI                                                   | 80%        |

When we run the simulation for this portfolio, while taking into account
transaction fees, we get the following results:

| Strategy                      | Average annual return rate | Difference with max |
|-------------------------------|----------------------------|---------------------|
| Yearly rebalancing            | 7.81%                      | 0.00%               |
| 5% tolerance per asset        | 7.76%                      | -0.05%              |
| Every two years rebalancing   | 7.71%                      | -0.10%              |
| Every three years rebalancing | 7.67%                      | -0.14%              |
| Quarterly rebalancing         | 7.67%                      | -0.14%              |
| No rebalancing                | 7.58%                      | -0.23%              |
| 10% tolerance per asset       | 7.58%                      | -0.23%              |
| 15% tolerance per asset       | 7.58%                      | -0.23%              |
| 20% tolerance per asset       | 7.58%                      | -0.23%              |
| Semesterly rebalancing        | 7.50%                      | -0.31%              |
| Monthly rebalancing           | 7.16%                      | -0.65%              |

The yearly, two-yearly and three-yearly rebalancing strategies are still
performing very well for this portfolio. However, for percentage-of-portfolio
strategies, the 5% tolerance now performs the best and the 10% tolerance
performs worse than not rebalancing at all.

From this, we can draw the conclusion that **for percentage-of-portfolio
strategies, it's very hard to pick the right tolerance that works best for your
portfolio**.

## Conclusion
In a way, rebalancing is as close as timing the market as a passive investor
can come. We don't like timing the market, but unfortunately we cannot avoid
having to choose a rebalancing strategy.

The most important lesson to be drawn from these simulations is that **it's
better to rebalance infrequently rather than too often**. Rebalancing every
year, every two years or every three years seem to be good strategies.
However, it's also important not to stress too much about your rebalancing
strategy, as the difference in performance between these three is not very
significant.

**Secondly, percentage-of-portfolio strategies are very sensitive to the chosen
tolerance.** We saw that the performance of the various tolerances varied
considerably between the two portfolios. **Sticking to calendar rebalancing is
a safer option.**
