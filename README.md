<html>
  <head>
    <!-- Load the Google Charts library -->
    <script type="text/javascript" src="https://www.gstatic.com/charts/loader.js"></script>
    <script type="text/javascript">
      // Load the visualization library and set a callback function
      google.charts.load('current', {'packages':['corechart']});
      google.charts.setOnLoadCallback(drawChart);

      // Create and populate the data table
      function drawChart() {
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'Year');
        data.addColumn('number', 'China');
        data.addColumn('number', 'India');
        data.addColumn('number', 'Japan');
        data.addColumn('number', 'Russia');
        data.addColumn('number', 'United States');

        data.addRows([
          ['1980',  981,  698,  117,  139,  229],
          ['2020',  1394,  1326,  126,  142,  333],
          ['2050 (estimated)',  1273,  1684,  106,  124,  398]
        ]);

        // Set chart options
        var options = {
          title: 'Population Comparison',
          curveType: 'function',
          legend: { position: 'bottom' }
        };

        // Create the chart and bind it to the specified HTML element
        var chart = new google.visualization.LineChart(document.getElementById('chart_div'));
        chart.draw(data, options);
      }
    </script>
  </head>
  <body>
    <!-- Specify the chart container -->
    <div id="chart_div" style="width: 100%; height: 400px;"></div>
  </body>
</html>
