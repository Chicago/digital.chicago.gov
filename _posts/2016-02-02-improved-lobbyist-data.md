---
id: 41857
title: Improved Lobbyist Data
date: 2016-02-02T23:20:54-06:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41857
permalink: /index.php/improved-lobbyist-data/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/02/chicago_cityhall.jpg
categories:
  - Default
  - Feature
tags:
  - data
  - ethics
  - lobbyists
  - Open Data
---
_Edited 8/21/2017 to add the new Expenditures &#8211; Hosting dataset._

We have revamped the presentation of data about lobbyists on our <a title="Chicago Open Data Portal" href="https://data.cityofchicago.org" target="_blank" rel="noopener">Open Data Portal</a>. People lobbying the City of Chicago are required to register with the <a title="Board of Ethics" href="http://www.cityofchicago.org/city/en/depts/ethics.html" target="_blank" rel="noopener">Board of Ethics</a> and file periodic reports through its <a title="Electronic Lobbyist Filing System" href="https://webapps1.cityofchicago.org/elf/index.html" target="_blank" rel="noopener">Electronic Lobbyist Filing System</a> (ELF), which began collecting data in 2012. The data structures are complex and previous attempts to recombine data about lobbyists, their employers, their clients, and their lobbying activity on behalf of these entities into tabular datasets ended up being difficult to understand.

In our new approach, we are publishing the data in a way that more closely matches the structures in the source system. Most of the datasets contain only a single type of information, with sufficient common IDs between the datasets for users to link them, as needed.  The subjects of these datasets are:

  * <a title="Clients" href="https://data.cityofchicago.org/d/g8p5-y4m5" target="_blank" rel="noopener">Clients</a>
  * <a title="Compensation" href="https://data.cityofchicago.org/d/dw2f-w78u" target="_blank" rel="noopener">Compensation</a> received by the lobbyists
  * <a title="Contributions" href="https://data.cityofchicago.org/d/p9p7-vfqc" target="_blank" rel="noopener">Contributions </a>(political) made by the lobbyists
  * <a title="Employers" href="https://data.cityofchicago.org/d/dmeb-2zra" target="_blank" rel="noopener">Employers</a>
  * [Expenditures &#8211; Hosting](https://data.cityofchicago.org/d/pvm2-bd2i)
  * <a title="Expenditures - Large" href="https://data.cityofchicago.org/d/xika-473c" target="_blank" rel="noopener">Expenditures &#8211; Larg</a>e ($250 or more, itemized)
  * <a title="Expenditures - Small" href="https://data.cityofchicago.org/d/eqdx-4qxd" target="_blank" rel="noopener">Expenditures &#8211; Small</a> (under $250, summarized)
  * <a title="Gifts" href="https://data.cityofchicago.org/d/5d79-9xqr" target="_blank" rel="noopener">Gifts </a>made by lobbyists
  * <a title="Lobbying Activity" href="https://data.cityofchicago.org/d/pahz-egmi" target="_blank" rel="noopener">Lobbying Activity</a> by lobbyists
  * <a title="Lobbyists" href="https://data.cityofchicago.org/d/tq3e-t5yq" target="_blank" rel="noopener">Lobbyists</a>

There is one dataset that does combine multiple types of information. It links a lobbyist and his or her employer and clients. This dataset contains elements from the Lobbyist, Employers, and Clients datasets but has been combined to give a single view of information from all three in order to show the most central set of relationships in the data:

  * <span style="line-height: 13px;"><a title="Lobbyist, Employer, Client Combinations" href="https://data.cityofchicago.org/d/2eqz-3nvz" target="_blank" rel="noopener">Lobbyist, Employer, Client Combinations</a> (each unique combination of the records from these three datasets)<br /> </span>

## Connections Between the Datasets

The new datasets have the indicated ID columns in common to allow for linking between datasets.

<div id="attachment_42504" style="width: 933px" class="wp-caption aligncenter">
  <img aria-describedby="caption-attachment-42504" loading="lazy" class="wp-image-42504 size-full" src="http://digital.cityofchicago.org/wp-content/uploads/2016/02/Lobbyists-ERD-1.png" alt="An ERD diagram of relationships between the new Lobbyist Datasets." width="923" height="619" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/02/Lobbyists-ERD-1.png 923w, https://digital.cityofchicago.org/wp-content/uploads/2016/02/Lobbyists-ERD-1-300x201.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/02/Lobbyists-ERD-1-768x515.png 768w" sizes="(max-width: 923px) 100vw, 923px" />
  
  <p id="caption-attachment-42504" class="wp-caption-text">
    The relationships between the new Lobbyist datasets.
  </p>
</div>

## Older Data

The [older datasets](https://data.cityofchicago.org/browse?category=Ethics) are still present on the Data Portal.  The Historical datasets are based on the predecessor system to ELF and contain data prior to 2012.  The Deprecated datasets are the previous presentation of ELF data, beginning in 2012.  (There is discussion of our general approach to dataset deprecation in <a href="http://dev.cityofchicago.org/open%20data/data%20portal/2015/07/16/what-is-a-deprecated-dataset.html" target="_blank" rel="noopener">this </a>post on our <a href="http://dev.cityofchicago.org/blog/" target="_blank" rel="noopener">developer blog</a>.)

As always, we welcome comments and questions on these datasets at <a href="mailto:dataportal@cityofchicago.org" target="_blank" rel="noopener">dataportal@cityofchicago.org</a> or <a href="https://twitter.com/ChicagoCDO" target="_blank" rel="noopener">@ChicagoCDO</a>.