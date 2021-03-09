---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<div class="container"> 

<h1>Open Data Realtime Report</h1>
<br>
<p>Chicago's open data program is a beacon of transparency in government. Open data <a href="http://opendatatoolkit.worldbank.org/en/open-data-in-60-seconds.html">helps</a> streamline government services, stimulate economic opportunities, improve public safety, and reduce poverty. Chicago’s open data is used every day by media, scholars, businesses, financial markets, and the general public to seek answers to important questions.</p>

<p>Open data plays a pivotal role in informed public discourse. Opening the books on government makes it easier to access facts, enabling more robust debate about what to change and how to change it. By entrusting the public with access to their data, a transparent and open government builds trust and encourages participation.</p>

<p>Open datasets are freely accessible to anyone in the world. They are formatted for ease and readability. They are also machine-readable and immediately ready for data analysis.</p>

<p>This report provides real-time metrics on Chicago’s open data program and is intended to inform public debate and help identify opportunities for growth and expansion of this important program.</p>

<p>Some highlights of our current datasets are listed below. Find these and more open data at <a href="https://data.cityofchicago.org">data.cityofchicago.org</a></p>

<h4>Public Health</h4>

<p>COVID-19 Status and Impact<br>Food and Medicine Access Maps</p>

<h4>Government Spending</h4>

<p>City Budget<br>Salaries<br>Contracts and Payments<br>Tax Increment Financing (TIF)</p>

<h4>Public Safety</h4>

<p>Arrests<br>Crimes<br>Shootings</p>

<h4>Equity</h4>

<p>TK</p>

<h4>Mobility</h4>

<p>Public Transit Use<br>Ride-hail and Taxi Trips<br>Bikeshare Use<br>Scooters Trips<br>Congestion and Traffic Conditions</p>

<h2>Our Most Popular Datasets</h2>

<button id="last24">Last 24 Hours</button>
<button id="lastWeek">Last Week</button>
<button id="lastMonth">Last Month</button>
<button id="lastYear">Last Year</button>

<canvas id="lastChart" width="200" height="100"></canvas>
<br>

<h2>How Much Data is Open?</h2>

<canvas id="rowHistoryChart" width="200" height="100"></canvas>
<br>

<h2>When Were Datasets Launched?</h2>

<canvas id="launchedChart" width="200" height="100"></canvas>
<br>

<h2>How Recently Were Datasets Refreshed?</h2>

<canvas id="updatedChart" width="200" height="100"></canvas>
<br>

<h2>Which Departments Release Open Data?</h2>

<canvas id="deptCountsChart" width="200" height="500"></canvas>
<br>

</div> 

<!-- Hold for now
<canvas id="deptVisitsDownloadsChart" width="200" height="500"></canvas>
<canvas id="deptRowsChart" width="200" height="500"></canvas>
-->



