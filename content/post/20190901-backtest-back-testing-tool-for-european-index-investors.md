---
title: "Backtest: the back-testing tool for European index investors"
date: 2019-09-01T14:09:32+02:00
slug: 'backtest-the-back-testing-tool-for-european-index-investors'
tags: ["Investing"]
---

I've written several articles on this blog for which I had to dive deeper into
the historical performance of my portfolio. Because I couldn't find an existing
tool that allowed me to do this, I wrote my own. Then, with every article, I
had to extend it a little bit and it slowly became better and better.

Finally, a couple of weeks ago, I wanted to see how different allocations of my
portfolio would impact its historical performance. For this, I needed to extend
the simulator so that I could easily compose a portfolio of ETFs and analyze
its past performance. That's when I realized that such a tool would be valuable
for any European index investor. After all, American investors can use
[Portfolio Visualizer](https://www.portfoliovisualizer.com/) but us, European
investors, are left in the cold.

I discussed the idea with my [Curvo](https://curvo.eu) co-founder Thomas and we
agreed that we should make the tool available to anyone. Then, after a weekend
of coding in July 2019, we released **[Backtest](https://backtest.curvo.eu/),
the back-testing tool for European index investors**.

{{< figure src="/images/backtest.gif" caption="Backtest in action" >}}

## What can you do with Backtest?
In short, Backtest lets you get more insight into portfolios that consist of
index funds. Some common use cases are:

* **Back-test your portfolio.** We have the official historical data for a lot of the popular ETFs and Backtest can run an analysis on the past performance of your portfolio. For example, take a look at the performance since 1981 of [Lars Kroijer's Rational portfolio](https://backtest.curvo.eu/portfolio/NoIgMghgTgzgBAaSgewJYCsCmUDk8BKEALqsgHYQA2cACslEQGbKWlwAUAssgCbbGYAlCAA0wUGACqARgDsADmkBWACzS5ATlEAGAHRKAumPCTtAZgWLFZ6Tv0GHQA).
* **Share your portfolio.** Want to show someone your portfolio? Just send them [the link](https://backtest.curvo.eu/portfolio/NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA)! No sign-up or login is required. All the information about the portfolio is embedded in the link.
* **Compare different allocations of the same portfolio.** How would your return change if you added more weight to the fixed-income portion of your portfolio? You can answer these questions with the comparator on Backtest. See for example a [comparison of three allocations of the same portfolio](https://backtest.curvo.eu/compare?portfolios=NoIgMghgTgzgBAaSgewJYCsCmUDk8BKEALqsgHYQA2cACslEQGbKWlwAUAggObdSYwYqAG6YAlCAA0wUGACqARgDsADgUBWACwLlATikAGAHQqAutPByDAZlVq11hYaMAmU%2B6A%2CNoIgMghgTgzgBAaSgewJYCsCmUDk8BKEALqsgHYQA2cACslEQGbKWlwAUAwuTNgG7FUfTAEoQAGmCgwAVQCMAdgAccgKwAWOYoCcEgAwA6AEwBdSeBl6AzMpUqrc-QaUnXQA%2CNoIgMghgTgzgBAaSgewJYCsCmUDk8BKEALqsgHYQA2cACslEQGbKWlwAUAssgCbbGYAlCAA0wUGACqARgDsADmkBWACzS5ATlEAGAHRKAumPCTtAZgWLFZ6Tv0GHQA).
* **Share a comparison.** Do you want to show off how your portfolio is so much better than someone else's? Just send them the link to the [comparison](https://backtest.curvo.eu/compare?portfolios=NoIgmg9gTghgdgcgM4AIAK0AuAzCAbASwhABphQAZAVQEYAWAZgHYAGGgDnYfdJYDoWATgC6ZEAEkAoixYAhAGJ0ASvIASDGrz71RoKTNl0KAVjCCuWuiLHUWzThxoatHXROlyAKgCklAWTQGYxdhUKA%2CNoIgMghgTgzgBAaSgewJYCsCmUDk8BKEALqsgHYQA2cACslEQGbKWlwAUAggObdSYwYqAG6YAlCAA0wUGACqARgDsADgUBWACwLlATikAGAHQqAutPByDAZlVq11hYaMAmU%2B6A).

## Where do I want to take Backtest?
**I want Backtest to become the best back-testing tool for European investors.**
At this point, even though the core functionality is there, it's still very much a
work in progress. For instance, there are a few features from [Portfolio Visualizer](https://www.portfoliovisualizer.com/) that I would like to
implement for Backtest, such as the portfolio optimization toolset.

Also, I really like how some of the visualizations on [Portfolio Charts](https://portfoliocharts.com/charts/) offer a complementary perspective on a
portfolio. In many cases, a great chart carries much more information than a
table or text. Visualization is an area where I want Backtest to excel at.

And of course, more ETFs and indexes need to be added. At the time of writing,
Backtest supports 255 ETFs but there are many more out there that investors
have in their portfolios.

For these reasons, I am still [actively improving Backtest](https://backtest.curvo.eu/updates). But I need your help to do it.

## I need your feedback and comments
Since I first released Backtest, I've received many emails and comments on Reddit
from people with feedback and asks to add funds that are missing. I want to
thank all these people because their feedback:

1. Tells me that Backtest is useful. After all, they care enough about it to go
   through the bother of sending an email.
2. Helps me guide the development. I know which funds need to be added, and I
   know better what features people are missing.
3. Gives me the motivation to continue to work on it!

Therefore, **I need your feedback too!** So try out the tool, and let me know
what you think by emailing me at [yoran.brondsema@gmail.com](mailto:yoran.brondsema@gmail.com).
