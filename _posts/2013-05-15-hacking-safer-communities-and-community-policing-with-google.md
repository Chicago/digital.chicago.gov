---
id: 40728
title: Hacking Community Policing with Google
date: 2013-05-15T22:06:22-05:00
author: ankurthakkar
layout: post
guid: http://digital.cityofchicago.org/?p=40728
permalink: /index.php/hacking-safer-communities-and-community-policing-with-google/
image: https://digital.cityofchicago.org/wp-content/uploads/2013/05/ClearPathWriting.jpg
categories:
  - Default
  - Feature
tags:
  - CAPS
  - Civic Data
  - CPD
  - data
  - Data Science
  - Public Safety
  - Technology and Innovation
---
<div id="attachment_40735" style="width: 688px" class="wp-caption aligncenter">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/05/ClearPathBlackandWhite.jpg"><img aria-describedby="caption-attachment-40735" loading="lazy" class="size-full wp-image-40735" alt="ClearPathBlackandWhite" src="http://digital.cityofchicago.org/wp-content/uploads/2013/05/ClearPathBlackandWhite.jpg" width="678" height="509" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/05/ClearPathBlackandWhite.jpg 678w, https://digital.cityofchicago.org/wp-content/uploads/2013/05/ClearPathBlackandWhite-300x225.jpg 300w" sizes="(max-width: 678px) 100vw, 678px" /></a>
  
  <p id="caption-attachment-40735" class="wp-caption-text">
    Photo by Brian Fitzpatrick
  </p>
</div>

