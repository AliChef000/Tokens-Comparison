<!DOCTYPE html>
<html>
  <head>
    <title>Tokens Dashboard</title>
    <link
      rel="stylesheet"
      media="all"
      href="https://cdn.jsdelivr.net/gh/bitquery/widgets@v1.3.8/dist/assets/css/widgets.css"
    />
    <link
      rel="stylesheet"
      href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css"
      integrity="sha384-Gn5384xqQ1aoWXA+058RXPxPg6fy4IWvTNh0E263XmFcJlSAwiGgFAW/dAiS6JXm"
      crossorigin="anonymous"
    />
    <script src="https://cdn.jsdelivr.net/gh/bitquery/widgets@v1.3.8/dist/widgets.js"></script>
    <script
      src="https://code.jquery.com/jquery-3.2.1.slim.min.js"
      integrity="sha384-KJ3o2DKtIkvYIK3UENzmM7KCkRr/rE9/Qpg6aAZGJwFDMVNA/GpGFF93hXpG5KkN"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.12.9/umd/popper.min.js"
      integrity="sha384-ApNbgh9B+Y1QKtv3Rn7W3mgPxhU9K/ScQsAP7hUibX39j7fakFPskvXusvfa0b4Q"
      crossorigin="anonymous"
    ></script>
    <script
      src="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/js/bootstrap.min.js"
      integrity="sha384-JZR6Spejh4U02d8jOt6vLEHfe/JQGiRRSQQxSfFWpi1MquVdAyjUar5+76PVCmYl"
      crossorigin="anonymous"
    ></script>
    <style></style>
  </head>
  <body>
    <div class="container">
      <div class="row" style="margin-top:20px; margin-bottom:20px">
        <div class="col">
          <div class="d-flex justify-content-center"  style="color: #E67E22;font-size: x-large; font-weight: bold;" >
              Tokens Analysis  
          </div>
        </div>
      </div>
      <div class="row" style="margin-top:20px; margin-bottom:20px">
        <div class="col-md-12">
          <div class="d-flex justify-content-center" style="font-weight: bold;">
            BSC Major AMM Active Address
          </div>
          <div id="bsc_address"></div>
        </div>
       </div>
      
  </body>

  <script>
  (function() {
  widgets.init('https://graphql.bitquery.io', '', {
    locale: 'en',
    theme: 'light'
  });
  var query = new widgets.query(`
{ethereum(network:bsc){
  smartContractCalls (date:{since:"2021-03-23"}
)
  {
    
 		 EPS:  count(uniq:callers,smartContractAddress:{is:"0xA7f552078dcC247C2684336020c03648500C6d9F"})
    DODO:count(uniq:callers,smartContractAddress:{is:"0x67ee3cb086f8a16f34bee3ca72fad36f7db929e2"})
    Pancake:count(uniq:callers,smartContractAddress:{is:"0x0e09fabb73bd3ade0a17ecc321fd13a19e81ce82"})
    Beefy:count(uniq:callers,smartContractAddress:{is:"0xB0BDBB9E507dBF55f4aC1ef6ADa3E216202e06FD"})
    Venus:count(uniq:callers,smartContractAddress:{is:"0xcf6bb5389c92bdda8a3747ddb454cb7a64626c63"})
    AUTO:count(uniq:callers,smartContractAddress:{is:"0xa184088a740c695e156f91f5cc086a06bb78b827"})
    Dego:count(uniq:callers,smartContractAddress:{is:"0x3fda9383a84c05ec8f7630fe10adf1fac13241cc"})
    Burger:count(uniq:callers,smartContractAddress:{is:"0xae9269f27437f0fcbc232d39ec814844a51d6b8f"})
    Lina:count(uniq:callers,smartContractAddress:{is:"0x762539b45a1dcce3d36d080f74d1aed37844b878"})
    Sparta:count(uniq:callers,smartContractAddress:{is:"0xe4ae305ebe1abe663f261bc00534067c80ad677c"})
    
    date{date}
    
  }
}}
`);
  var wdts = new widgets.chartByTime('#eth_trade', query, 'ethereum.smartContractCalls', {
    "title": "Trades",
    "chartOptions": {
      "vAxes": {
        "0": {
          "title": "Active address",
          "scaleType": "log"
        },
        "1": {
          "title": "Active Address",
          "scaleType": "linear"
        },
      },
      "series": {
        "0": {
          "color": "#ffc107",
          "barWidth": "2",
          "pointsVisible": true,
          "pointShape": "round",
          "pointSize": "3",
          "targetAxisIndex": 0,
          "type": "line"
        },
        "1": {
          "color": "#28a745",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
        "2": {
          "color": "#264653",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
        "3": {
          "color": "#2a9d8f",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
        "4": {
          "color": "#e7c15f",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
         "5": {
          "color": "#f4a261",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
         "6": {
          "color": "#e76f51",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
         "7": {
          "color": "#0077b6",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
         "8": {
          "color": "#90e0ef",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
         "9": {
          "color": "#e5989b",
          "lineWidth": "2",
          "pointsVisible": true,
          "pointShape": "diamond",
          "pointSize": "3",
          targetAxisIndex: 0,
          "type": "line"
        },
      },
      "seriesType": "line"
    },
    "dataOptions": [{
        title: {
          label: "Date",
          type: "datetime",
        },
        path: "date.date",
      },

      {
        "title": "Pancake Addres",
        "path": "Pancake",
      },
      {
        "title": "DoDo Address",
        "path": "DODO"
      },
       {
        "title": "EPS Address",
        "path": "EPS"
      },
       {
        "title": "Beefy Address",
        "path": "Beefy"
      },
      {
        "title": "Venus Address",
        "path": "Venus"
      },
       {
        "title": "Auto Address",
        "path": "AUTO"
      },
       {
        "title": "Dego Address",
        "path": "Dego"
      },
       {
        "title": "Burger Address",
        "path": "Burger"
      },
       {
        "title": "Lina Address",
        "path": "Lina"
      },
       {
        "title": "Sparta Address",
        "path": "Sparta"
      },
    ]
  });
  query.request({});
})();

  </script>
   </html>
