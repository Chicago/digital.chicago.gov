---
id: 41991
title: Is it safe to swim? A new tool to make better predictions for Chicagoans
date: 2016-06-20T13:16:31-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41991
permalink: /index.php/is-it-safe-to-swim-a-new-tool-to-make-better-predictions-for-chicagoans/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/06/14056727746_fd7cdd54c9_k.jpg
categories:
  - Default
  - Feature
tags:
  - Analytics
  - Chicago Park District
  - Open Data
  - open data portal
---
We are very excited that, this summer, the City of Chicago teamed-up with a team of volunteer data scientists to develop new statistical models to improve the accuracy of beach advisories due to the presence of _E. Coli_. Sean Thornton, a Program Advisor at Harvard University&#8217;s Ash Center, has a terrific article on the project:

> For Chicagoans, few things are as enjoyable as a day at the beach. That joy, however, is contingent on clean waters that are free of contaminants such as E. coli bacteria.  With the arrival of this year’s beach season, Chicago has built an analytical pilot model that will enhance its Park District’s regular beach water quality inspection process.  The model specifically aims to guide which beaches may need to close based on predicted E. Coli readings, which helps protect the public with advisories or closures as soon as possible.
> 
> This is not Chicago’s first municipal predictive analytics project; the city has had success with predictive models for rodent baiting operations and food establishment inspections, among others.  This model differs, however, because it wasn’t built by the City of Chicago at all, but by a team of volunteers from the city’s civic tech community.

This was both a fascinating and difficult question to deliver a better model. In fact, the team put together an ensemble model ranging from [logit regressions](https://en.wikipedia.org/wiki/Logistic_regression) to [gradient-boosting models](https://en.wikipedia.org/wiki/Gradient_boosting) to deliver improved performance. Each week, between 4 and 12 data scientists, statisticians, and researchers attempted to develop a model which can reduce the chance of children and Chicagoans getting sick from an enjoyable day at the beach.

Because the project is open source, you can find the [entire source code on GitHub](http://github.com/Chicago/e-coli-beach-predictions) to see if you can improve the work done by a group of civic technologists. Notes about the project can be found on the project&#8217;s [wiki page](https://github.com/Chicago/e-coli-beach-predictions/wiki), including detailed noted on the lab testing process and weekly updates on the teams findings.

The summer of 2016 is needed to compare performance. As with any statistical model, the team was concerned with &#8220;over-fitting&#8221;&#8211;where such effort is made to predict past events, that the model suffers when predicting things that truly happen in the future. This summer provides an excellent testing-ground for the new model, providing feedback on the predictive power of these new techniques.

## Open Data

Open data played a key role in enabling this project. For the past two years, Chicago Park District has [published](http://cpdbeaches.com) real-time information on the forecasts from the statistical model developed by the United States Geological Survey (USGS). Beginning this week, these results are now being [stored on the city&#8217;s open data portal](https://data.cityofchicago.org/Parks-Recreation/Beach-Swim-Advisories/t62e-8nvc).

To support this project, the Chicago Park District and City of Chicago also released the actual [results of the lab tests](https://data.cityofchicago.org/Parks-Recreation/Beach-Lab-Data/2ivx-z93u) on the portal as well. Over the course of this summer, the team of volunteer civic technologists, the City of Chicago, and Chicago Park District will be comparing the results of the existing USGS model to the new models to compare performance. Both the forecast data and the actual lab results will be used to show the performance of each model.

The above statistical models depend on hourly weather forecasts. For this, the team used the excellent weather models from [Forecast.io](http://forecast.io/) (which powers the popular Dark Sky apps). Updated weather information for each beach is available [here](https://s3.amazonaws.com/beach-ecoli-weather-data/hourly_weather_readings.csv).

## Teamwork

Of course, this project was not possible without the [team](https://github.com/Chicago/e-coli-beach-predictions/graphs/contributors) that volunteered their time on the project: [Matt,](https://github.com/mesweeney4) [Rebecca](https://github.com/beckeroobonsai), [Kevin](https://github.com/kbrose), [Melissa](https://github.com/mmcneill), [Scott](https://github.com/scottlittle), [David](https://github.com/DGalt), [Daniel](https://github.com/knowledgemonger), [Nick](https://github.com/nicklucius), [Scott](https://github.com/sbeslow), [Chris](https://github.com/ChrisProkop), and [Forest](https://github.com/fgregg). Well over 150 hours were dedicated to this project by a team who worked hard on helping improve our summers a little more.

_Featured image is __&#8220;[Simple Times](https://www.flickr.com/photos/christopherf/14056727746/in/photolist-nq9pqW-55spdy-hKU9zw-HnkUeU-huEbCq-c4rfdU-6E6b6t-ruDN9T-ampjZh-dTrnwK-dUF32Z-6yFNZR-2F1CG-5qwGAR-2F1zW-9gDBt2-o9sD1A-pjYazE-4Wg3SW-krDFBc-tEMBNk-f39q63-pn9yLw-cPBPhm-dDNtEq-5nYuiq-pmQAus-qqgUAV-5nwboc-5nUeFM-a6kZqP-fGzBSp-bVLeKd-6Pi4co-6gz4qg-93t4Pe-cEpPKE-9pPvuD-ddSRgB-c4rf11-c4rgdU-biRhGn-AjQR86-fGSc2Y-71BBKC-cPBN7W-ataXKE-obKAPA-pCGfwL-oUNP5V)&#8221; by [Christopher.F](https://www.flickr.com/photos/christopherf/), copyright 2014 and licensed under Creative Commons Attribution-NonCommercial-NoDerivs 2.0 Generic (CC BY-NC-ND 2.0)_