---
id: 42258
title: OpenGrid v1.2.0 Now Available
date: 2016-10-03T17:02:59-05:00
author: Tom Schenk
layout: post
guid: http://digital.cityofchicago.org/?p=42258
permalink: /index.php/opengrid-v1-2-0-now-available/
image: https://digital.cityofchicago.org/wp-content/uploads/2016/10/opengrid-with-legend.jpg
categories:
  - Feature
tags:
  - Open Source
  - OpenGrid
---
Back in April, the City of Chicago partnered with one of the Smart Chicago Collaborative anchor programs, the [Civic User Testing Group (CUTGroup)](http://www.cutgroup.org/), to host a UX testing feedback session attended by more than 20 Chicago residents for [OpenGrid](https://opengrid.io). The purpose of these tests was not only to engage all of Chicago in the civic app development process, but provide valuable information to OpenGrid developers seeking to enhance the apps’ usability and performance. The newest version contains improvements to OpenGrid to make it easier to use. The latest release contains friendlier language, an improved user interface to highlight more important features while deemphasizing more technical options, and reducing the number of mouse clicks to see data. Below are some of the highlights of this release.

## Simpler Advanced Search Panel

### More Accessible Language throughout the application

During the CUTGroup testing, we saw that there were some opportunities to make the language more accessible. Users commented that the language throughout the application seemed to be targeted more towards developers and people with tech backgrounds. For example, in the Advanced Search panel, language such as “Geo-spatial filters” and “Queries” seemed to cause some hesitation to users.  Therefore, we simplified the language to make it more user friendly. “Advanced Search” was changed to “Find Data,” “Datasets and Standard Filters” was changed to “Select Data,” and “Submit” and “Reset” were changed to “Get Data” and “Clear Search” respectively.

### Submit and Reset buttons are now set as footer

Previously, users would have to scroll to the bottom of the advanced search panel to run or clear a search. Now these buttons are static at the bottom of the page for easier accessibility.

<img loading="lazy" class="aligncenter size-full wp-image-42259" src="http://digital.cityofchicago.org/wp-content/uploads/2016/10/before-and-after.jpg" alt="before-and-after" width="1046" height="635" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/10/before-and-after.jpg 1046w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/before-and-after-300x182.jpg 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/before-and-after-768x466.jpg 768w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/before-and-after-1024x622.jpg 1024w" sizes="(max-width: 1046px) 100vw, 1046px" /> 

### Color coded dots for each dataset

When multiple datasets are added to a search, the dots for each dataset are now assigned a different color by default. Now that the user doesn’t have to manually assign a new color, we have cleaned up the advanced search panel to retract the color and opacity under “Color Options.”

<img loading="lazy" class="aligncenter size-full wp-image-42260" src="http://digital.cityofchicago.org/wp-content/uploads/2016/10/color-options.jpg" alt="color-options" width="969" height="296" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/10/color-options.jpg 969w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/color-options-300x92.jpg 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/color-options-768x235.jpg 768w" sizes="(max-width: 969px) 100vw, 969px" /> 

### Advanced Search Panel Retracts After Executing Query

To maximize the amount of data viewable to the user upon executing a search, the advanced search panel now retracts upon performing a search.

### The ability to perform searches using OR

When applying filters for a dataset, users were only limited to applying an “AND” operator, now users can select “OR.”

## Easier-to-read Map

### Map Icons More Accessible

Users no longer have to retract the Find Data Panel in order to apply a layer or create a measurement on the grid. The layers and measurement icons have been moved to the boot left of the map for easier access.

<img loading="lazy" class="aligncenter size-full wp-image-42261" src="http://digital.cityofchicago.org/wp-content/uploads/2016/10/map-icons.jpg" alt="map-icons" width="673" height="777" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/10/map-icons.jpg 673w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/map-icons-260x300.jpg 260w" sizes="(max-width: 673px) 100vw, 673px" /> 

### More Prominent Grid View

As seen in the screenshots above, we have changed the grid view access bar to a bold and black color, whereas previously it was gray and overlooked by users.

### Map Extent by Default

When performing a search, all of the data is limited to a default geographical area shown on the map (i.e. map extent). The map extent is now setup to return results of the area that is currently visible on the grid. For example, if a user pans or zooms in to the Loop or Humboldt Park area and runs a quick search on crimes or fires, the results will return within the area that the user extended on the map.

Note: The default map extent does not apply when searching for points of interest like Starbucks, McDonalds, etc.

### New Base Map

The new base map is now lighter and has a better contrast quality, allowing users to see the data displayed on the grid more clearly.

### Map Legend

The map legend displays all of the datasets that were included in the users search. It appears at the bottom right of the grid when an advanced or quick search is executed.

<img loading="lazy" class="aligncenter size-full wp-image-42262" src="http://digital.cityofchicago.org/wp-content/uploads/2016/10/legend.jpg" alt="legend" width="921" height="698" srcset="https://digital.cityofchicago.org/wp-content/uploads/2016/10/legend.jpg 921w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/legend-300x227.jpg 300w, https://digital.cityofchicago.org/wp-content/uploads/2016/10/legend-768x582.jpg 768w" sizes="(max-width: 921px) 100vw, 921px" /> 

## Future of OpenGrid

To continue our efforts in improving the user experience, the team is working towards making the map more responsive as users move around the city. As the user drags the map, the query will refresh to the new map extent. The team is also working towards upgrading Leaflet to v1.0 (previously v0.7) as well as all dependent plugins. Lastly, we will also be improving the Quick Search feature to allow users to perform multiple quick searches as well as perform a quick search along with an advanced search (now called, “Find Data”).

## **Interested in contributing to OpenGrid?**

If you&#8217;re interested in collaborating with the city, you can take a look at the [past meeting notes](https://www.github.com/Chicago/opengrid/wiki) on the project&#8217;s Wiki. While the source code is online, the [project&#8217;s documentation](https://docs.opengrid.io) gives a concise overview for developers. Likewise, look at the [instructions for contributors](https://github.com/Chicago/opengrid/blob/master/CONTRIBUTING.md) to help us run a useful, collaborative project.