<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="utf-8">
  <title>Dashboard</title>
</head>
<body>
  
  
  
  
    <div style="font-size: 60px; font-weight: 800; text-align: center;"> Dashboard </div>
    <!-- 月次 -->
    <div style="font-size: 40px; font-weight: 800;"> 月次 </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: center;">

        <!-- チーム別 棒グラフ -->
        <div id="teamMonthlyGraphs" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('teamMonthlyGraphs');
                    var data;
                    var options = {
                    title: '管掌別',
                    // width: 500,
                    height: 300,
                    animation: {
                        startup: true,
                        duration: 800,
                        easing: 'inAndOut'
                    },
                    isStacked: 'percent'
                    };
                    var chart = new google.visualization.ColumnChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '消化pt', '未達分'],
                    ['Team Wonder', 304, 298],
                    ['山口管掌', 174, 81],
                    ['新木管掌', 73, 104],
                    ['岸本管掌', 57, 50]
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 管掌別 円グラフ -->
        <div id="teamMonthlyPieChart" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var query = new google.visualization.Query('https://docs.google.com/spreadsheets/d/1pvWzFgnRfqcoiZ6ZMPvvw-P-WtGHYdJ8ZcsqSm7VYwc/edit?usp=sharing');
                    query.send(handleQueryResponse);
                    function handleQueryResponse(response) {
                        var target = document.getElementById('teamMonthlyPieChart');
                        var data;
                        var options = {
                        slices: {  3: {offset: 0.2}},
                        colors: ['#2595C7', '#2B7396', '#77B8DA', 'rgb(220, 57, 18)'],
                        // width: 500,
                        height: 300,
                        is3D: true
                        };
                        var chart = new google.visualization.PieChart(target);
                        data = response.getDataTable();
                        // data = new google.visualization.arrayToDataTable([
                        // ['Team', '成果'],
                        // ['山口管掌', 50],
                        // ['新木管掌', 20],
                        // ['岸本管掌', 10],
                        // ['未達分', 15],
                        // ]);
                        chart.draw(data, options);
                    }
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 個人別 棒グラフ -->
        <div id="individualMonthlyGraphs" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('individualMonthlyGraphs');
                    var data;
                    var options = {
                    title: '個人別',
                    // width: 500,
                    height: 300,
                    animation: {
                        startup: true,
                        duration: 800,
                        easing: 'inAndOut'
                    },
                    isStacked: 'percent'
                    };
                    var chart = new google.visualization.ColumnChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '消化pt', '未達分'],
                    ['山口', 102.975, 0],
                    ['野呂', 3.6, 38.4],
                    ['高橋', 59.25, 0],
                    ['新木', 61.075, 30.925],
                    ['豊田', 12, 44],
                    ['岸本', 53.25, 0],
                    ['木田', 4.05, 37.95],
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 個人別 円グラフ -->
        <div id="individualMonthlyPieChart" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('individualMonthlyPieChart');
                    var data;
                    var options = {
                    colors: ['#007042', '#0091C5', '#7C4B8D', '#E67928', '#212222', '#FFBB00', '#285294', 'rgb(220, 57, 18)'],
                    slices: {  7: {offset: 0.2}},
                    // width: 500,
                    height: 300,
                    is3D: true
                    };
                    var chart = new google.visualization.PieChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '成果'],
                    ['山口', 102.975],
                    ['野呂', 3.6],
                    ['高橋', 59.25],
                    ['新木', 61.075],
                    ['豊田', 12],
                    ['岸本', 53.25],
                    ['木田', 4.05],
                    ['未達分', 298],
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>
    </div>


    <!-- 半期 -->
    <div style="font-size: 40px; font-weight: 800;"> 半期 </div>
    <div style="display: flex; flex-wrap: wrap; justify-content: center;">

        <!-- チーム別 棒グラフ -->
        <div id="teamHalfTermGraphs" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('teamHalfTermGraphs');
                    var data;
                    var options = {
                    title: '管掌別',
                    // width: 500,
                    height: 300,
                    animation: {
                        startup: true,
                        duration: 800,
                        easing: 'inAndOut'
                    },
                    isStacked: 'percent'
                    };
                    var chart = new google.visualization.ColumnChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '消化pt', '未達分'],
                    ['Team Wonder', 2367.15, 1415],
                    ['山口管掌', 770.115, 579],
                    ['新木管掌', 774.0925, 288],
                    ['岸本管掌', 653.365, 547],
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 管掌別 円グラフ -->
        <div id="teamHalfTermPieChart" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('teamHalfTermPieChart');
                    var data;
                    var options = {
                    colors: ['#2595C7', '#2B7396', '#77B8DA', 'rgb(220, 57, 18)'],
                    slices: {  3: {offset: 0.2}},
                    // width: 500,
                    height: 300,
                    is3D: true
                    };
                    var chart = new google.visualization.PieChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '成果'],
                    ['山口管掌', 770.115],
                    ['新木管掌', 774.0925],
                    ['岸本管掌', 653.365],
                    ['未達分', 1415],
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 個人別 棒グラフ -->
        <div id="individualHalfTermGraphs" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('individualHalfTermGraphs');
                    var data;
                    var options = {
                    title: '個人別',
                    // width: 500,
                    height: 300,
                    animation: {
                        startup: true,
                        duration: 800,
                        easing: 'inAndOut'
                    },
                    isStacked: 'percent'
                    };
                    var chart = new google.visualization.ColumnChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '消化pt', '未達分'],
                    ['山口', 396.755, 180],
                    ['野呂', 62.26, 106],
                    ['高橋', 258.65, 59.35],
                    ['新木', 572.64, 0],
                    ['豊田', 201.4525, 135],
                    ['岸本', 280.94, 1.06],
                    ['木田', 111.195, 140.8],
                    ]);
                    chart.draw(data, options);
                }

                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>

        <!-- 個人別 円グラフ -->
        <div id="individualHalfTermPieChart" style="width: 45%;">
            <script src="https://www.gstatic.com/charts/loader.js"></script>
            <script>
                (function() {
                'use strict';

                function drawChart() {
                    var target = document.getElementById('individualHalfTermPieChart');
                    var data;
                    var options = {
                    colors: ['#007042', '#0091C5', '#7C4B8D', '#E67928', '#212222', '#FFBB00', '#285294', 'rgb(220, 57, 18)'],
                    slices: {  7: {offset: 0.2}},
                    // width: 500,
                    height: 300,
                    is3D: true
                    };
                    var chart = new google.visualization.PieChart(target);
                    data = new google.visualization.arrayToDataTable([
                    ['Team', '成果'],
                    ['山口', 396.755],
                    ['野呂', 62.26],
                    ['高橋', 258.65],
                    ['新木', 572.64],
                    ['豊田', 201.45],
                    ['岸本', 280.94],
                    ['木田', 111.195],
                    ['未達分', 1415],
                    ]);
                    chart.draw(data, options);
                }
                google.charts.load('48', {packages: ['corechart']});
                google.charts.setOnLoadCallback(drawChart);
                })();
            </script>
        </div>
    </div>
</body>
</html>
