---
title       : Pe'ah Garden stats
subtitle    : Results for 2014
author      : Scott Gaul
job         : Pe'ah stats person
framework   : minimal      # 
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
ext_widgets : {rCharts: ["libraries/nvd3", "libraries/morris"]} 
mode        : selfcontained # {standalone, draft}
---

## 2014 overall results

We had great results in 2014! While [2013 had the lowest yields ever](http://sgaul.github.io/peah2013/), this year had the highest yields ever (at least, as far as the historical record stands).  

We distributed 2,367 pounds of vegetables or about 225,000 calories - roughly three months of food for an adult. This is almost three times last year's total and 40 percent higher than the previous best year.





<div id = 'chart1' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart1()
    });
    function drawchart1(){  
      var opts = {
 "dom": "chart1",
"width":    500,
"height":    300,
"x": "Year",
"y": "Calories",
"type": "discreteBarChart",
"id": "chart1" 
},
        data = [
 {
 "Year": 2002,
"Pounds":        1273.25,
"Calories": 114403.9329167 
},
{
 "Year": 2003,
"Pounds":          778.5,
"Calories":       86920.57 
},
{
 "Year": 2004,
"Pounds":        1302.25,
"Calories":      140183.85 
},
{
 "Year": 2005,
"Pounds":         1392.5,
"Calories":      151554.28 
},
{
 "Year": 2006,
"Pounds":        1321.25,
"Calories":     134382.865 
},
{
 "Year": 2007,
"Pounds":        1686.25,
"Calories":  153063.073334 
},
{
 "Year": 2008,
"Pounds":            898,
"Calories":    90317.34125 
},
{
 "Year": 2009,
"Pounds":           1028,
"Calories": 100385.8316667 
},
{
 "Year": 2010,
"Pounds":         911.75,
"Calories":      84708.455 
},
{
 "Year": 2011,
"Pounds":           1269,
"Calories":      147313.92 
},
{
 "Year": 2012,
"Pounds":        1901.23,
"Calories":    164506.3552 
},
{
 "Year": 2013,
"Pounds":            608,
"Calories":      67887.755 
},
{
 "Year": 2014,
"Pounds":           2367,
"Calories":      225292.96 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        chart
  .forceY([      0, 1.7e+05 ])
  .margin({
 "left":     80 
})
          
        chart.xAxis
  .axisLabel("Year")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Calories")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

Here is the same result in pounds harvested. 


<div id = 'chart2' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart2()
    });
    function drawchart2(){  
      var opts = {
 "dom": "chart2",
"width":    500,
"height":    300,
"x": "Year",
"y": "Pounds",
"type": "discreteBarChart",
"id": "chart2" 
},
        data = [
 {
 "Year": 2002,
"Pounds":        1273.25,
"Calories": 114403.9329167 
},
{
 "Year": 2003,
"Pounds":          778.5,
"Calories":       86920.57 
},
{
 "Year": 2004,
"Pounds":        1302.25,
"Calories":      140183.85 
},
{
 "Year": 2005,
"Pounds":         1392.5,
"Calories":      151554.28 
},
{
 "Year": 2006,
"Pounds":        1321.25,
"Calories":     134382.865 
},
{
 "Year": 2007,
"Pounds":        1686.25,
"Calories":  153063.073334 
},
{
 "Year": 2008,
"Pounds":            898,
"Calories":    90317.34125 
},
{
 "Year": 2009,
"Pounds":           1028,
"Calories": 100385.8316667 
},
{
 "Year": 2010,
"Pounds":         911.75,
"Calories":      84708.455 
},
{
 "Year": 2011,
"Pounds":           1269,
"Calories":      147313.92 
},
{
 "Year": 2012,
"Pounds":        1901.23,
"Calories":    164506.3552 
},
{
 "Year": 2013,
"Pounds":            608,
"Calories":      67887.755 
},
{
 "Year": 2014,
"Pounds":           2367,
"Calories":      225292.96 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        chart
  .forceY([      0,   1700 ])
  .margin({
 "left":     80 
})
          
        chart.xAxis
  .axisLabel("Year")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Pounds")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>


## 2014 individual results

Individual results for the year are listed in the table below. (Some gardeners harvested more than one crop for the pe'ah contribution, so each crop is shown in that case. We also tracked a few plots in the same column, so I've lumped those together, i.e. plots 6 and 11 are 'Masha and Dan and Len and Avery').  

<!-- html table generated in R 3.0.2 by xtable 1.7-4 package -->
<!-- Tue Oct 14 11:30:04 2014 -->
<table border=1>
<tr> <th> Name </th> <th> Crop </th> <th> Pounds </th> <th> Calories </th>  </tr>
  <tr> <td> Avi and Michelle </td> <td> broccoli </td> <td align="right"> 18 </td> <td align="right"> 2701 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> collards </td> <td align="right"> 10 </td> <td align="right"> 1362 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> cucumbers </td> <td align="right"> 190 </td> <td align="right"> 12922 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> lettuce </td> <td align="right"> 34 </td> <td align="right"> 2349 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> parsley </td> <td align="right"> 4 </td> <td align="right"> 654 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> tomatoes </td> <td align="right"> 0 </td> <td align="right"> 34 </td> </tr>
  <tr> <td> Avi and Michelle </td> <td> zucchini </td> <td align="right"> 8 </td> <td align="right"> 545 </td> </tr>
  <tr> <td> Community </td> <td> beans </td> <td align="right"> 20 </td> <td align="right"> 2780 </td> </tr>
  <tr> <td> Community </td> <td> beets </td> <td align="right"> 2 </td> <td align="right"> 488 </td> </tr>
  <tr> <td> Community </td> <td> cabbage </td> <td align="right"> 7 </td> <td align="right"> 794 </td> </tr>
  <tr> <td> Community </td> <td> peppers </td> <td align="right"> 10 </td> <td align="right"> 863 </td> </tr>
  <tr> <td> Community </td> <td> tomatoes </td> <td align="right"> 50 </td> <td align="right"> 3405 </td> </tr>
  <tr> <td> Community </td> <td> zucchini </td> <td align="right"> 40 </td> <td align="right"> 2906 </td> </tr>
  <tr> <td> Dalton and Larry </td> <td> collards </td> <td align="right"> 22 </td> <td align="right"> 2996 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> beets </td> <td align="right"> 120 </td> <td align="right"> 23426 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> corn </td> <td align="right"> 3 </td> <td align="right"> 1446 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> parsley </td> <td align="right"> 2 </td> <td align="right"> 327 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> peppers </td> <td align="right"> 20 </td> <td align="right"> 1816 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> squash </td> <td align="right"> 13 </td> <td align="right"> 944 </td> </tr>
  <tr> <td> Holly / Deb / Toni / Community </td> <td> tomatoes </td> <td align="right"> 2 </td> <td align="right"> 102 </td> </tr>
  <tr> <td> Holly and Deb </td> <td> peppers </td> <td align="right"> 56 </td> <td align="right"> 5085 </td> </tr>
  <tr> <td> Holly and Deb </td> <td> tomatoes </td> <td align="right"> 1 </td> <td align="right"> 68 </td> </tr>
  <tr> <td> Holly and Deb and Rabbi and Janice </td> <td> peppers </td> <td align="right"> 55 </td> <td align="right"> 4971 </td> </tr>
  <tr> <td> Jennifer </td> <td> lettuce </td> <td align="right"> 85 </td> <td align="right"> 5788 </td> </tr>
  <tr> <td> Jennifer </td> <td> peppers </td> <td align="right"> 5 </td> <td align="right"> 454 </td> </tr>
  <tr> <td> Jennifer </td> <td> tomatoes </td> <td align="right"> 20 </td> <td align="right"> 1362 </td> </tr>
  <tr> <td> Julie and David </td> <td> cucumbers </td> <td align="right"> 1 </td> <td align="right"> 85 </td> </tr>
  <tr> <td> Julie and David </td> <td> kale </td> <td align="right"> 81 </td> <td align="right"> 18444 </td> </tr>
  <tr> <td> Julie and David </td> <td> lettuce </td> <td align="right"> 8 </td> <td align="right"> 545 </td> </tr>
  <tr> <td> Julie and David </td> <td> zucchini </td> <td align="right"> 68 </td> <td align="right"> 4940 </td> </tr>
  <tr> <td> Len and Averay and Sue and Scott and Madeline </td> <td> beans </td> <td align="right"> 72 </td> <td align="right"> 10098 </td> </tr>
  <tr> <td> Len and Averay and Sue and Scott and Madeline </td> <td> zucchini </td> <td align="right"> 27 </td> <td align="right"> 1961 </td> </tr>
  <tr> <td> Len and Avery </td> <td> beans </td> <td align="right"> 3 </td> <td align="right"> 422 </td> </tr>
  <tr> <td> Len and Avery </td> <td> peppers </td> <td align="right"> 2 </td> <td align="right"> 136 </td> </tr>
  <tr> <td> Len and Avery </td> <td> squash </td> <td align="right"> 13 </td> <td align="right"> 944 </td> </tr>
  <tr> <td> Len and Avery </td> <td> tomatoes </td> <td align="right"> 53 </td> <td align="right"> 3609 </td> </tr>
  <tr> <td> Len and Avery </td> <td> zucchini </td> <td align="right"> 89 </td> <td align="right"> 6447 </td> </tr>
  <tr> <td> Masha and Dan </td> <td> tomatoes </td> <td align="right"> 52 </td> <td align="right"> 3507 </td> </tr>
  <tr> <td> Masha and Dan and Len and Avery </td> <td> tomatoes </td> <td align="right"> 269 </td> <td align="right"> 18336 </td> </tr>
  <tr> <td> Phil and Raffaella </td> <td> cabbage </td> <td align="right"> 154 </td> <td align="right"> 17451 </td> </tr>
  <tr> <td> Phil and Raffaella </td> <td> zucchini </td> <td align="right"> 32 </td> <td align="right"> 2324 </td> </tr>
  <tr> <td> Priscilla and Leslie </td> <td> eggplant </td> <td align="right"> 32 </td> <td align="right"> 3459 </td> </tr>
  <tr> <td> Priscilla and Leslie </td> <td> zucchini </td> <td align="right"> 79 </td> <td align="right"> 5757 </td> </tr>
  <tr> <td> Rabbi + Janice </td> <td> peppers </td> <td align="right"> 7 </td> <td align="right"> 636 </td> </tr>
  <tr> <td> Rabbi + Janice </td> <td> squash </td> <td align="right"> 28 </td> <td align="right"> 2034 </td> </tr>
  <tr> <td> Shayla </td> <td> squash </td> <td align="right"> 275 </td> <td align="right"> 19958 </td> </tr>
  <tr> <td> Shayla </td> <td> zucchini </td> <td align="right"> 55 </td> <td align="right"> 3995 </td> </tr>
  <tr> <td> Toni </td> <td> cucumbers </td> <td align="right"> 37 </td> <td align="right"> 2520 </td> </tr>
  <tr> <td> Toni </td> <td> peppers </td> <td align="right"> 6 </td> <td align="right"> 590 </td> </tr>
   </table>

The full data for all years can be found [here](https://docs.google.com/spreadsheet/ccc?key=0AlYsW526rxsmdDhIVzM0VDYzRkdLOXlvcldfQkJtcnc&usp=sharing). 

We don't have individual results for plots the same as in prior years since results for some plots were tracked in the same column. 

We do have results for particular crops. We distributed 15 different kinds of vegetables this year, with tomatoes, squash and zucchini yielding the most (over 300 lbs of each). 


<div id = 'chart4' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart4()
    });
    function drawchart4(){  
      var opts = {
 "dom": "chart4",
"width":    500,
"height":    300,
"x": "Crop",
"y": "Pounds",
"type": "multiBarHorizontalChart",
"id": "chart4" 
},
        data = [
 {
 "Crop": "beans",
"Pounds":           94.5,
"Calories":       13299.93 
},
{
 "Crop": "beets",
"Pounds":          122.5,
"Calories":       23914.45 
},
{
 "Crop": "broccoli",
"Pounds":           17.5,
"Calories":         2701.3 
},
{
 "Crop": "cabbage",
"Pounds":         160.75,
"Calories":      18245.125 
},
{
 "Crop": "collards",
"Pounds":             32,
"Calories":         4358.4 
},
{
 "Crop": "corn",
"Pounds":           3.25,
"Calories":        1445.99 
},
{
 "Crop": "cucumbers",
"Pounds":            228,
"Calories":        15526.8 
},
{
 "Crop": "eggplant",
"Pounds":          31.75,
"Calories":        3459.48 
},
{
 "Crop": "kale",
"Pounds":          81.25,
"Calories":       18443.75 
},
{
 "Crop": "lettuce",
"Pounds":          127.5,
"Calories":        8682.75 
},
{
 "Crop": "parsley",
"Pounds":              6,
"Calories":         980.64 
},
{
 "Crop": "peppers",
"Pounds":         160.25,
"Calories":        14550.7 
},
{
 "Crop": "squash",
"Pounds":         328.75,
"Calories":        23880.4 
},
{
 "Crop": "tomatoes",
"Pounds":         446.75,
"Calories":      30423.675 
},
{
 "Crop": "zucchini",
"Pounds":          397.5,
"Calories":        28874.4 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        chart
  .showControls(false)
          
        chart.xAxis
  .axisLabel("Crop")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Pounds")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

The results by calories are similar, although a couple high-calorie crops like beets and kale show up with better results: 


<div id = 'chart5' class = 'rChart nvd3'></div>
<script type='text/javascript'>
 $(document).ready(function(){
      drawchart5()
    });
    function drawchart5(){  
      var opts = {
 "dom": "chart5",
"width":    500,
"height":    300,
"x": "Crop",
"y": "Calories",
"type": "multiBarHorizontalChart",
"id": "chart5" 
},
        data = [
 {
 "Crop": "beans",
"Pounds":           94.5,
"Calories":       13299.93 
},
{
 "Crop": "beets",
"Pounds":          122.5,
"Calories":       23914.45 
},
{
 "Crop": "broccoli",
"Pounds":           17.5,
"Calories":         2701.3 
},
{
 "Crop": "cabbage",
"Pounds":         160.75,
"Calories":      18245.125 
},
{
 "Crop": "collards",
"Pounds":             32,
"Calories":         4358.4 
},
{
 "Crop": "corn",
"Pounds":           3.25,
"Calories":        1445.99 
},
{
 "Crop": "cucumbers",
"Pounds":            228,
"Calories":        15526.8 
},
{
 "Crop": "eggplant",
"Pounds":          31.75,
"Calories":        3459.48 
},
{
 "Crop": "kale",
"Pounds":          81.25,
"Calories":       18443.75 
},
{
 "Crop": "lettuce",
"Pounds":          127.5,
"Calories":        8682.75 
},
{
 "Crop": "parsley",
"Pounds":              6,
"Calories":         980.64 
},
{
 "Crop": "peppers",
"Pounds":         160.25,
"Calories":        14550.7 
},
{
 "Crop": "squash",
"Pounds":         328.75,
"Calories":        23880.4 
},
{
 "Crop": "tomatoes",
"Pounds":         446.75,
"Calories":      30423.675 
},
{
 "Crop": "zucchini",
"Pounds":          397.5,
"Calories":        28874.4 
} 
]
  
      if(!(opts.type==="pieChart" || opts.type==="sparklinePlus")) {
        var data = d3.nest()
          .key(function(d){
            //return opts.group === undefined ? 'main' : d[opts.group]
            //instead of main would think a better default is opts.x
            return opts.group === undefined ? opts.y : d[opts.group];
          })
          .entries(data);
      }
      
      if (opts.disabled != undefined){
        data.map(function(d, i){
          d.disabled = opts.disabled[i]
        })
      }
      
      nv.addGraph(function() {
        var chart = nv.models[opts.type]()
          .x(function(d) { return d[opts.x] })
          .y(function(d) { return d[opts.y] })
          .width(opts.width)
          .height(opts.height)
         
        chart
  .showControls(false)
          
        chart.xAxis
  .axisLabel("Crop")

        
        
        chart.yAxis
  .tickFormat(function(d) {return d3.format(',.0f')(d)})
  .axisLabel("Calories")
      
       d3.select("#" + opts.id)
        .append('svg')
        .datum(data)
        .transition().duration(500)
        .call(chart);

       nv.utils.windowResize(chart.update);
       return chart;
      });
    };
</script>

## Comparison with prior years

It was a good year for many crops and not really a bad year for any particular crop. We had historically good yields for beets, cucumbers, beans and lettuce. Results for most other crops were above average. 

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2.png) 

If we compare the total yields by month to the average yields for all prior years, 2014 had higher yields in every month after June, with the biggest differences in July and August.

![plot of chunk unnamed-chunk-3](assets/fig/unnamed-chunk-3.png) 

Based on a week-by-week comparison with prior years, we do not appear to have had a noticeably longer growing season than in the past. Harvests continued well into October in some years.

![plot of chunk unnamed-chunk-4](assets/fig/unnamed-chunk-4.png) 

That's all!


```
Error: object 'opts_current' not found
```



