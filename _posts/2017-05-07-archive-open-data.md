---
id: 42457
title: 'Preserve Public Data with Chicago&#8217;s RSocrata'
date: 2017-05-07T09:43:53-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=42457
permalink: /index.php/archive-open-data/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/09/16323834751_809771f790_o.jpg
categories:
  - Default
  - Feature
tags:
  - Open Data
  - open data portal
  - RSocrata
---
Chicago has rolled-out a public test for a new feature designed to help scientists, journalists, archivists, and others to archive and preserve open data. In light of recent concerns about the [removal of government](https://sunlightfoundation.com/tracking-u-s-government-data-removed-from-the-internet-during-the-trump-administration/) data from public websites and data portals, particularly related to climate change, this new feature allows for data to be downloaded archived with a simple command in the R language.

All of the data, including maps, saved to your hard drive and time-stamped so you can easily see when the data was last preserved. The data are also compressed on your hard drive to to save space. In the near future, we will offer the ability to save data to the cloud to make it easier to save very large open data sets. Read the post on the city&#8217;s [developers blog](http://dev.cityofchicago.org/rsocrata/data%20portal/2017/05/07/new-export-socrata-feature.html) for instructions on installing and working with the the new features.

[RSocrata](https://github.com/Chicago/RSocrata) is available for the R programming language and data hosted on Socrata open data portals, which is the largest open data portal provider in the world and is the portal for hundreds of federal agencies, state governments, and cities.

Right now, this is a public test of the new feature and may have some bugs. We welcome feedback and encourage you to report any issues on our [bug tracker](https://github.com/Chicago/RSocrata/issues/126) or email <developers@cityofchicago.org>.

RSocrata was developed and released by the City of Chicago in 2013 as a free, open source program. It has allowed researchers and programmers who use R to easily retrieve individual datasets. The program has been used to [forecast ambulance and fire truck incidents](https://dev-socrata-com-455.surge.sh/consumers/examples/forecasting_with_rsocrata.html), used by the City of New Orleans to [generate performance reports](https://dev.socrata.com/blog/2016/07/29/rsocrata-etl-framework.html), and [mentioned](https://books.google.com/books?id=69VOCwAAQBAJ) in [books](https://books.google.com/books?id=NrddDgAAQBAJ) teaching the fundamentals of data science. It is also used by Chicago&#8217;s data team on a regular basis, ranging from uploading and refreshing the open data portal to [predicting food inspections](http://chicago.github.io/food-inspections-evaluation).

&nbsp;

_Featured image [&#8220;Open Data&#8221;](https://www.flickr.com/photos/descrier/16323834751/in/photolist-qStVmK-dq9qxc-aMi8gz-9Rk68o-9jMLxQ-8F9ojE-ddn815-ddn7sf-ddmZ9U-aNU6Hr-9jJGhi-9jMMjh-7Uasyy-9S93UL-fxK1x9-9S3Ybr-ddn5gb-9rnTdL-9S6SwT-9S9HdY-9S3XTT-9S6RaW-9S5Z5P-9S68qZ-9S3XEp-9S9GEh-9S64VV-9S9Fiy-9S8S1u-9S92xC-9S6S6b-9S9G1b-9S6RJ5-9S7mwJ-9S5Wu6-9S9JJ7-9S4pPi-9S5XTZ-9S9DYw-9S61fP-9S7m53-8Z9pht-ddn4Pj-9S62ok-9S8Xdj-hn2Jdr-9S9RmQ-9S9NLm-9S6KD2-7FfmwS/) Copyright (c) 2015 by Descrier_