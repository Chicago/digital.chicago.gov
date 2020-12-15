---
id: 42097
title: Building Safety Data on the Open Data Portal
date: 2016-08-01T15:54:44-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=42097
permalink: /index.php/building-safety-data-on-the-open-data-portal/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/07/chicago-796121_1920.jpg
categories:
  - Feature
tags:
  - administrative hearings
  - buildings
  - department of buildings
  - Open Data
  - open data portal
---
[<img loading="lazy" class="aligncenter size-large wp-image-42100" src="http://digital.cityofchicago.org/wp-content/uploads/2016/08/Capture-1024x525.png" alt="Building Violations DataLense" width="1024" height="525" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/08/Capture-1024x525.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2016/08/Capture-300x154.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/08/Capture-768x393.png 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/08/Capture.png 1622w" sizes="(max-width: 1024px) 100vw, 1024px" />](https://data.cityofchicago.org/Administration-Finance/Ordinance-Violations/r6as-hbrs)

&nbsp;

One of the most defining characteristics of any city is its buildings. They help define the physical character and aesthetic of any city. A&nbsp;_[USA Today](http://www.10best.com/awards/travel/best-international-skyline/)_ reader poll put Chicago&#8217;s skyline as the second-best in the United States. Buildings go beyond the downtown and into our neighborhoods to&nbsp;serve a greater function to also house and shelter us. So it&#8217;s also important to make sure these buildings are safe and cared for, which is accomplished by the [City of Chicago&#8217;s Department of Buildings](http://www.cityofchicago.org/city/en/depts/bldgs.html)&nbsp;which&nbsp;inspects and sometimes issues violations for buildings failing to meet a standard for quality and safety.

Several years ago, Chicago published building violations data on the data portal. Last year, the city began publishing a list of&nbsp;[problematic landlords](https://data.cityofchicago.org/Buildings/Problem-Landlord-List/n5zj-r44u)&nbsp;and a list of&nbsp;[building code scofflaws](https://data.cityofchicago.org/Buildings/Building-Code-Scofflaw-List/crg5-4zyp). Today, we&#8217;ve expanded building safety data on the open data portal by releasing&nbsp;[administrative hearings data for ordinance violations issued by the Department of Buildings on the open data portal](https://data.cityofchicago.org/Administration-Finance/Ordinance-Violations-Buildings-/6br9-quuz).

<!--more-->

These data detail the current and historical [administrative hearing cases](http://www.cityofchicago.org/city/en/depts/ah.html) resulting from violations and tickets (notices of violations) issued by Department of Buildings. Administrative hearing records provide the status of the cases which result from&nbsp;violations issued&nbsp;to building owners. This is the same data that is used to help the city determine the aforementioned problematic landlord and building scofflaw lists. Updated each day, you can see whether someone was ultimately found liable for a violation or if the case was dismissed. Likewise, you can also see the status of cases that have yet to be decided.

<p class="aligncenter">
</p>

As with any data, there is some nuance in understanding its structure. Often, a single building is issued a ticket (a notice of violation, which is abbreviated as NOV). In this data, each row represents a particular violation. Violations which were part of the same ticket are denoted by the same NOV NUMBER. The VIOLATION CODE indicates the unique code for a particular violation while VIOLATION DESCRIPTION gives a plain-language description of the VIOLATION CODE.

At times, a case may have multiple respondents. This field is pipe-delimited, so each respondent is separated by a &#8220;|&#8221; character.

Every morning, the data set is updated with the most recent information, including the stage for each case.&nbsp;For cases that haven&#8217;t been determined, it shows the current status, such as cases that have continuances (i.e., rescheduled). See the LAST MODIFIED DATE&nbsp;to see when the case status has been last updated. When a case has been decided as either a default or liable, information on the associated fines are also included.

<img loading="lazy" class="wp-image-42103 size-medium alignleft" src="http://digital.cityofchicago.org/wp-content/uploads/2016/08/law-and-order-300x169.jpg" alt="law-and-order" width="300" height="169" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/08/law-and-order-300x169.jpg 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/08/law-and-order-768x434.jpg 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/08/law-and-order.jpg 1024w" sizes="(max-width: 300px) 100vw, 300px" /> 

This data set complements the [building violations data](https://data.cityofchicago.org/Buildings/Building-Violations/22u3-xenr) already on the data portal. The building violation data set represents the inspections and violations issued by the Department of Buildings.&nbsp;Just like&nbsp;_Law & Order_, the violations data provides the citation (law), while this new ordinance violations provides the hearing (order).