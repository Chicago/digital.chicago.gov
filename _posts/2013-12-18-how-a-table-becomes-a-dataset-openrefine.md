---
id: 41063
title: How a Table Becomes a Dataset, OpenRefine
date: 2013-12-18T20:18:49-06:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=41063
permalink: /index.php/how-a-table-becomes-a-dataset-openrefine/
image: https://digital.cityofchicago.org/wp-content/uploads/2013/12/open-data21.jpg
categories:
  - Default
  - Feature
tags:
  - data
  - Data Science
  - open data portal
  - tutorials
---
The City of Chicago has a small team that works to liberate city data on the [data portal](http://data.cityofchicago.org). We use a variety of tools to clean, transform, and publish data on the portal. Often, datasets are automatically updated every day, but a number of datasets are one-time or infrequent updates.

In a series of posts, we will review the tools and techniques that are used for datasets. Whenever possible, we use open source tools to conduct a process to extract, transform, and load datasets on the portal. In this first post, we will give a detailed description of how we use [OpenRefine](http://openrefine.org/) (formerly GoogleRefine) to clean and transform one-time or infrequently updated datasets.

<!--more-->

Recently, the City posted a on-time upload that describes school performance for [elementary](https://data.cityofchicago.org/Education/Chicago-Public-Schools-Elementary-School-Progress-/tj8h-mnuv) and [high schools](https://data.cityofchicago.org/Education/Chicago-Public-Schools-High-School-Progress-Report/2m8w-izji) based on Chicago Public School&#8217;s [school progress report](http://www.cps.edu/SCHOOLDATA/Pages/SchoolProgressReports.aspx).

### Obtaining Data

The first step is to obtain the dataset. The city is a large organization with over 30,000 employees, so finding new data and the person who knows about it can be more complicated than it seems. Fortunately, we have been posting this dataset for a number of years so we have a great partnership with the CPS staff who delivers this information.

In this case, we actually receive the information via email, which is pretty typical for one-time uploads.

### Cleaning & Organizing Data

There is a significant amount of work to be ready for primetime. Our primary goal is to organize the data to be usable for the civic developer community, researchers, and the member of the public who wants to use the information. This means transforming the data to be machine-readable, easy to conduct statistical analytics, and ready for data visualization. This process can be messy, but fortunately, we have a great tool, OpenRefine, to help with the process.

#### OpenRefine

OpenRefine is an open-source tool designed around wrangling dirty data. Often, data is cleaned in a spreadsheet, but OpenRefine is better. It allows you to quickly investigate your data for extreme values, blanks, or errant text fields mixed with numbers. It also has a powerful scripting language that allows you to systematically transform data.

We load the data we received into OpenRefine. The applications opens typical spreadsheet-like files, such as comma-separated values (CSV), tab-separated values (TSV), and Excel documents. It also supports file types such as XML and JSON&#8211;a favorite for web and application developers.

<div id="attachment_41075" style="width: 624px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_project.png"><img aria-describedby="caption-attachment-41075" loading="lazy" class=" wp-image-41075 " alt="Creating new OpenRefine project" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_project-1024x546.png" width="614" height="328" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_project-1024x546.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_project-300x160.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_project.png 1366w" sizes="(max-width: 614px) 100vw, 614px" /></a>
  
  <p id="caption-attachment-41075" class="wp-caption-text">
    Create a new OpenRefine project
  </p>
</div>

We use OpenRefine&#8217;s facet tool to quickly explore data in each column, looking for extreme values, type-o&#8217;s, and to get the general idea for each column.

<div id="attachment_41076" style="width: 624px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/facet_menu.png"><img aria-describedby="caption-attachment-41076" loading="lazy" class=" wp-image-41076 " alt="Faceting fields" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/facet_menu-1024x546.png" width="614" height="328" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/facet_menu-1024x546.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/facet_menu-300x160.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/facet_menu.png 1366w" sizes="(max-width: 614px) 100vw, 614px" /></a>
  
  <p id="caption-attachment-41076" class="wp-caption-text">
    Facet fields to explore values.
  </p>
</div>

Upon opening, it&#8217;s clear that &#8220;No Data&#8221; is repeated throughout to represent missing values. This creates additional work for any civic developer or researchers. NWEA percentiles were also tagged with suffixes like 1_st, _2_nd_, 3_rd_, and 50_th,_ which would require additional effort to analyze or graph. We want to remove these elements before publishing a dataset.

<div id="attachment_41077" style="width: 307px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_facet.png"><img aria-describedby="caption-attachment-41077" loading="lazy" class="size-full wp-image-41077" alt="Faceting NWEA Scores" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_facet.png" width="297" height="520" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_facet.png 297w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_facet-171x300.png 171w" sizes="(max-width: 297px) 100vw, 297px" /></a>
  
  <p id="caption-attachment-41077" class="wp-caption-text">
    A menu displaying a text facet of NWEA scores
  </p>
</div>

OpenRefine supports several scripting languages: GREL, Clojure, and JRuby, for powerful transformations. We use GREL to eliminate &#8220;No Data&#8221; and eliminate any &#8220;st&#8221;, &#8220;nd&#8221;, &#8220;rd&#8221;, and &#8220;th&#8221;. In addition, we also need to transform the values as proper numbers&#8211;instead of text that appears to be numbers.

We used the replace() function to search and replace values. By default, Google refers to the existing column of data as &#8220;value&#8221;. For instance, to replace any instance of &#8220;No Data&#8221; in a column, we used value.replace(&#8220;No Data&#8221;, &#8220;&#8221;). Like other languages, you can &#8220;daisy chain&#8221; arguments which we use to make several replacements. In addition to removing “No Data”, the “st”, “nd”, “rd”, and &#8220;th&#8221; is also replaced with no values. Thus, the full expression is value.replace(&#8220;No Data&#8221;, &#8220;&#8221;).replace(&#8220;st&#8221;, &#8220;&#8221;).replace(&#8220;nd&#8221;, &#8220;&#8221;).replace(&#8220;rd&#8221;, &#8220;&#8221;).replace(&#8220;th&#8221;, &#8220;&#8221;).

<a style="background-color: #f3f3f3; text-align: center;" href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_transformation.png"><img loading="lazy" class="size-full wp-image-41078" alt="Transforming test scores using GREL" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_transformation.png" width="709" height="541" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_transformation.png 709w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/NWEA_transformation-300x228.png 300w" sizes="(max-width: 709px) 100vw, 709px" /></a>

<dl class="wp-caption aligncenter" id="attachment_41078" style="width: 719px;">
  <dd class="wp-caption-dd">
    A GREL script to strip any text and transform to numbers.
  </dd>
</dl>

Finally, we convert the values to numbers as OpenRefine will treat the result as a text. We add &#8220;.toNumber()&#8221; at the end to force the results to be displayed as numbers. It&#8217;s also important to choose &#8220;set to blank&#8221; on errors as the toNumber() function is invalid after changing &#8216;No Data&#8217; values to blanks. There are over a dozen columns using NWEA scores, so we easily repeated this operation by copy and pasting the function for other columns.

#### Regular Expressions

Website addresses weren&#8217;t normalized, so we performed a couple of operations to normalize the data. It&#8217;s easy to edit single entries within the faceting menu.

<div id="attachment_41079" style="width: 698px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/editing_single_address.png"><img aria-describedby="caption-attachment-41079" loading="lazy" class=" wp-image-41079 " alt="Editing values from facet menu" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/editing_single_address.png" width="688" height="445" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/editing_single_address.png 860w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/editing_single_address-300x193.png 300w" sizes="(max-width: 688px) 100vw, 688px" /></a>
  
  <p id="caption-attachment-41079" class="wp-caption-text">
    Change all instances of single value.
  </p>
</div>

However, that solution does not scale well if there are many corrections to be made. In that situtation, it&#8217;s best to use the transformation tool. OpenRefine supports regular expressions, which we used to add &#8220;http://&#8221; infront of websites that only began with &#8220;www&#8221;.

&nbsp;

<div id="attachment_41080" style="width: 624px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/regex_add_http.png"><img aria-describedby="caption-attachment-41080" loading="lazy" class=" wp-image-41080 " alt="Regex transofmrations" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/regex_add_http-1024x602.png" width="614" height="361" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/regex_add_http-1024x602.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/regex_add_http-300x176.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/regex_add_http.png 1054w" sizes="(max-width: 614px) 100vw, 614px" /></a>
  
  <p id="caption-attachment-41080" class="wp-caption-text">
    Use regular expressions for OpenRefine transformations
  </p>
</div>

#### Adding columns

The &#8220;CPS Performance Policy Status&#8221; needed a number of changes to make it more usable for developers and researchers. The values were &#8216;NOT ON PROBATION&#8217;, &#8216;NOT APPLICABLE&#8217;, or &#8216;ON PROBATION (_x_ YEARS)&#8217; depending on the probation length. We wanted to separate the status and have another column that just has a single number for any probation length.

First, we isolate the number of years if a school is on probation by adding a column based on &#8220;CPS Performance Policy Status&#8221;. We use a series of replace() functions to eliminate the &#8216;NOT APPLICABLE&#8217;, &#8216;NOT ON PROBATION (&#8216;, and &#8216;ON PROBATION (&#8216; text. Next, we use a regular expression to replace &#8221; years)&#8221;, leaving the _x_ years of probation.

<div id="attachment_41082" style="width: 624px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_column.png"><img aria-describedby="caption-attachment-41082" loading="lazy" class=" wp-image-41082 " alt="See the error in the code?" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_column-1024x484.png" width="614" height="290" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_column-1024x484.png 1024w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_column-300x141.png 300w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/create_new_column.png 1158w" sizes="(max-width: 614px) 100vw, 614px" /></a>
  
  <p id="caption-attachment-41082" class="wp-caption-text">
    Create a new column with years of probation
  </p>
</div>

Second, we eschew anything but the probation status using the split() function. We used value.split(&#8221; (&#8220;) to separate the string into an array using &#8221; (&#8221; as the separator. For instance, &#8216;ON PROBATION (5 years)&#8217; is transformed into [&#8216;ON PROBATION&#8217;, &#8216;5 years&#8217;]. We want to just keep &#8216;ON PROBATION&#8217;, so the entire function is written as value.split(&#8221; (&#8220;)[0].

<div id="attachment_41081" style="width: 724px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/11/normalizing_values.png"><img aria-describedby="caption-attachment-41081" loading="lazy" class="size-full wp-image-41081" alt="Normalizing using value.split()" src="http://digital.cityofchicago.org/wp-content/uploads/2013/11/normalizing_values.png" width="714" height="546" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/11/normalizing_values.png 714w, https://digital.cityofchicago.org/wp-content/uploads/2013/11/normalizing_values-300x229.png 300w" sizes="(max-width: 714px) 100vw, 714px" /></a>
  
  <p id="caption-attachment-41081" class="wp-caption-text">
    Splicing probation status from using the value.split function.
  </p>
</div>

OpenRefine stores any changes in a JSON file, which can be exported at the end. If needed, we can use the JSON file to repeat any transformations needed from the original file. You can see the JSON for this file on this [gist](https://gist.github.com/tomschenkjr/8028811).

#### Limitations

OpenRefine is a wonderful tool, but there are limitations. It&#8217;s not a full fledged [ETL](http://en.wikipedia.org/wiki/Extract,_transform,_load) tool and easily allow us to systematically repeat the same transformations on a frequent basis. That limitation leads us to exclusively use OpenRefine on one-time or infrequently updated datasets.

A well-known limitation of OpenRefine is the inability to handle large datasets of several million rows. Usually, it will not allow users to import large datasets into the program, regardless of the performance or specifications.

To fill the gap of these limitations, we have relied on Kettle, an open-source ETL tool for automated updates and will be the subject of the next post in this series.