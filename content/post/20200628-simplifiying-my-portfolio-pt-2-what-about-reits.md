---
title: "Simplifying my portfolio (pt 2): what about REITs?"
date: 2020-06-28T10:17:39+02:00
slug: simplifying-my-portfolio-pt-2-what-about-reits
tags: ["Investing"]
toc: true
---

## Investing the REIT fund
In the [first article of this series]({{< ref "post/20200516-simplifying-my-portfolio-pt-1-questioning-the-small-cap-fund.md" >}}), we scrutinized the role of the small cap fund in my portfolio. And we
concluded that it isn't worth keeping, because of the questionable benefits of
small cap stocks and the higher broker fees that come with having more funds in
a portfolio. In this article, we are going to take a hard look at the REIT fund
in my portfolio, *Amundi ETF FTSE EPRA NAREIT Global*[^1], which makes up 9% of
my portfolio.

{{< table "table-simplify-portfolio-reit" >}}
| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 63%        
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        
| ➡️ [Amundi ETF FTSE EPRA NAREIT Global](https://www.justetf.com/en/etf-profile.html?isin=LU1437018838) | Real-estate | 9%         
{{</ table >}}

## What are REITs?
Real estate investment trusts, or REITs, are a special type of fund that invest
primarily in income-producing real-estate assets. They were created in the US
in 1960 to enable investors to gain exposure to the real estate market without
having to operate the buildings themselves. Since then, REITs have been
expanded to many other countries around the world.

There are many types of REITs that are categorized based on the type of
building that they operate. Some examples include:

- **Residential.** They own and operate homes and apartment buildings which they rent out to individuals and families.
- **Retail.** Malls, shopping centres and other retail centres.
- **Office.**
- **Industrial.** Factories, warehouses and so on.
- **Speciality.** Properties that don’t fit within the other REIT sectors. Examples include movie theaters, casinos, farmland and outdoor advertising sites.

REITs are a good way for an investor to gain exposure to the real estate market
without having to own the property. Indeed, the ownership of real estate comes
with several problems:

- **Illiquidity.** Property is notoriously illiquid. I know many people around me who have had their house on the market for several years and still haven't been able to sell it. In contrast, shares of REITs are traded like stocks that you can buy and sell at any time. The liquidity is even higher when the REITs are packaged in an ETF that follows a REIT index.
- **Intensiveness of management.** Operating and renting out a building can be time-intensive and a huge hassle. REITs take care of all the management of its buildings so it demands no time on your part.
- **Lack of diversification.** Property that you buy as an individual tends to be concentrated in a single city or region, typically the area that you live in. This makes them a poorly diversified investment. On the other hand, because of their scale, REITs can own buildings all over the world.

## What's in the REIT fund?
The *Amundi ETF FTSE EPRA NAREIT Global* fund[^1] tracks the FTSE EPRA/NAREIT Developed index (they love their acronyms). This index consists of 335 REITs from 21 "developed" countries[^2]. Over half of the exposure comes from the US alone, though.

The index is diversified across various types of REITs:
- 29% industrial and office REITs
- 20% real estate holding and development
- 15% specialty REITs
- 15% residential REITs
- 13% retail REITs

All in all, it represents a good sample of the world real estate market.

## Why REITs belong in a passive investment portfolio
There are several reasons why you may want to consider adding REITs into your
portfolio of index funds.

### Distinct asset class
The real estate sector is often viewed as a distinct asset class, separate from
stocks and bonds. In theory, the inclusion of REITs in your portfolio should
result in a diversification benefit.

How true is that? We can check by examining the correlation between different
assets. The chart below shows the 36-month rolling correlation between the
**FTSE EPRA/NAREIT Developed** index and the **FTSE World Government Bond
Developed Markets (Hedged EUR)** index. The latter is a global index of
investment-grade government bonds. The bonds portion of my portfolio follows
this index.

{{< figure src="/images/correlation--ftse-epra-nareit-developed--ftse-world-government-bond-developed-markets-hedged-eur.svg" caption="36-month rolling correlation between the FTSE EPRA/NAREIT Developed index and the FTSE World Government Bond Developed Markets (Hedged EUR) index (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgSgogkgKgBAMjgIQPYDsAmBnEAaYUAGQFUBGAFgGYB2ABjIA5GrH86A6AVgF0CRSdAGwBOOiKEVxAJnbceCoA))" >}}

The correlation changes a lot, but there are clearly periods where it's low or
even negative.

Below, we plotted the correlation between the **FTSE EPRA/NAREIT Developed**
index with the **MSCI World** index, a stock index. Overall, the correlation is
quite high, although there have been periods where the correlation was close to
zero.

{{< figure src="/images/correlation--ftse-epra-nareit-developed--msci-world.svg" caption="36-month rolling correlation between the FTSE EPRA/NAREIT Developed index and the MSCI World index (source: [Backtest](https://backtest.curvo.eu/portfolio/NoIgSgogkgKgBAMjgZQC4HsDGBrAziAGmFABkBVARgBYBmAdgAYKAOZm5whgOgFYBdIiHIU6zCjyoURATk68+CoA))" >}}

After seeing these numbers, I'm not totally convinced that the real estate
market truly diversifies my portfolio, especially in relation to stocks.

### Historical returns have been very good
A second reason to include a REIT fund in your portfolio is that real estate
has seen very good returns over the last decades.

The chart below compares the performance of the FTSE EPRA/NAREIT Developed fund
with that of the MSCI World fund. The average returns of both indexes have been
fairly similar. Pre-Corona, I would argue that the REIT fund was performing
even better.

||Net asset value|Compound annual growth rate|Sharpe ratio|
|--- |--- |--- |--- |
|MSCI World|€75,144|6.86%|0.34|
|FTSE EPRA/NAREIT Developed|€68,941|6.55%|0.30|

{{< figure src="/images/comparison--ftse-epra-nareit-developed--msci-world.svg" caption="Comparison of €10,000 invested in the FTSE EPRA/NAREIT Developed fund and the MSCI World fund (source: [Backtest](https://backtest.curvo.eu/compare?portfolios=NoIgsgygwgkgBAdQPYCcA2ATEAaYoYCiADEQEIAsAMgKwCaAnABwDMOAjALpdA%2CNoIgYgKgygogBDACgJQIIHoByrkwJIRwAiApgG4kA2A9gA4kAmIANMKADICqAjACwDMAdgAM3ABxj%2BYltwC68oA))" >}}

## Why REITs *don't* belong in a passive investment portfolio
However, there are also reasons for excluding a separate REIT fund from your
portfolio.

### Other funds in my portfolio already allocate to real estate
REIT funds are not the only way to gain exposure to the real estate market. In
fact, the two other equity indexes in my portfolio, MSCI World and MSCI
Emerging Markets, include REITs and other real estate companies:
- 3.00% of MSCI World[^3]
- 2.67% of MSCI Emerging Markets[^4]

For instance, Prologis is the largest constituent in the FTSE EPRA/NAREIT
Developed index with a weight of 5.21%. But it's also present in the MSCI World
index, at a lesser weight of 0.16% nonetheless[^5]. Digital Realty Trust, the
second largest REIT, is represented in the MSCI World index as well.

### Overweighting the real estate sector is active investing
By adding a REIT fund to my portfolio, I essentially overweight the real estate
sector compared to its market capitalization. But I have no reason to believe
that I have an edge over the markets when it comes to real estate. I hardly
know anything about my local real estate market, let alone the global sector.
Furthermore, this looks suspiciously like active investing and contradicts the
philosophy of passive investing, which I adhere to.

### REITs are actually not that separate of an asset class
One of the reasons to include REITs as a separate fund in your portfolio is
that the behaviour of the real estate market is different enough from stocks
and bonds that they form a distinct asset class. Our analysis of the
correlation among the asset classes have put this in doubt. Recent academic
research cast further doubt on this claim.

Both *Real Estate Betas and the Implications for Asset Allocation*[^6] and *Are
REITs a Distinct Asset Class?*[^7] investigated if the returns of the real
estate sector can be explained by the same factors that underpin the risks and
returns of the stocks and bonds markets. It turns out that it does.

A portfolio consisting of 60% small cap value stocks and 40% high-yield bonds
achieves the same returns as the real estate market. The killer, though, is
that it does so **with a lower risk**. REITs are not adding any expected return
in excess of what could be achieved through stocks and bonds, but they are
adding additional **uncompensated risk**. Therefore, the most efficient way to
get exposure to the factor returns of REITs is actually through a portfolio of
stocks and bonds.

### Additional transaction fees
Every fund in my portfolio adds another trade that I have to do when I make a
round of investments. I aim to invest on a monthly basis and therefore I
suspect that these fees really affect the resulting performance of my
portfolio.

First, let's not take into account transaction fees just yet. In the chart
below, we compare the performance of my current portfolio that includes the
REIT fund, with the portfolio where I removed the REIT fund and allocated its
portion to the MSCI World fund instead:

||Net asset value|Compound annual growth rate|Sharpe ratio|
|--- |--- |--- |--- |
|Yoran's Portfolio|€87,024|7.37%|0.43|
|Yoran's Portfolio (without REIT)|€85,480|7.31%|0.42|

{{< figure src="/images/comparison--yoran-portfolio-reit.svg" caption="Comparison of €10,000 invested in my portfolio that includes the REIT fund and that excludes the REIT fund (source: [Backtest](https://backtest.curvo.eu/compare?portfolios=NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQAYBmAdgA4mBGNu10mgOnYF0yIAJIBRGjQBCAFgoBWMAE4mdbjwBsdQaDETJAFQBSAJQCyaOnLWttIaq2mMa7FUzU1F-L0A%2CNoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhQAoB3AzACwgFdMUAlAUQEkAVAShABphQAMgFUADAGYA7AA4pARjljZvEQDp5AXT4hWzESIBCAFgEBWMAE4pY5SokAmTaB1797AFKMAsmjEmbI80Cg4JCpdXCgA))" >}}

My current portfolio, which includes the REIT, performs slightly better.

However, things change when we simulate the scenario of monthly contributions
of €200 together with a broker fee of €6 per transaction (this is the fee that
I pay at my broker Lynx). This time, the portfolio without the REIT ends up on
top, albeit slightly, reflecting the impact of broker fees.

||Net asset value|Compound annual growth rate|Sharpe ratio|
|--- |--- |--- |--- |
|Yoran's Portfolio|€227,369|3.80%|0.96|
|Yoran's Portfolio (without REIT)|€233,059|3.88%|0.96|

{{< figure src="/images/comparison--yoran-portfolio-reit-recurrent.svg" caption="Comparison of monthly investments of €200 with a €6 transaction fee between my portfolio that includes the REIT fund and that excludes the REIT fund (source: [Backtest](https://backtest.curvo.eu/compare?config=%7B%22investmentPatterns%22%3A%5B%5B%22recurrent%22%2C1%2C200%5D%5D%2C%22transactionFee%22%3A6%7D&portfolios=NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQAYBmAdgA4mBGNu10mgOnYF0yIAJIBRGjQBCAFgoBWMAE4mdbjwBsdQaDETJAFQBSAJQCyaOnLWttIaq2mMa7FUzU1F-L0A%2CNoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhQAoB3AzACwgFdMUAlAUQEkAVAShABphQAMgFUADAGYA7AA4pARjljZvEQDp5AXT4hWzESIBCAFgEBWMAE4pY5SokAmTaB1797AFKMAsmjEmbI80Cg4JCpdXCgA))" >}}

## Verdict: drop the REIT fund
Taking all the pros and cons into consideration, I decided to **drop the REIT
fund from my portfolio**.

Academic research has shown that the real estate sector isn't as much as a
distinct asset class as previously thought. Assuming this, overweighting a
specific sector contradicts the basic principle underlying passive investing:
the markets price assets efficiently. I don't know much about my local real
estate market, let alone the global sector. So I can't claim to have an edge
over everyone else. Therefore, I have no basis to claim that the real estate
sector is under-priced and that I should overweight it as a consequence.

Furthermore, historical analysis shows that, when taking into account
transaction fees, there has been no difference in the returns and risk of my
portfolio with or without a REIT fund over the last 30 years. Of course, past
performance doesn't say anything about the future, but I feel reassured in my
decision being founded by academic research.

And in the end, I just love a **simpler portfolio**.

## Updated portfolio
After removing the REIT fund from my portfolio, I have 9% to allocate, which I
am going to put into the MSCI World fund. The resulting portfolio is shown
below. We're down to 3 funds!

| ETF                                                                                                 | Type        | Allocation 
|-----------------------------------------------------------------------------------------------------|-------------|------------
| [Xtrackers Global Government Bond EUR Hedged](https://www.justetf.com/en/etf-profile.html?isin=LU0378818131) | Bonds   | 18%
| [iShares Core MSCI World](https://www.justetf.com/en/etf-profile.html?isin=IE00B4L5Y983)            | Stocks      | 72%        
| [Xtrackers MSCI Emerging Markets](https://www.justetf.com/en/etf-profile.html?isin=IE00BTJRMP35)    | Stocks      | 10%        

[^1]: View on the [Amundi website](https://www.amundietf.fr/professional/product/view/LU1437018838)
[^2]: From the [factsheet of FTSE EPRA/NAREIT Developed](/documents/factsheet--ftse-epra-nareit-developed.pdf)
[^3]: From the [factsheet of MSCI World](/documents/factsheet--msci-world.pdf)
[^4]: From the [factsheet of MSCI Emerging Markets](/documents/factsheet--msci-emerging-markets.pdf)
[^5]: [MSCI Constituents](https://www.msci.com/constituents)
[^6]: [Real Estate Betas and the Implications for Asset Allocation](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3134732), mentioned by Ben Felix in [Real Estate Investment Trusts (REITs)](https://www.youtube.com/watch?v=IzK5x3LlsUU)
[^7]: [Are REITs a Distinct Asset Class?](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=2965146) by Jared Kizer and Sean Grover, mentioned by Ben Felix in [Real Estate Investment Trusts (REITs)](https://www.youtube.com/watch?v=IzK5x3LlsUU)
