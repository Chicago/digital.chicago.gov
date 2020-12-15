---
id: 41682
title: 'Summertime Data: Four new datasets launched on open data portal'
date: 2014-07-16T22:19:10-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41682
permalink: /index.php/summertime-data-four-new-datasets-launched-on-open-data-portal/
image: https://digital.cityofchicago.org/wp-content/uploads/2014/07/Ohio_street_beach1.jpg
categories:
  - Default
  - Feature
tags:
  - broadband challenge
  - chicago beaches
  - data
  - Open Data
---
The City of Chicago has released a handful of new datasets which pertain to several parts of daily life in Chicago. The public will be able to explore the [water quality at Chicago beaches](https://data.cityofchicago.org/Parks-Recreation/Beach-Water-Quality-Automated-Sensors/qmqz-2xku), [find who and which vehicles are licensed to carry passengers](https://data.cityofchicago.org/Community-Economic-Development/Public-Chauffeurs/97wa-y6ff), activities for Chicago&#8217;s [Micro-Market Recovery Program](https://data.cityofchicago.org/browse?q=micro-market%20recovery&sortBy=relevance), and the geographic areas targeted by the [City&#8217;s Broadband Innovation Challenge](https://data.cityofchicago.org/Community-Economic-Development/Broadband-Innovation-Zones/jkfs-hwcr).

## Sensors at Chicago&#8217;s Beaches

Chicago Parks District maintains automated sensors that report water data at the city&#8217;s beaches, including water temperature, water clarity (turbidity), and wave height&#8211;the same information  [  
](http://digital.cityofchicago.org/wp-content/uploads/2014/07/7768005582_33f40559a0_k.jpg) The new dataset provides current and historical information from sensors starting during the 2014 swimming season. The graph below the break shows water temperatures every hour for each Chicago beach from Memory Day 2014 until present.

<!--more-->

<div>
  <p>
    <a href="http://www.socrata.com/" target="_blank">Powered by Socrata</a>
  </p>
</div>

These sensors will go offline during the winter, but the data will remain and be active each summer.

## Public Chauffeurs, Vehicles, and Pedicabs

Every day, licensed chauffeurs carry Chicago residents in taxis, limousines, and even horse-drawn carriages and pedicabs. Each driver is licensed by the City of Chicago&#8217;s Department of Business Affairs and Consumer Protection (BACP). Now, a dataset on the portal shows the licensed chauffeurs in the city and the vehicles authorized to carry passengers.

The [public chauffeurs dataset](https://data.cityofchicago.org/Community-Economic-Development/Public-Chauffeurs/97wa-y6ff) lists which drivers have applied for a chauffeurs permit to operate ambulances, horse-drawn carriages, pedicabs, taxis, and livery vehicles (e.g., limos).

Meanwhile, [public passenger vehicle licenses](https://data.cityofchicago.org/Community-Economic-Development/Public-Passenger-Vehicle-Licenses/tfm3-3j95) show which vehicles are authorized to carry passengers. The make, model, and year of vehicle is shown, including the vehicle color and type of fuel the vehicle uses. The graph below shows the most popular model for taxi cabs with an active license.

<div>
  <a href="http://www.socrata.com/" target="_blank">Powered by Socrata</a>
</div>

Additionally, the data also shows if the vehicle is wheelchair accessible, the name of the company which owns the vehicle and their address is also available through this dataset.

Finally, the dataset also includes permits recently issued by BACP in response to a new city ordinance. Individuals who applied to pedicab licenses are displays alongside other public chauffeur applicants. Want to just view pedicab permits?

## Micro-Market Recovery Program

The portal contains several datasets on the Micro-Market Recovery Program ([http://www.cityofchicago.org/city/en/depts/dcd/supp\_info/micro\_market_recoveryprogram.html](http://www.cityofchicago.org/city/en/depts/dcd/supp_info/micro_market_recoveryprogram.html)) in the City of Chicago. The city has identified several MMRP zones to provide real estate purchasing assistance to stabilize the local housing market. Community development organizers work to provide residents the ability to buy vacant or abandoned properties from absentee landowners and banks to revitalize neighborhoods.

The MMRP data consists of five different datasets covering [addresses](https://data.cityofchicago.org/Community-Economic-Development/Micro-Market-Recovery-Program-Addresses/cf2f-mmzv), [building permits](https://data.cityofchicago.org/Community-Economic-Development/Micro-Market-Recovery-Program-Permits/4dpw-9rts), [cases](https://data.cityofchicago.org/Community-Economic-Development/Micro-Market-Recovery-Program-Cases/gm9b-bwv5), and [violations and inspections](https://data.cityofchicago.org/Community-Economic-Development/Micro-Market-Recovery-Program-Violations-and-Inspe/ujwc-724r) of properties within MMRP zone. A [map](https://data.cityofchicago.org/Community-Economic-Development/Boundaries-Micro-Market-Recovery-Program-Zones/np6m-dynq) of the boundaries for each MMRP zone is also available.

Need to link data, for instance, matching violations with cases? You can join the data using the address\_key or address\_grouping_key fields.  Below is a diagram showing the relationship between these tables.

<div id="attachment_41694" style="width: 480px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2014/07/MMRP-ERM.png"><img aria-describedby="caption-attachment-41694" loading="lazy" class=" wp-image-41694 " alt="MMRP ER Model" src="http://digital.cityofchicago.org/wp-content/uploads/2014/07/MMRP-ERM-783x1024.png" width="470" height="614" srcset="https://digital.cityofchicago.org/wp-content/uploads/2014/07/MMRP-ERM-783x1024.png 783w, https://digital.cityofchicago.org/wp-content/uploads/2014/07/MMRP-ERM-229x300.png 229w, https://digital.cityofchicago.org/wp-content/uploads/2014/07/MMRP-ERM.png 950w" sizes="(max-width: 470px) 100vw, 470px" /></a>
  
  <p id="caption-attachment-41694" class="wp-caption-text">
    An entity-relationship model showing address_key and address_grouping_key used across the MMRP datasets.
  </p>
</div>

## Broadband Innovation Zones

Last year, the City released a request-for-qualifications for companies to build gigabit or near-gigabit broadband in designated innovation zones at affordable prices. We&#8217;ve posted a machine-readable, [GIS map](https://data.cityofchicago.org/Community-Economic-Development/Broadband-Innovation-Zones/jkfs-hwcr) on the broadband innovation zones. Maps can be explored within your browser, so you won&#8217;t need to use special GIS software to view the innovation zones.

<div>
  <a href="http://www.socrata.com/" target="_blank">Powered by Socrata</a>
</div>

## Stay in the loop

Keep tabs on technical updates with the portal at our new [status blog](http://chicagoportalstatus.tumblr.com/). You can keep in touch with the open data team through [@ChicagoCDO](http://www.twitter.com/ChicagoCDO) or dataportal@cityofchicago.org.