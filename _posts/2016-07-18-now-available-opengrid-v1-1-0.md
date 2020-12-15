---
id: 42037
title: 'Now available: OpenGrid v1.1.0'
date: 2016-07-18T22:26:07-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=42037
permalink: /index.php/now-available-opengrid-v1-1-0/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates.png
categories:
  - Default
  - Feature
tags:
  - Open Source
  - OpenGrid
---
This week, the City released the newest version of [OpenGrid](http://www.opengrid.io),  [v1.1.0](https://github.com/Chicago/opengrid/releases/tag/v1.1.0) with a number of enhancements that is now available in the project repository and users of opengrid.io.

## Queries with Relative Dates

Now you can search and save queries where certain dates fall within relative date ranges.  A relative date range is a period of time that is relative to the current date.  OpenGrid supports the following relative date time periods:

  * Today
  * Yesterday
  * 1 minute ago, # minutes ago
  * 1 hour ago, # hours ago
  * 1 day ago, # days ago
  * 1 week ago, # weeks ago
  * 1 month ago, # months ago
  * 1 year ago, # years ago

For example, suppose you are a foodie and want to stay up-to-date on all of the hotspots that opened within the last week. You would select the Business Licenses Dataset, and set the License_description = “Retail Food Establishments.” Then apply another filter with the Issue Date between “1 week ago” and “today.”

<img loading="lazy" class="aligncenter size-large wp-image-42081" src="http://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates-1024x524.png" alt="relative-dates" width="1024" height="524" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates-1024x524.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates-300x154.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates-768x393.png 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/relative-dates.png 1137w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

For those using OpenGrid with user management, users can save queries with relative date. Running those queries at a later date will use the relative date, making it more useful for those who want to re-run queries within a moving time window.

## 

## Datasets alphabetized for easier discovery

Previously all of the datasets available in OpenGrid were not alphabetized, making the finding and selection of a dataset an arduous task.  Now you can view and access all of the datasets available to you in a more organized manner.

<img loading="lazy" class="aligncenter size-large wp-image-42079" src="http://digital.cityofchicago.org/wp-content/uploads/2016/07/sorted-dataset-1024x576.jpg" alt="sorted-dataset" width="1024" height="576" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/07/sorted-dataset-1024x576.jpg 1024w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/sorted-dataset-300x169.jpg 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/sorted-dataset-768x432.jpg 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/07/sorted-dataset.jpg 1920w" sizes="(max-width: 1024px) 100vw, 1024px" /> 

## **Improved Geospatial Filtering Performance on OpenGrid.io**

At times, users would notice that queries using geospatial filters would not always return all the results and may omit some data. This issue has been fixed, though, opengrid.io is still limited to a maximum of 1,000 results for the time being.

## **API support of geospatial filtering**

OpenGrid&#8217;s [API](http://opengrid.readthedocs.io/en/stable/OpenGrid%20API/) now supports geospatial filtering calls. Previous versions of OpenGrid would search for all data before &#8220;filtering&#8221; for specific geographies. As a result, queries were extraneous and took longer than necessary. Now, queries can be provided which will only search for data within a given geospatial parameter.

Opengrid.io displays a maximum of 1,000 research results.  Previously, when a user would try to maximize their search results for a particular area via application of a geo-spatial filter, the filtering was happening on top of the 1,000 random records that were being pulled from Plenar.io.  Now that we’ve modified the API which uses geo-spatial filtering, we are able to support filtering on the service itself.  When a user applies a geo-spatial filter, the query will run on the defined area to find the top 1,000 results, as opposed to querying the entire database for the 1,000 results and then applying the geo-spatial filter.

## Future of OpenGrid

Over the past few months, City staff has worked with Chicagoans from various neighborhoods to gather [feedback on usability](https://github.com/Chicago/opengrid/milestones/v1.2.0).  With the information we have gathered, the next phase of OpenGrid will be focused on making the data that is available in the app even more accessible and user friendly.  The City will also continue to [collaborate](https://github.com/Chicago/opengrid/wiki) with technologists who can help improve the platform to let residents explore open data, to help the city keep our streets safer, and to even make it useful for non-profits who may want to adopt the platform.

## **Interested in contributing to OpenGrid?**

If you&#8217;re interested in collaborating with the city, you can take a look at the [past meeting notes on the project&#8217;s Wiki](https://github.com/Chicago/opengrid/wiki/OpenGrid-Weekly-Meeting-Notes-2016-06-17). While the [source code is online](http://www.github.com/Chicago/opengrid), the [project&#8217;s documentation](http://opengrid.readthedocs.io/en/stable/) gives a concise overview for developers. Likewise, look at the [instructions for contributors](https://github.com/Chicago/opengrid/blob/master/CONTRIBUTING.md) to help us run a useful, collaborative project.

&nbsp;