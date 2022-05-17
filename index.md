---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<div class="container"> 


<h1>Open Data Realtime Report</h1>
<br>
<p>This report provides real-time metrics on Chicago’s open data program and is intended to inform public debate and help identify opportunities for growth and expansion of this important program.</p>
<br>
<p>Updated May 17, 2022</p>
<br>
<h3><a id="dataset"></a> open datasets</h3> 
<br>
<h3><a id="otherAssets"></a> other data assets built with open datasets</h3> 
<br>
<canvas id="catalogChart" width="200" height="100"></canvas>
<br>	

<h3>Most Popular Datasets</h3>
<br>
<button id="last24">Last 24 Hours</button>
<button id="lastWeek">Last Week</button>
<button id="lastMonth">Last Month</button>
<button id="lastYear">Last Year</button>

<canvas id="lastChart" width="200" height="100"></canvas>
<br>

<h3>How Much Data is Open?</h3>

<canvas id="rowHistoryChart" width="200" height="100"></canvas>
<br>

<h3>When Were Datasets Launched?</h3>

<canvas id="launchedChart" width="200" height="100"></canvas>
<br>

<h3>How Recently Were Datasets Refreshed?</h3>

<canvas id="updatedChart" width="200" height="100"></canvas>
<br>

<h3>Which Departments Release Open Data?</h3>
<br>
<button id="top10">Top 10</button>
<button id="all">All</button>

<canvas id="deptCountsChart" width="200" height="100"></canvas>
<br>

<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/2.9.4/Chart.bundle.min.js
"></script>

<script>

var ctxCatalog = document.getElementById('catalogChart').getContext('2d');
var ctxLaunched = document.getElementById('launchedChart').getContext('2d');
var ctxUpdated = document.getElementById('updatedChart').getContext('2d');
var ctxDeptCounts = document.getElementById('deptCountsChart').getContext('2d');
//var ctxDeptVisitsDownloads = document.getElementById('deptVisitsDownloadsChart').getContext('2d');
//var ctxDeptRows = document.getElementById('deptRowsChart').getContext('2d');
var ctxRowHistory = document.getElementById('rowHistoryChart').getContext('2d');
var ctxLastChart = document.getElementById('lastChart').getContext('2d');


async function getData(address) {
  //const response = await fetch('https://data.cityofchicago.org/resource/2kfw-zvte.json?$select=date_trunc_ymd(start_time)%20as%20day,count(start_time)%20as%20count&$group=day')

  // catalog counts = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=type,count(UID)%20as%20count&$where=audience=%27public%27&$group=type&$order=-count

  // public datasets launched = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=date_trunc_ym(creation_date)%20as%20month,count(creation_date)%20as%20count&$group=month&$where=Audience=%22public%22&type=%27dataset%27&$order=month

  // public datasets last updated = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=date_trunc_ym(last_data_updated_date)%20as%20month,count(last_data_updated_date)%20as%20count&$group=month&$where=Audience=%22public%22&type=%27dataset%27&$order=month

  // all assets access counts = https://data.cityofchicago.org/resource/fbwj-4m2z.json?$select=date_trunc_ym(Timestamp)%20as%20month,count(Timestamp)%20as%20count&$group=month&$order=month

  // assets inventory visits + download by dept = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=metadata_dataowner%20as%20department,sum(visits)%20as%20visits,sum(downloads)%20as%20downloads&$group=department

  // rows by department = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=metadata_dataowner%20as%20department,sum(row_count)%20as%20count&$group=department&$where=Audience=%22public%22&type=%27dataset%27&$order=-count

  // row history by date = https://data.cityofchicago.org/resource/he44-gjvs.json?$select=inventory_date%20as%20date,sum(row_count)%20as%20count&$group=date&$where=type=%27dataset%27&audience=%27public%27

  // datasets by department = https://data.cityofchicago.org/resource/ip5i-wfzw.json?$select=metadata_dataowner%20as%20department,count(department)%20as%20count&$group=department&$where=Audience=%22public%22&type=%27dataset%27&$order=-count

  // relative as of 2/20 8pm UTC

  // top 10 last 24 hours = https://data.cityofchicago.org/resource/fbwj-4m2z.json?$select=asset_name%20as%20department,sum(value)%20as%20count&$group=department&$where=timestamp%3E%272021-02-18T21:00:00.000%27&$order=-count&$limit=10

  // top 10 last week = https://data.cityofchicago.org/resource/fbwj-4m2z.json?$select=asset_name%20as%20department,sum(value)%20as%20count&$group=department&$where=timestamp%3E%272021-02-13T21:00:00.000%27&$order=-count&$limit=10

  // top 10 last month = https://data.cityofchicago.org/resource/fbwj-4m2z.json?$select=asset_name%20as%20department,sum(value)%20as%20count&$group=department&$where=timestamp%3E%272021-01-20T21:00:00.000%27&$order=-count&$limit=10

  // top 10 last year = https://data.cityofchicago.org/resource/fbwj-4m2z.json?$select=asset_name%20as%20department,sum(value)%20as%20count&$group=department&$where=timestamp%3E%272020-02-20T21:00:00.000%27&$order=-count&$limit=10

  const response = await fetch(address)
  const data = await response.json();

  // needs to be generalized just for basic labels and counts, timeseries and department

  var labels = data.map(function(row) {
    if (row.month) {
      return new Date(row.month);
    } else if (row.date) {
      return new Date(row.date);
    } else if (row.department) {
      if(row.department.length > 50) {
        return row.department.substring(0,49);
      } else return row.department;
    }        
  })
  var counts = data.map(function(row) {
    if (row.visits) {
      return parseInt(row.visits) + parseInt(row.downloads);
    } else if (row.count) {
      return row.count;
    } else if (row.visits) {
      return row.visits + row.downloads
    }
  })
  return {labels, counts}
} 