On Saturday, civic web developers, designers, and data gurus came together with the Chicago Police Department at Google’s Chicago headquarters to test out and find creative ways to use the new [ClearPath API](http://api1.chicagopolice.org/clearpath/documentation).

[ClearPath](https://portal.chicagopolice.org/portal/page/portal/ClearPath) is the Chicago Police Department’s community information portal. First launched in 2007, ClearPath gives residents information not only about crime in their area, but also information about which police beat they’re on and when their [CAPS](https://portal.chicagopolice.org/portal/page/portal/ClearPath/Get%2520Involved/How%2520CAPS%2520works) meeting is.

CAPS (Chicago Alternative Policing Program) is Chicago’s community policing program. At the center of this program are the CAPS meetings that occur in each police beat. At the CAPS meetings, the police department can hear about community concerns in the neighborhood and interact with local residents. With the new [API](https://portal.chicagopolice.org/portal/page/portal/ClearPath/Get%2520Involved/How%2520CAPS%2520works/What%2520is%2520CAPS), the Chicago Police Department wants to make it easier for residents to interact with the[ClearPath](https://portal.chicagopolice.org/portal/page/portal/ClearPath) website and to report community concerns.

The hackathon produced a number of creative ways to use the API to make it easier to interact with CAPS and the ClearPath system.

<h2 style="text-align: left;">
  <a href="http://capsure.opencityapps.org/">CAPSure</a> by <a href="http://www.opencityapps.org/">OpenCity Apps</a>
</h2>

<img loading="lazy" class="size-full wp-image-40731 alignleft" alt="clearpathcapsure" src="http://digital.cityofchicago.org/wp-content/uploads/2013/05/clearpathcapsure.jpg" width="640" height="348" srcset="https://digital.cityofchicago.org/wp-content/uploads/2013/05/clearpathcapsure.jpg 640w, https://digital.cityofchicago.org/wp-content/uploads/2013/05/clearpathcapsure-300x163.jpg 300w" sizes="(max-width: 640px) 100vw, 640px" /> 

[Derek Eder](http://datamade.us/ "http://datamade.us/") and the [OpenCity](http://www.smartchicagocollaborative.org/using-the-new-clearpath-api-to-help-communities-interact-with-the-chicago-police-department/opencityapps.org)team helped to test the API and got an early start on building an app using the API.

The app they launched is called CAPsure. CAPSure helps residents get information about their local CAPS meeting. You enter in your address and the app will tell you which police beat you are in, when your next CAPS meeting is, and where the meeting is located. The app can also add the meeting to your Outlook, Google, or iCal calendars.

The [app uses](http://capsure.opencityapps.org/about%23why-did-you-build-this) the [ClearPath API’s](http://api1.chicagopolice.org/clearpath/documentation) calendar and event data to find events. The app also uses the City of Chicago’s data sets to help find users [police district](https://www.google.com/fusiontables/DataSource?docid=1fYRn1iHFY65w6QAEzBoPnw-SHtwvgWO2zeyCrkU%23rows:id=1 "https://www.google.com/fusiontables/DataSource?docid=1fYRn1iHFY65w6QAEzBoPnw-SHtwvgWO2zeyCrkU#rows:id=1") and [beat number](https://www.google.com/fusiontables/DataSource?docid=1GXIIvWOaM_YDdY8GHeK0Vo-4nrceGnmhZtHLDFs%23rows:id=1 "https://www.google.com/fusiontables/DataSource?docid=1GXIIvWOaM_YDdY8GHeK0Vo-4nrceGnmhZtHLDFs#rows:id=1").

<h2 style="text-align: left;">
  <a href="https://github.com/donnchacarroll/cityeyes">CAPStagram</a> – Hackathon Winner
</h2>

<div style="width: 650px" class="wp-caption alignleft">
  <a href="http://digital.cityofchicago.org/wp-content/uploads/2013/05/clearpathcapstagram.jpg"><img loading="lazy" alt="clearpathcapstagram" src="http://digital.cityofchicago.org/wp-content/uploads/2013/05/clearpathcapstagram.jpg" width="640" height="480" /></a>
  
  <p class="wp-caption-text">
    Photo by Patrick Brown
  </p>
</div>

The winner of the Hackathon was a team of [Patrick Brown](https://twitter.com/DwerroAB), [Karl Statz](https://twitter.com/GroverSmash), [Donchaa Carroll](https://twitter.com/donnchacarroll "https://twitter.com/donnchacarroll"), and [Cathy Deng](https://twitter.com/cthydng "https://twitter.com/cthydng").

For this concept, the app attaches a picture to community concerns submitted by residents. Currently, the ClearPath API doesn’t allow you to include pictures when making a community concern report. This mobile app allows users to send their local CAPS district a picture of a concern such as an abandoned building or graffiti to help aid in the investigation.

## CAPS by Text – Runner Up

The runner-up for the hackathon was the team of [Alex Soble](https://twitter.com/alexsoble), [Josh Kalov](https://twitter.com/shua123) and [Demond Drummer](https://twitter.com/citizendrummer).

Their app prototype allows users to send a community concern to their local CAPS district by text so that residents without the internet could still take advantage of the new system.

## CAPs Alerts – Third Place

In third place was an app prototype built by [Kevin McMahon](https://twitter.com/klmcmahon). This mobile app not only uses the ClearPath API to help report community concerns, but it will also alert users when crime is reported near them.

## Other prototypes:

Other ideas for using the ClearPath API included:

[MapThatTrap](https://github.com/JoeGermuska/maptrap): An app that residents can use to report abandoned buildings to both 311 and to the ClearPath API

Green Light Program: A concept that would change the colors of [Chicago’s Blue Light Cameras](https://portal.chicagopolice.org/portal/page/portal/ClearPath/About%2520CPD/POD%2520Program) from blue to green as crime rates went down in the neighborhood.

## Next Steps:

For groups wanting to continue to work on their apps or for people not at the hackathon wanting to get involved, there are some great resources out there to make that happen.

The first is the [Chicago OpenGov Hacknight](http://opengovhacknight.eventbrite.com/) that happens every Tuesday at 6:00pm at [1871](http://www.smartchicagocollaborative.org/using-the-new-clearpath-api-to-help-communities-interact-with-the-chicago-police-department/1871.com). The OpenGov Hack Nights are a great place to learn about what is happening with civic innovation in Chicago and work on civic app projects.

If you’re looking for a place to host your civic app, the Smart Chicago Collaborative provides [free hosting to civic applications](http://www.smartchicagocollaborative.org/projects/hosted-web-space/). Smart Chicago will also provide [user testing](http://cutgroup.smartchicagoapps.org/) for your app for free as well.

If civic developers have questions about the API, they can contact the developers directly by emailing API@ChicagoPolice.org

Making our communities safer is an ongoing challenge that will not be solved in a single weekend or by a single web application. To utilize the new API to the fullest extent will require partnerships between the CAPS office, civic technologists, and community groups. If you’re a CAPS group or neighborhood organization that would like to form partnerships with civic technologists, feel free to email cwhitaker@cct.org for more information.

_By Christopher Whitaker for the  [Smart Chicago Collaborative](http://www.smartchicagocollaborative.org/using-the-new-clearpath-api-to-help-communities-interact-with-the-chicago-police-department/)_