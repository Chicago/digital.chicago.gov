---
id: 41771
title: 'Now Available: RSocrata 1.6.0'
date: 2015-04-24T08:00:56-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41771
permalink: /index.php/now-available-rsocrata-1-6-0/
image: https://digital.cityofchicago.org/wp-content/uploads/2015/06/IMAG0220-1.jpg
categories:
  - Default
  - Feature
tags:
  - data.json
  - Open Data
  - open data portal
  - Project Open Data Metadata Schema
  - R
  - RSocrata
  - rstats
---
Last year the City’s data science team released the [first version of RSocrata](http://digital.cityofchicago.org/index.php/rsocrata/), which allows an easy way for R programmers to access and download data from [Socrata data portals](http://www.socrata.com/) using the [R statistical language](http://www.r-project.org/). This week, we’ve released [RSocrata 1.6.0](http://cran.r-project.org/web/packages/RSocrata/index.html), which introduces some new features for users.

Users can now quickly download a list of all datasets from a Socrata open data portal using ls.socrata (short for “list space Socrata”). Use the domain on an open data portal, such as [data.cityofchicago.org](http://data.cityofchicago.org), [data.hawaii.org](http://data.hawaii.org), [iranhumanrights.socrata.com](http://iranhumanrights.socrata.com), or any other portal hosted by Socrata:

<pre>all_the_data &lt;- ls.socrata("data.cityofchicago.org")
nrow(allSitesDataFrame) # Number of datasets
allSitesDataFrame$title # Names of each dataset</pre>

Users can navigate through the entire list of datasets on the portal, a brief description, download URLs, and more. It’s a quick and easy way to view the available data on the portal and also write scripts to download each dataset (using the read.socrata function).

This feature uses the [Project Open Data Metadata Schema](https://project-open-data.cio.gov/v1.1/schema/)—otherwise known as data.json—standard (currently compatible with v1.1). The schema is becoming the _de facto _standard for transmitting metadata, which serves as the basis for the ls.socrata function. This new feature was conceived, [written and submitted](https://github.com/Chicago/RSocrata/pull/12) by [Peter Schmiedeskamp](https://github.com/pschmied) from the University of Washington.

## API Tokens

Heavy users of Socrata should use [API tokens](http://dev.socrata.com/docs/app-tokens.html) to allow for more API requests without being throttled. RSocrata now supports a separate API token field. Users can simply use that optional field to pass along their token and reduce download throttling.

<pre>token &lt;- "ew2rEMuESuzWPqMkyPfOSGJgE"
earthquakesDataFrame &lt;- read.socrata("http://soda.demo.socrata.com/resource/4334-bgaj.csv",
app_token = "ew2rEMuESuzWPqMkyPfOSGJgE")</pre>

Want to hide your API keys on a public project, such as on GitHub? Now you can use the app_token to keep your private token from other users. Create a new file in your project called token.txt with the following content:

<pre>ew2rEMuESuzWPqMkyPfOSGJgE</pre>

You can read-in the token using readLines

<pre>token &lt;- readLines(“path/to/token.txt”, n=1)
read.socrata("http://soda.demo.socrata.com/resource/4334-bgaj.csv",
app_token = token)</pre>

To mask your token, add token.txt to your [.gitignore file](https://help.github.com/articles/ignoring-files/) and, _voila_, you’ve hidden the token.

RSocrata 1.6.0 is available on [CRAN](http://cran.r-project.org/web/packages/RSocrata/index.html) for R 3.2.0 or greater and can be downloaded using:

<pre>install.packages("RSocrata")
library("RSocrata")</pre>

Further development will be conducted on the project’s [GitHub site](https://github.com/Chicago/RSocrata). You can install the beta using devtools the devtools package:

<pre>install.packages("devtools")
library(devtools)
install_github(“Chicago/RSocrata”)</pre>

Use GitHub to submit new features or [issues](https://github.com/Chicago/RSocrata/issues). You can also reach us by contacting [@ChicagoCDO](https://twitter.com/ChicagoCDO) or emailing <developers@cityofchicago.org>.