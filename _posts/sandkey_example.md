---
title: 'Introducing myself'
date: 2024-1-18
permalink: /posts/sandkey_example
tags:
  - 
---

      google.charts.load('current', {
        'packages': ['sankey']
      });
      google.charts.setOnLoadCallback(drawChart);

      function drawChart() {
        var data = new google.visualization.DataTable();
        data.addColumn('string', 'From');
        data.addColumn('string', 'To');
        data.addColumn('number', 'Weight');
        data.addRows([
          ['High School 1', 'CSUSM', 5],
          ['High School 1', 'UC San Diego', 7],
          ['High School 1', 'Community College', 10],
          ['High School 1', 'Harvard', 2],
          ['High School 1', 'MIT', 2],
          ['High School 2', 'CSUSM', 2],
          ['High School 2', 'MIT', 3],
          ['High School 2', 'UC San Diego', 9],
          ['High School 2', 'Community College', 2],
          ['High School 2', 'Yale', 2],
          ['High School 2', 'Harvard', 4]
        ]);

        // Sets chart options.
        var options = {
          width: 600,
        };

        // Instantiates and draws our chart, passing in some options.
        var chart = new google.visualization.Sankey(document.getElementById('sankey_basic'));
        chart.draw(data, options);
      }
