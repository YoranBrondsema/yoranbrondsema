---
title: "Simplifying my portfolio (pt 1): questioning the small cap fund"
date: 2020-05-16T19:16:53+02:00
slug: simplifying-my-portfolio-pt-1-questioning-the-small-cap-fund
tags: ["Investing"]
toc: true
---

## Simplifying my portfolio
Of all the decisions that I made since I started investing, the one that I
regret the most concerns the complexity of [my portfolio]({{< ref "post/my-asset-allocation.md" >}}). It consists of 5 different funds, meaning
the broker fees that I pay for each investment round are high.

**In this series of articles I intend to investigate simplifying my
portfolio.** I will assess the role of each of its equity funds to determine
whether or not I can remove the fund without affecting exposure or performance.
If not, could I merge it with another fund?

The [rule of thumb](https://indexfundinvestor.eu/2020/05/04/how-much-should-you-spend-on-brokerage-fees/)
says that you shouldn't spend more than 0.5% of your annual investments on
transaction fees. I contribute €200 per month to my investments, meaning I
shouldn't spend more than €12 per year on broker fees.

My broker, Lynx, charges a minimum of €6.00 per transaction. Because my
portfolio has 5 funds, I spend €30 each investment round on broker fees alone.
Even if I invest only once per year, this is more than I should spend. The fees
are too high compared to my contributions and this will reduce the performance
of the portfolio in the long term.

## The role of the small cap fund
In this first article, we are going to scrutinize the role of the **small cap
fund** in my portfolio.

{{< table "table-simplify-portfolio-small-cap" >}}
| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 49%        
| ➡️ [iShares MSCI World Small Cap](https://www.justetf.com/en/etf-profile.html?isin=IE00BF4RFH31)       | Stocks      | 14%        
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        
| [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | Real-estate | 9%         
{{</ table >}}

## The problem with small cap stocks
In 1981, Banz published a paper[^1] where he found evidence of a "size effect".
By analyzing the US stock market between 1936 and 1975, he found that smaller
firms on average had higher risk adjusted returns than larger firms.  Since
then, small cap stocks have been regarded as deserving of their own allocation
in a diversified portfolio, next to other types of equities such as large cap
stocks. This was the basis for the presence of the small cap fund in my
portfolio.

But recently his findings got debunked. Researchers recreated the study in
2018[^2] using today's data and found:

1. The size effect that Banz discovered was statistically weak. His research
   barely meets the 10% significance threshold and does not meet the more
   commonly used threshold of 5%.
2. They could not replicate the size effect across different time periods and
   geographies.

The size effect does not really exist, so does this mean that we should get rid
of small cap stocks from our portfolio?

## Value stocks at the rescue
A different pattern emerges when we make a distinction between value and growth
stocks. It turns out that growth small cap stocks are responsible for the
underperformance and statistical unreliability of the asset class as a
whole[^3]. In other words, if we remove growth small cap stocks, the size
effect comes back to life. It becomes consistent over time and across
geographies, delivers a larger premium and it becomes statistically
significant.

### Composition of MSCI World Small Cap
The small cap fund in my portfolio, *iShares MSCI World Small Cap*, tracks the
MSCI World Small Cap index. We expect the index to hold both value and growth
stocks. Indeed, the image below shows that it holds about an equal amount of
value and growth stocks, with only a negligible tilt towards value stocks.

{{< figure src="/images/msci-world-small-cap-factors.png" caption="Factors of the MSCI World Small Cap index (source: [factsheet](https://www.msci.com/documents/10199/a67b0d43-0289-4bce-8499-0c102eaa8399))" width="450" >}}

### Performance of MSCI World Small Cap Value
The research tells us that we're better off getting rid of the small cap fund
unless we find a way to remove growth stocks from the small cap index and keep
only value stocks. MSCI has an index that does that: the **MSCI World Small
Cap Value** index.

Let's find out how the MSCI World Small Cap variants have compared to each
other in the past:

{{< figure src="/images/msci-world-small-cap.svg" caption="Evolution of the MSCI World Small Cap variants (source: [Backtest](https://curvo.eu/backtest/compare-indexes))" >}}

A backtesting period of 20 years is statistically insignificant. But it's
encouraging because it confirms the research: the premium as a result of the
size effect is larger for value small cap stocks than for growth small cap
stocks.

### Finding a global value small cap index
Great! So all we have to do is replace our small cap fund with a fund that
tracks a global small cap value index. Unfortunately, this is where the
good news ends.

A search on
[justETF](https://www.justetf.com/en/find-etf.html?assetClass=class-equity&equityStrategy=Small+Cap)
for all small cap equity funds yields the following indexes:

- EURO STOXX Small
- MSCI AC Far East ex Japan Small Cap
- MSCI EMU Small Cap
- MSCI Emerging Markets Small Cap
- MSCI Europe Small Cap
- MSCI Europe Small Cap Value Weighted
- MSCI Japan Small Cap
- MSCI UK Small Cap
- MSCI USA Small Cap
- MSCI USA Small Cap Value Weighted
- MSCI World Small Cap
- Russell 2000
- S&P SmallCap 600
- SDAX
- STOXX Europe Small 200

We are looking for an index that is **global** and contains only **value
stocks**. None of these indexes match these criteria.

## Verdict: drop the small cap fund
We face a situation where the ideal solution, a fund tracking the MSCI World
Small Cap Value index, does not exist in practice. The research shows that the
size premium does not exist when including growth small cap stocks, which is
the case for the MSCI World Small Cap index. **So until a small cap value fund
becomes available, we're better off dropping the small cap fund from our
portfolio** altogether.

## Updated portfolio
This decision liberates 14% of my portfolio. I don't want to change the
bond/equity ratio so I'm not going to allocate a higher percentage to the bond
fund. Also, I'm reticent on giving more exposure to real estate or emerging
markets.  That's why I'm going to allocate more to the MSCI World fund, its
large cap counterpart.

Now, we've obtained a simpler portfolio:

| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 63%        
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        
| [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | Real-estate | 9%         

## Acknowledgments
I would like to thank Ben Felix. His excellent video [The Problem With Small Cap Stocks](https://www.youtube.com/watch?v=uErHwq4M6pg) presented the research
that provided the basis for my conclusions. Furthermore, I highly recommend his entire [YouTube channel](https://www.youtube.com/channel/UCDXTQ8nWmx_EhZ2v-kp7QxA/featured)!

[^1]: [The relationship between return and market value of common stocks](http://www.business.unr.edu/faculty/liuc/files/BADM742/Banz_sizeeffect_1980.pdf)
[^2]: [Fact, Fiction, and the Size Effect](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3177539)
[^3]: [Size Matters, If You Control Your Junk](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2553889)
