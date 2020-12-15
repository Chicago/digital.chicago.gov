---
id: 41863
title: Open Data ETL Utility Kit version 1.2.0 now available
date: 2015-12-10T17:07:37-06:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41863
permalink: /index.php/open-data-etl-utility-kit-version-1-2-0-now-available/
image: https://digital.cityofchicago.org/wp-content/uploads/2015/12/8016200072_c5dca4b9da_o.jpg
categories:
  - Default
  - Feature
tags:
  - Open Data
  - open data portal
  - Open Source
---
One of the important lessons we&#8217;ve learned with open data is to leverage technology to automatically update data. There are a number of benefits to this: leveraging technology means we can update data every day, every hour, or even every 10 minutes. Providing data that is reliably updated also means companies, like [Chicago Cityscape](http://www.chicagocityscape.com/) and [EveryBlock](http://www.everyblock.com/), and civic developers can have confidence that fresh data will be available in their applications. Every day, a little over 100 scripts run to keep the data portal up-to-date using an internal &#8220;framework&#8221; we&#8217;ve developed for this process.

Last year, we [released the software](http://www.smartchicagocollaborative.org/city-of-chicago-launches-opendata-etl-utility-kit/) we used to drive our Extract-Transform-Load (ETL) process that automatically updates our data portal. Today, [we&#8217;ve released version 1.2.0](https://github.com/Chicago/open-data-etl-utility-kit/releases/tag/1.2.0) with some new enhancements.

## Windows compatibility

While the software is compatibility with Windows, there have been a few utilities that were only compatible on the Linux and MacOS. With this release, we&#8217;ve brought full compatibility to Windows, so you can use the useful ETL Log utilities. As always, this utility is platform agnostic so you can develop ETLs on a Windows machine and deploy it on Red Hat, or vice versa, with no modifications.

For instance, suppose I am experiencing issues with uploading data on [Beach Water Quality](https://data.cityofchicago.org/Parks-Recreation/Beach-Water-Quality-Automated-Sensors/qmqz-2xku). It appears to take a long time, but need to discover if the performance is unusual. I can use the A_ETLRuntimes.bat utility to summarize the time it. We refer to each data set by it&#8217;s unique ID, in the case of the beach data, that is &#8220;qmqz-2xku&#8221; (see the URL):

`C:\path\to\open-data-etl-utility-kit\Log>A_ETLRuntimes qmqz-2xku`

The output from the command summarizes the run-time:

<pre>INFO 01-08 00:45:31,840 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 01:45:30,199 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 02:45:31,140 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 03:45:28,912 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 04:45:36,126 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 05:45:34,713 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 06:45:30,634 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 07:45:30,623 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 08:45:29,526 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 09:45:31,162 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 10:45:29,547 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 11:45:30,572 - Kitchen - Processing ended after 11 seconds.
INFO 01-08 12:45:30,549 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 13:45:30,839 - Kitchen - Processing ended after 11 seconds.
INFO 01-08 14:45:31,076 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 15:45:30,413 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 16:45:36,389 - Kitchen - Processing ended after 15 seconds.
INFO 01-08 17:45:30,481 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 18:45:26,824 - Kitchen - Processing ended after 8 seconds.
INFO 01-08 19:45:35,574 - Kitchen - Processing ended after 11 seconds.
INFO 01-08 20:45:29,922 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 21:45:27,716 - Kitchen - Processing ended after 9 seconds.
INFO 01-08 22:45:28,732 - Kitchen - Processing ended after 10 seconds.
INFO 01-08 23:45:30,488 - Kitchen - Processing ended after 10 seconds.
INFO 02-08 00:45:29,156 - Kitchen - Processing ended after 9 seconds.
INFO 02-08 01:47:32,107 - Kitchen - Processing ended after 2 minutes and 14 sec
 onds (134 seconds total).</pre>

It appears that the most recent ETL did take longer than normal&#8211;over 2 minutes compared to the typical 10 seconds.

There are a [handful of these utilities](http://open-data-etl-utility-kit.readthedocs.org/en/1.2.0/utilities-for-administering-etls.html) now compatible on Windows machines (and Linux/Mac):

  * Summarize ETL run times
  * Show the files associated with a particular data set
  * Show ETL logs from today
  * Run a specific ETL based on its name (see below)

## Quick update from the command line

While it&#8217;s best to schedule uploads ahead of time, sometimes it&#8217;s convenient to run a one-time, unscheduled upload. Now, it&#8217;s a [little easier](http://open-data-etl-utility-kit.readthedocs.org/en/1.2.0/utilities-for-administering-etls.html#run-a-specific-etl) to do this from a Linux/MacOS shell or Windows command prompt. Using that same unique ID as before, we run the ETL with:

`C:\path\to\open-data-etl-utility-kit\Log>A_RunETL.bat qmqz-2xku`

For Linux or Mac:

<pre>$ cd \path\to\open-data-etl-utility-kit\Log
$ ./A_RunETL.sh qmqz-2xku
</pre>

Soon enough, your data set will be updated on the portal.