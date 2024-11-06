---
layout: essay
type: essay
title: "Final Project Idea"
date: 2024-11-04
labels:
  - Software Engineering
  - Nextjs
---

# Project: Menstrual Tracker and Statistics Aggregator **Authors**: Amanda
Eckardt, Joshua Samonte, Chansen Tano, Elwais Golbuu

## Overview

*The problem*: Many menstrual trackers rigidly assume 28-day cycles and fail to
account for outliers and reproductive diseases that impact menstrual cycles.
Additionally, the great variability of menstrual cycles make tracking
individuals wonder whether their cycles conform to what most in their region
experience or not.

*The solution*: We propose creating a menstrual tracker that uses a modified
prediction algorithm that allows for more flexible tracking than that
encompasses more than the generalized 28 day menstrual cycle. Additionally,
information entered will be processed to generate aggregate statistics with
which individuals can use to assess how "normal" their periods are.

## Approach

Upon accessing the website the user is present with aggregate statistics of
women cycle and symptoms. The user may create an account using an email,
password, and additional information --- some essential, some optional --- which
will be used in aggregate statistics. Once logged in, the user may enter and
track periods along with symptoms. Upon updating their periods, the user will be
given their personal statistics immediately. Prediction will improve with
repeated usage. Additionally, entered data is sent to a database which
aggregates all users statistics and averages once per day.

## Use case ideas

Users will have more tailored, flexible, and accurate predictions and
information regarding their cycles. Users will also understand how their cycles
relate to other individuals using the app, which will largely be people
affiliated with UH Manoa.

## Beyond the basics

After implementing the basic functionality, here are ideas for more advanced
features:

+ Expanding aggregation of statistics beyond UH Manoa
+ Accounting for diversity amongst all menstruating individuals.
+ Offer more than one predictive model based on users essential information.
+ Expose an API for people to enter and access anonymous data from consenting
users.
