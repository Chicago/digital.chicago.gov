---
id: 42278
title: Chicago Taxi Data Released
date: 2016-11-16T13:13:14-06:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=42278
permalink: /index.php/chicago-taxi-data-released/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/11/IMG_20161102_13435701.jpg
categories:
  - Default
  - Feature
tags:
  - data portal
  - Economic and Business Development
  - Open Data
  - open data portal
  - Streets and Transportation
  - Taxi
---
Chicago residents and visitors [took more than 27 million taxi rides](https://data.cityofchicago.org/Transportation/Taxi-Trips-Dashboard/spcw-brbq) in 2015, traveling 83 million miles and spending more than $400 million.

The City of Chicago assures the quality and safety of those rides through its <a href="https://www.cityofchicago.org/city/en/depts/bacp/provdrs/vehic.html" target="_blank">Department of Business Affairs & Consumer Protection</a> (BACP).  We have long published the taxi <a href="https://data.cityofchicago.org/d/97wa-y6ff" target="_blank">drivers</a> and <a href="https://data.cityofchicago.org/d/tfm3-3j95" target="_blank">vehicles</a> licensed by BACP on the Chicago Data Portal.

As part of its mission, BACP is also authorized to collect information on taxi rides, themselves.  It does so through periodic reporting by two major payment processors believed to cover most taxis in Chicago.  Based on these reports, we are now able to provide a dataset of over 100 million Chicago taxi <a href="https://data.cityofchicago.org/d/spcw-brbq" target="_blank">rides</a>, dating back to 2013.

<div id="attachment_42328" style="width: 944px" class="wp-caption aligncenter">
  <a href="https://data.cityofchicago.org/d/spcw-brbq"><img aria-describedby="caption-attachment-42328" loading="lazy" class="wp-image-42328 size-full" src="http://digital.cityofchicago.org/wp-content/uploads/2016/11/Trips_By_Month.png" alt="Chart of rides per month" width="934" height="276" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/11/Trips_By_Month.png 934w, https://digital.cityofchicago.org/wp-content/uploads/2016/11/Trips_By_Month-300x89.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/11/Trips_By_Month-768x227.png 768w" sizes="(max-width: 934px) 100vw, 934px" /></a>
  
  <p id="caption-attachment-42328" class="wp-caption-text">
    Rides Per Month
  </p>
</div>

<!--more-->

## What is included?

Each row in the dataset describes a distinct taxi trip and shows:

  * Which taxi provided the trip
  * What times the trip started and ended
  * Length of the trip in both time and distance
  * Starting and ending <a href="https://data.cityofchicago.org/d/cauq-8yn6" target="_blank">Community Area</a> — plus <a href="https://data.cityofchicago.org/d/5jrd-6zik" target="_blank">Census Tract</a> for many trips
  * Fare amount and other components of the trip cost
  * Type of payment — such as cash or credit card.  (As an important note, cash tips are not included in the data because they do not go through the payment systems.)
  * Taxi company

## What about privacy?

Although taxi rides take place on the public streets and can be freely observed, we realized from the start that there could be privacy issues in publishing them.  We took this issue very seriously and implemented a number of measures to preserve privacy while not unduly hampering use of the data.  These measures include the following.

#### Delay

Taxi trips are not reported in real time.  Each trip appears long after the completion of the ride.  Therefore, the dataset cannot be used to track trips in motion or even just-completed trips.  By the nature of how the data are collected, reported, and processed, a minimum of a few days will pass between completion of a ride and its appearance in the dataset.  More typically, the delay will be anywhere from a week to a month.

#### Masking of Taxi Medallion Number

Each licensed Chicago taxi has a license number, indicated by the Illinois license plate number, a painted number on the body of the taxi, and the medallion on the taxi&#8217;s hood.  The Taxi ID in this dataset is not that license number.  It is created specifically for this dataset, with no external meaning, to allow users to determine rides provided by the _same_ taxi but not _which_ taxi.

#### Masking of Time

We anticipate that analysis of taxi trips by time will be a major use of this dataset and we hope will add significant value for understanding the taxi industry and travel in Chicago.  However, there is minimal value and some potential privacy cost in making it possible to find a specific trip that someone knows departed at 10:13 am.  To balance these issues, we have rounded all start and end times to the nearest 15 minutes.

#### Masking of Location

From where and to where people travel is, of course, the most basic information about taxi trips and expected to be the topic of much analysis.  However, as with exact time, exact location down to the street address could affect privacy.  Therefore, we provide location only at the Census Tract and Community Area levels.

Since some Census Tracts have relatively infrequent taxi trips, we show the Census Tracts of a trip only if both the starting and ending Census Tracts had at least three trips in the relevant 15-minute time period.  Because of this rule, about 1/4 of Census Tracts that would otherwise be shown are blank.  (Others are blank because of missing data or falling outside Chicago.)

## What else have we changed?

Our usual approaches to open data are &#8220;you see what we see&#8221; and &#8220;open data can be messy data.&#8221;  We generally lean against cleaning up data before publication to the Data Portal.  However, with over 100 million rows of data, collected from a variety of hardware and software under real-world conditions, we found that some values not only were plainly implausible or impossible but also affected such things as averages and data visualizations to unreasonable degrees.  Therefore, we have applied the following corrections to the data.

  * Trip times less than zero or greater than 86,400 seconds are removed.
  * Trip lengths less than zero or greater than 3,500 miles are removed.
  * If any component of the trip cost is less than $0 or greater than $10,000, _all_ components of the trip cost are removed.

A time of 86,400 seconds is one day. Even making generous assumptions about breaks for rest, a trip longer than that pushes against City of Chicago limits on maximum working time for taxi drivers.

A distance of 3,500 miles happens to be about the furthest from Chicago one can drive and end within the United States.

[<img loading="lazy" class="alignnone wp-image-42299" src="http://digital.cityofchicago.org/wp-content/uploads/2016/10/Maximum_Distance-1-1024x454.png" alt="Google map image showing approximate driving distance from Chicago to the tip of the Alaska Peninsula" width="600" height="266" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/10/Maximum_Distance-1-1024x454.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/Maximum_Distance-1-300x133.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/Maximum_Distance-1-768x341.png 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/Maximum_Distance-1.png 1487w" sizes="(max-width: 600px) 100vw, 600px" />](https://www.google.com/maps)

In the case of trip costs, $10,000 likely is very high but happens to be a break point in the scaling of charts on our dashboard and the next break point down, $1,000, is not necessarily implausible for rare trips.

Naturally, many of the extreme values that remain likely are also wrong but we prefer to leave it to the user to filter further, based on his or her judgement and needs for a particular use of the data.

Finally, we determined that we likely have duplicate trips and have de-duplicated a bit (currently about 0.45% of records).  Again, being conservative about removing data, we call records duplicates only if they have identical values for:

  * Taxi ID
  * Trip Start and End Timestamps
  * Trip Seconds
  * Trip Miles
  * Pickup and Dropoff Census Tracts (after blanking out for privacy, if necessary)
  * Pickup and Dropoff Community Areas

## Enjoy

We hope residents of Chicago, researchers, and others find the taxi trip data useful.  We do realize that at 100 million rows and growing, the dataset speed, particularly the classic rows and columns [view](https://data.cityofchicago.org/d/wrvz-psew), may not always be as fast as for other datasets.  As always, and especially with a dataset of this size and complexity, we welcome questions, comments, suggestions for improvements, and any other feedback to <a href="mailto:dataportal@cityofchicago.org" target="_blank">dataportal@cityofchicago.org</a> or <a href="https://twitter.com/ChicagoCDO" target="_blank">@ChicagoCDO</a>.