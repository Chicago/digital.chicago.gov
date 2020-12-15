---
id: 40552
title: Release All the Data
date: 2013-04-01T22:17:34-05:00
author: ankurthakkar
layout: post
guid: http://digital.cityofchicago.org/?p=40552
permalink: /index.php/release-all-the-data/
image: https://digital.cityofchicago.org/wp-content/uploads/2013/04/cottagegrove.jpg
categories:
  - Feature
tags:
  - Data Science
  - Open Data
  - Streets and Transportation
  - Technology and Innovation
---
[Last December](http://digital.cityofchicago.org/index.php/21-new-open-data-releases/), we released [current](https://data.cityofchicago.org/Transportation/Chicago-Traffic-Tracker-Congestion-Estimates-by-Re/t2qc-9pjd) [traffic](https://data.cityofchicago.org/Transportation/Chicago-Traffic-Tracker-Congestion-Estimates-by-Se/n4j6-wkkf) congestion estimates and received a tremendous amount of feedback along the lines of, “Sweet! But can we have more data?”

<p align="center">
  <img loading="lazy" class="aligncenter" alt="" src="http://media.tumblr.com/03488d2d9d2b4e3d5812431037d0bcc6/tumblr_inline_mjwg1n1WC91qz4rgp.gif" width="400" height="157" />
</p>

We released almost 9 million new rows of data across two new datasets: The historical archive is available for each region and segment of Chicago’s streets. Each archive displays the estimated speed of traffic on Chicago’s roads based on the bus traffic around the city. Historical traffic [data by region](https://data.cityofchicago.org/Transportation/Chicago-Traffic-Tracker-Historical-Congestion-Esti/emtn-qqdi) will be available from March 2007 and [segment data](https://data.cityofchicago.org/Transportation/Chicago-Traffic-Tracker-Historical-Congestion-Esti/77hq-huss)—which reflects much smaller portions of roads—is available from August 2011. The archives will be regularly updated for a complete history. The current traffic tracker dataset will remain in its current location and be refreshed every 10 minutes.

The historical traffic tracker data is now the largest dataset on the portal and was launched with Socrata’s [API Foundry](http://www.socrata.com/api-foundry/). The API is faster and allows users to interact with data using a SQL-style query language. This implementation helps guarantee users can quickly browse millions of rows of data for app-development and analysis. Here&#8217;s <a title="Segment" href="https://data.cityofchicago.org/developers/docs/historical-traffic-congestion-segments?" target="_blank">documentation</a> on the segment data.

[<img loading="lazy" class="aligncenter  wp-image-40553" alt="all of the data" src="http://digital.cityofchicago.org/wp-content/uploads/2013/04/all-of-the-data.png" width="373" height="271" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/04/all-of-the-data.png 622w, https://digital.cityofchicago.org/wp-content/uploads/2013/04/all-of-the-data-300x217.png 300w" sizes="(max-width: 373px) 100vw, 373px" />](http://digital.cityofchicago.org/wp-content/uploads/2013/04/all-of-the-data.png)