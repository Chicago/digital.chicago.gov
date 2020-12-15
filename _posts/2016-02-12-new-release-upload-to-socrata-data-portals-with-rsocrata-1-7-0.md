---
id: 41895
title: 'New release: Upload to Socrata data portals with RSocrata 1.7.0'
date: 2016-02-12T00:06:33-06:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41895
permalink: /index.php/new-release-upload-to-socrata-data-portals-with-rsocrata-1-7-0/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/01/67187558_5643ef917a_o.jpg
categories:
  - Feature
tags:
  - Open Source
  - R
  - RSocrata
  - rstats
  - Socrata
---
We&#8217;ve released a new version of [RSocrata](https://cran.r-project.org/web/packages/RSocrata/index.html) with two new, big features. You can now upload data to Socrata using the new “write.socrata()” function. If you have a dataframe ready to go in R, and you’ve already setup a corresponding schema in Socrata, you can use your Socrata credentials to upload the data directly from R. This is a superb addition if you want to use R to upload datasets to your data portal. Our team has used our own [ETL framework](http://digital.cityofchicago.org/index.php/open-data-etl-utility-kit-version-1-2-0-now-available/) to work with our portal, but others may feel more comfortable using R to do the same thing.

[<img loading="lazy" class="aligncenter size-full wp-image-41962" src="http://digital.cityofchicago.org/wp-content/uploads/2016/02/rsocrata.gif" alt="rsocrata" width="683" height="418" />](http://digital.cityofchicago.org/wp-content/uploads/2016/02/rsocrata.gif)

For instance, [Stuart Gano used the beta version](https://dev.socrata.com/consumers/examples/forecasting_with_rsocrata.html) to download calls for ambulances, create a statistical forecast of upcoming call volumes for upcoming months, and then use RSocrata to upload those estimates to a data portal.

<div>
  <a href="http://www.socrata.com/" target="_blank">Powered by Socrata</a>
</div>

Second, you can now download private, non-public data from Socrata portals. While Socrata is intended to publish public data, there is an option to keep data private. If you want to download that private data using the “read.socrata()” function, you may use your Socrata credentials to complete that task.

These are a couple of great features that were added by the open source community. There have been dozens of contributions to City of Chicago open source projects, which have helped our team and also helped others who use this software. Thanks to all of those who have contributed to this project, especially [John Malc](https://github.com/dmpe) and [Mark Silverberg](https://github.com/marks).

If you’re interested in other open source projects by the city, take a look at <http://chicago.github.io> for a list of active projects.

_Feature image modified from &#8220;[R Graffiti](https://www.flickr.com/photos/carbonnyc/67187558/)&#8221; by [David Goehring](https://www.flickr.com/photos/carbonnyc/) and licensed under [Creative Commons Attribution 2.0 Generic (CC BY 2.0)](https://creativecommons.org/licenses/by/2.0/)._