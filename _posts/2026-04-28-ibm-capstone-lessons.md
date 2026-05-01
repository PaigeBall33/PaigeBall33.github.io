---
layout: post
title: "What completing the IBM Data Analytics Capstone actually taught me"
date: 2026-04-28
categories: [Data Analytics, Learning]
tags: [IBM, Python, SQL, capstone, data analytics]
description: Six modules, 65,000 respondents, and more pandas errors than I care to admit. Here is what the capstone actually felt like from the inside.
---

I finished the IBM Data Analytics Professional Certificate capstone while working full time on a cattle ranch in rural Alberta. That context matters, because the capstone is not a weekend project. It is eleven courses worth of skills applied to one real dataset — the Stack Overflow Developer Survey — across six modules that each build directly on the last.

What follows is what I actually learned, which is not the same list as what the course says you will learn.

## The data is never what you think it is

Module 1 felt straightforward on paper: pull data from an API, scrape some web pages, load a CSV. I connected to a job postings endpoint with 27,005 records and built functions to count postings by skill and location. Manageable.

Then I loaded the Stack Overflow survey. Sixty-five thousand rows, 117 columns, and the first column I tried to analyze — age — was stored as text strings like "25-34 years old." Not numbers. Strings.

That was the moment I understood that real data analysis begins before you touch a single statistical function. I spent more time writing regex to extract numeric midpoints from text ranges than I spent on the actual age analysis itself. Handling edge cases like "Under 18 years old" and "65 years or older" required decisions that weren't in any rubric.

The lesson is straightforward but takes experience to internalize: assume nothing about how your data is stored, and verify every column's format before building anything on top of it.

## Cleaning data is where analysis is won or lost

Module 2 was data wrangling, and it was the most humbling part of the project. The dataset had 20 fully duplicate rows and 109 out of 114 columns with at least some missing data. The compensation column — ConvertedCompYearly — was missing for 42,002 respondents. That is 64% of the dataset.

Every cleaning decision I made in that module shaped every finding that followed. Imputing missing compensation values with the median ($65,000) was a deliberate methodological choice, not a default. Removing duplicates based on five demographic columns reduced the dataset from 65,457 rows to 4,748 — a reduction that required justification, not just execution.

What nobody tells you about data cleaning is that it demands judgment, not just technical skill. You have to decide what "good enough" looks like and document your reasoning at every step. I started keeping notes on each imputation decision, which felt excessive at the time and turned out to be essential in Module 6 when I had to defend my methodology in the final presentation.

## Outliers will break your analysis if you let them

Module 3 was exploratory data analysis, and the compensation column nearly derailed every visualization I attempted. The maximum value in the dataset was $16,256,600. The mean was $86,155. The median was $65,000.

The gap between that mean and median is the story. A small number of extreme earners were pulling the average well above where most developers actually land. Once I applied IQR-based outlier removal — capping the upper bound at $220,861 — the dataset dropped from 65,437 to 22,457 rows, and the resulting charts reflected the actual developer workforce rather than a distribution skewed by outliers.

The correlation findings were the most instructive part of this module. Work experience moderately predicts compensation (r = 0.407), which is intuitive. What surprised me was that salary has essentially no relationship with job satisfaction (r = −0.060). Compensation matters enough to get someone in the door, but it does not determine how they feel once they are there. That finding has stayed with me.

## Visualization is a communication decision, not a technical one

By Module 4 I had produced charts across nine labs: histograms, box plots, scatter plots, bubble plots, pie charts, stacked bars, line charts. I completed all of them.

The ones that actually communicated something were the ones built around a specific question. The compensation trend line by age group was legible because I removed outliers first and ordered the groups chronologically. The overlapping histograms comparing job satisfaction across experience levels worked because I kept the transparency low enough to show density without losing the individual distributions.

The charts that did not work were the ones I built to complete the exercise without first asking what question they were answering. A scatter plot of 65,000 semi-transparent data points communicates very little without a regression line. Adding that line took three lines of NumPy code and transformed the chart from decorative to informative.

The underlying principle: every design choice in a visualization is a communication choice. There is no neutral default.

## A dashboard is not a collection of charts

Module 5 was the Looker Studio dashboard. I built three tabs — current technology usage, future technology trends, and developer demographics — with twelve panels total.

The thing I had to unlearn was the instinct to show everything I knew. A dashboard is not evidence of effort. It is a tool for a specific audience to answer specific questions quickly. Every panel I added had to justify its presence by answering something a stakeholder would actually ask.

A small but instructive example: the null filter I applied to every panel excluded blank dimension entries from every chart. Without it, blank values appear as their own category and distort every proportion on screen. With it, the charts reflect actual respondent preferences. That single configuration decision is what separates an accurate dashboard from a misleading one, and it required no complex code — just awareness that the problem existed.

## The presentation is the actual deliverable

Everything in Modules 1 through 5 existed to support Module 6. The 17-section presentation was where I had to account for every methodological choice I had made and translate six modules of technical work into something a non-technical stakeholder could read and act on.

The discipline that helped most was pairing every finding with a concrete implication. Not just "Python is the most desired programming language" but "Python is the most desired programming language, which means professionals who prioritize it now are positioning ahead of where measurable job market demand is heading." The finding is interesting. The implication is useful. Only one of them drives a decision.

The appendix — a table mapping every lab to a plain-language description of what it produced — was the element that felt most like genuine professional work. Complete documentation so that someone else could reproduce the analysis. Not glamorous. Entirely necessary.

---

The capstone took longer than I anticipated and taught me more than the course description suggested it would. The technical skills are real and I use them regularly. But the more durable lesson was this: most of data analytics is making defensible decisions under uncertainty and communicating those decisions clearly to people who were not present when you made them.

That does not appear in any course module. It shows up in the work.
