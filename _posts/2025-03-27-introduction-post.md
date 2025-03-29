---
title: Presentation of the Open Trade Project
date: 2025-03-27 10:00:00 -0800
categories: [Blogging]
tags: [introduction]
description: Understand our data-driven grading approach
---

## Welcome to the Open Trade Project!

I’ve always been interested in data analysis and how it applies to the roster building aspects of NFL teams, and draft season is one of my favorite parts of the year. The league is increasingly paying attention to data science, as evidenced by NFL Next Gen Stats and Pro Football Focus. The internet is full of mock drafts and projections and I wanted to contribute in some way.

Scouting prospects is a highly subjective process; each team has its own priorities and athletic requirements, and we'll never know what happens inside war rooms. I wanted to stay away from speculating and projecting players as much as possible. Eventually, I had an idea: how to reimagine the current NFL trade chart using modern data analysis techniques? The result is The Open Trade Project.

Over the past few months, I have gathered data for all NFL draft trades since 2002 (when the current format was established). I evaluated the trades using the classic Jimmy Johnson model and added uncertainty to the value of each pick using machine learning. I also developed an open, free-to-use [draft trade grader](https://huggingface.co/spaces/TheOpenTradeProject/Sample_Draft_Grader).

This post is an overview of the project. In the upcoming weeks, further posts will take a deep dive on specific aspects.

Trades for the 2025 NFL Draft will be graded live [here](https://x.com/TheOpenTrade/).

## The Jimmy Johnson trade chart

The Jimmy Johnson Trade Value Chart is a widely used tool in the NFL to assess the relative value of draft picks during trades. Created in the early 1990s by former Dallas Cowboys head coach Jimmy Johnson, the chart assigns a numerical value to each pick in the draft, with the highest values placed on early first-round selections and progressively lower values assigned to later picks. This straightforward scoring system helps teams evaluate whether a proposed trade involving draft picks is fair or advantageous. 

![The Jimmy Johnson Trade Value Chart](assets/img/JJtradechart.svg)
*Figure 1: The classic Jimmy Johnson Trade Value Chart, a staple in NFL draft trade analysis.*

NFL draft trades don't always reflect pick values according to the Jimmy Johnson model, leading to speculation about "winners or losers" for each trade, as well as the creation of new models which better describe more recent trades, such as the [Rich Hill model.](https://www.patspulpit.com/2018/4/21/17256758/2018-nfl-draft-value-chart-rich-hill). There is a common aspect in both models: each pick has a fixed value; for example, pick 21 is worth 800 points in the Jimmy Johnson chart. Suppose 3 hypothetical trades, where pick 21 sells for 780, 800 and 820 points. On average, pick 21 was transacted for 800 points. But how about the variance?

## No love for standard deviation?

Suppose the average cost of a gallon of gas in Texas is $2.75. That _does not mean that every gallon of gas in Texas sells for that much_. In fact, there is a variability of gas prices around the mean; that variability is called [standard deviation.](https://www.youtube.com/watch?v=MRqtXL2WX2M). Suppose that, in our example, the standard deviation is 10 cents. If the price distribution is normal, according to [the theory of normal distributions]([https://www.youtube.com/watch?v=MRqtXL2WX2M](https://en.wikipedia.org/wiki/Normal_distribution), 68% of the gallons of gas in Texas are sold for an amount between $2.65 and $2.85; 95% are sold for an amount between $2.55 and $2.95; and 99% are sold for an amount between $2.45 and $3.05. 

This example provides a valuable takeaway in terms of evaluating draft charts. Both options describe the value of picks __only in terms of a mean value__; in other words, the possibility of variation in the cost due to external circumstances is disregarded. In the real NFL draft, multiple factors affect the value of a pick, just like the cost of gas across different gas stations. It is clear that any redesign of the Jimmy Johnson model that does not take cost variability into account will not capture all the information that the available data on past trades has to offer.

## How to determine the cost variability for each pick?




