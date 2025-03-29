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

Suppose the average cost of a gallon of gas in Texas is $2.75. That __does not mean that every gallon of gas in Texas sells for that much__. 