async function makeChart(ctx,data,type,options,lbl) {
  if (type=='line') {
    background='rgba(148,159,177,0.2)' 
  } else background='#66ACD6'
  return new Chart(ctx, {
    type: type,
    data: {
      labels: data.labels,
      datasets: [{
        label: lbl,
        borderColor: '#66ACD6',
        backgroundColor: background,
        borderWidth: 2,
        pointRadius: 0,
        data: data.counts,
        lineTension: 0.1
      }]
    },
    options: options
  });
}


async function start(){
  const catalogData = await getData('/json/catalog-data.json')
  const launchedData = await getData('/json/launched-data.json')
  const updatedData = await getData('/json/updated-data.json')
  const deptCountsData = await getData('/json/department-counts.json')
  const deptCountsDataTop10 = await getData('/json/department-counts-top-10.json')
//  const deptVisitsDownloadsData = await getData('/json/department-visits-downloads.json')
//  const deptRowsData = await getData('/json/department-rows.json')
  const rowHistoryData = await getData('/json/row-history.json')
  const dept24hoursData = await getData('/json/24-hours.json')
  const deptWeekData = await getData('/json/week.json')
  const deptMonthData = await getData('/json/month.json')
  const deptYearData = await getData('/json/year.json')

  timeOptions = {
    tooltips: {
      callbacks: {
        label: function(tooltipItems, data) {
          const num = new Number(data.datasets[0].data[tooltipItems.index])
          return data.datasets[0].label + ": " + num.toLocaleString();
        }        
      }
    },
    scales: {
      xAxes: [{
        type: 'time',
        time: {
          unit: 'year' 
        },
        ticks: {
          autoSkip: false,
        }
      }],
      yAxes: [{
        ticks: {
          beginAtZero: true,
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }]
    }
  }

  timeOptionsOffset = {
    tooltips: {
      callbacks: {
        label: function(tooltipItems, data) {
          const num = new Number(data.datasets[0].data[tooltipItems.index])
          return data.datasets[0].label + ": " + num.toLocaleString();
        }
      }
    },
    scales: {
      xAxes: [{
        type: 'time',
        time: {
          unit: 'year' 
        },
        offset: true,
        ticks: {
          autoSkip: false,
        }
      }],
      yAxes: [{
        ticks: {
          beginAtZero: true,
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }]
    }
  }

  timeOptionsMonth = {
    tooltips: {
      callbacks: {
        label: function(tooltipItems, data) {
          const num = new Number(data.datasets[0].data[tooltipItems.index])
          return data.datasets[0].label + ": " + num.toLocaleString();
        }   
      }
    },
    scales: {
      xAxes: [{
        type: 'time',
        time: {
          unit: 'month' 
        },
        offset: true,
        ticks: {
          autoSkip: false,
        }
      }],
      yAxes: [{
        ticks: {
          beginAtZero: true,
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }]
    }
  }

  categoryOptions = {
    tooltips: {
      callbacks: {
        label: function(tooltipItems, data) {
          const num = new Number(data.datasets[0].data[tooltipItems.index])
          return data.datasets[0].label + ": " + num.toLocaleString();
        }
      }
    },
    scales: {
      xAxes: [{
        categoryPercentage: 1.0,
        barPercentage: 1.0,
        ticks: {
          beginAtZero: true,
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }]
    }
  }

  categoryOptionsVertical = {
    tooltips: {
      callbacks: {
        label: function(tooltipItems, data) {
          const num = new Number(data.datasets[0].data[tooltipItems.index])
          return data.datasets[0].label + ": " + num.toLocaleString();
        }
      }
    },
    scales: {
      xAxes: [{
        ticks: {
          beginAtZero: true,
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }],
      yAxes: [{
        ticks: {
          callback: function(value, index, values) {
            return value.toLocaleString();
          }
        } 
      }]
    }
  }


  var catalogChart = makeChart(ctxCatalog, catalogData, 'bar', categoryOptionsVertical, 'Asset Count')
  var launchedChart = makeChart(ctxLaunched, launchedData, 'line', timeOptions, 'Public Datasets Launched')
  var updatedChart = makeChart(ctxUpdated, updatedData, 'bar', timeOptionsOffset, 'Datasets Refreshed') 
  var deptCountsChart = makeChart(ctxDeptCounts, deptCountsDataTop10, 'horizontalBar', categoryOptions, 'Public Datasets') 
//  makeChart(ctxDeptVisitsDownloads, deptVisitsDownloadsData, 'horizontalBar', categoryOptions, 'Public Dataset Visits and Downloads') 
//  makeChart(ctxDeptRows, deptRowsData, 'horizontalBar', categoryOptions, 'Public Dataset Row Counts') 
  var rowHistoryChart = makeChart(ctxRowHistory, rowHistoryData, 'line', timeOptionsMonth, 'Rows of Data')
  var lastChart = makeChart(ctxLastChart, dept24hoursData, 'horizontalBar', categoryOptions, 'Access Count - Last 24 hours')   

  document.getElementById('last24').addEventListener('click', function() {
    const update = () => {
      lastChart.then((lc) => {
        lc.data.labels = dept24hoursData.labels;
        lc.data.datasets.forEach((dataset) => {
          dataset.data = dept24hoursData.counts;
          dataset.label = "Access Count - Last 24 hours"
        });
        lc.update();
      });
    };
    update()
  });
  document.getElementById('lastWeek').addEventListener('click', function() {
    const update = () => {
      lastChart.then((lc) => {
        lc.data.labels = deptWeekData.labels;
        lc.data.datasets.forEach((dataset) => {
          dataset.data = deptWeekData.counts;
          dataset.label = "Access Count - Last Week"
        });
        lc.update();
      });
    };
    update()
  });

  document.getElementById('lastMonth').addEventListener('click', function() {
    const update = () => {
      lastChart.then((lc) => {
        lc.data.labels = deptMonthData.labels;
        lc.data.datasets.forEach((dataset) => {
          dataset.data = deptMonthData.counts;
          dataset.label = "Access Count - Last Month"
        });
        lc.update();
      });
    };
    update()
  });

  document.getElementById('lastYear').addEventListener('click', function() {
    const update = () => {
      lastChart.then((lc) => {
        lc.data.labels = deptYearData.labels;
        lc.data.datasets.forEach((dataset) => {
          dataset.data = deptYearData.counts;
          dataset.label = "Access Count - Last Year"
        });
        lc.update();
      });
    };
    update()
  });

  document.getElementById('top10').addEventListener('click', function() {
    const update = () => {
      deptCountsChart.then((dcc) => {
        dcc.data.labels = deptCountsDataTop10.labels;
        dcc.data.datasets.forEach((dataset) => {
          dataset.data = deptCountsDataTop10.counts;
          dataset.label = "Access Count - Last Year"
        });
        dcc.update();
      });
    };
    update()
  });

  document.getElementById('all').addEventListener('click', function() {
    const update = () => {
      deptCountsChart.then((dcc) => {
        dcc.data.labels = deptCountsData.labels;
        dcc.data.datasets.forEach((dataset) => {
          dataset.data = deptCountsData.counts;
          dataset.label = "Access Count - Last Year"
        });
        dcc.update();
      });
    };
    update()
  });

}

start()

</script>

<script>

async function getCurrentNumbers() {

  const response = await fetch('https://data.cityofchicago.org/resource/xzkq-xp2w.json?$select=avg(annual_salary)')

  const data = await response.json();
  
  avgSalary = data[0].avg_annual_salary;

  //  document.getElementById("dataset").innerHTML = avgSalary.substring(0,3);
  //  document.getElementById("otherAssets").innerHTML = Number(avgSalary.substring(0,5)).toLocaleString();
  document.getElementById("dataset").innerHTML = '551';
  document.getElementById("otherAssets").innerHTML = '13,950'
}

getCurrentNumbers()

</script>

</div>
