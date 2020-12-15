---
id: 41997
title: An Open Data Gift for Chicago Bike Week
date: 2016-06-14T13:36:19-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41997
permalink: /index.php/an-open-data-gift-for-chicago-bike-week/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/06/9041137405_294b1972e3_h.jpg
categories:
  - Feature
tags:
  - Divvy
  - Open Data
  - open data portal
---
Happy [Chicago Bike Week](http://bikecommuterchallenge.org/)! Chicago has over 200 miles of on-street protect, buffered, and shared bike lanes and over 13,000 bike racks. Chicago also has [DIVVY](https://www.divvybikes.com/), a bike-sharing program with 480 docking stations across Chicago and is the largest bike-share program in North American in terms of geography covered. With 3.2 million trips in 2015 alone, DIVVY bikes are a sizable portion of bicyclists who get to work, run errands, and get around Chicago using their bicycle.

<div id="attachment_42004" style="width: 1034px" class="wp-caption aligncenter">
  <a href="https://data.cityofchicago.org/Transportation/Divvy-Trips-Data-Lens/u94x-unre"><img aria-describedby="caption-attachment-42004" loading="lazy" class="size-large wp-image-42004" src="http://digital.cityofchicago.org/wp-content/uploads/2016/06/Capture-1024x481.png" alt="DIVVY Trips dashboard" width="1024" height="481" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/06/Capture-1024x481.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2016/06/Capture-300x141.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/06/Capture-768x361.png 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/06/Capture.png 1625w" sizes="(max-width: 1024px) 100vw, 1024px" /></a>
  
  <p id="caption-attachment-42004" class="wp-caption-text">
    DIVVY Trips dashboard
  </p>
</div>

Today, we&#8217;ve rolled-out some massive data sets for the data savvy to explore DIVVY. First, we have released the [history of bike availability at DIVVY docking stations](https://data.cityofchicago.org/dataset/Divvy-Bicycle-Stations-Historical/eq45-8inv) for the past three years. DIVVY users will know that sometimes bikes cannot be found at a DIVVY station and other times a station can be full of bikes. This data set contains the history of each station availability for every 10 minutes over the past 3 years. By leveraging the portal, you can get see each time a station was [full](https://data.cityofchicago.org/resource/eq45-8inv.json?$where=percent_full=100) and each time a station was [empty](https://data.cityofchicago.org/resource/eq45-8inv.json?$where=percent_full=0).

This is a massive data set with over 52 million rows at the time of writing, but useful to others. For instance, this data set allows others to figure out when a bike station might be full or empty, helping the city optimize the allocation of bikes. This data was collected from [DIVVY&#8217;s API](http://www.divvybikes.com/stations/json). However, because of occasional glitches, there may be some gaps in the data. We will be filling-in any noticed gaps and if you notice any issues, feel free to [contact us](mailto:dataportal@cityofchicago.org).

Second, we&#8217;ve released [DIVVY bicycle trips](https://data.cityofchicago.org/Transportation/Divvy-Trips/fg6s-gzvg) on the data portal from 2013 through 2015. This data has always [been available](https://www.divvybikes.com/data) as a bulk download, but this centralizes it in the data portal, allowing you to leverage the [data portal APIs](https://dev.socrata.com/consumers/getting-started.html) and [filtering](https://dev.socrata.com/docs/queries/), such as [this command](https://data.cityofchicago.org/resource/fg6s-gzvg.json?$where=from_station_id%20=%2790%27) to only show trips originating from the Millennium Park bike station. There are 6.4 million trips at the time of writing, so we&#8217;re excited to see what everyone will be able to do with DIVVY data powered by an API.

These data sets give you some interesting insight into the short, but successful history behind the DIVVY program. Don&#8217;t forget, we also have the list of [current DIVVY stations](https://data.cityofchicago.org/Transportation/Divvy-Bicycle-Stations/bbyy-e7gq) if you just want to be in the know.

_Feature image is &#8220;[First Divvy bike share station opens in Daley Plaza](https://www.flickr.com/photos/chicagopublicradio/9041137405/)&#8220;, copyright WBEZ 2013 and licensed under [Creative Commons Attribution-NonCommercial 2.0 Generic (CC BY-NC 2.0)](https://creativecommons.org/licenses/by-nc/2.0/)._