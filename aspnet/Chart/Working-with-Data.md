---
layout: post
title: Data binding| Chart  | ASP.NET Webforms | Syncfusion
description: Learn how to bind Chart with JSON data from a remote server or locally in client browser.
platform: aspnet
control: Chart
documentation: ug
---

# Working with Data

## Local Data

There are two ways to provide local data to chart.

1. You can bind the data to the chart by using the **DataSource** property of the series and then you need to map the X and Y value with the *XName* and *YName* properties respectively.

N> For the **OHLC** type series, you have to map four dataSource fields *High, Low, Open* and *Close* to bind the data source and for the **bubble** series you have to map the *Size* field along with the *XName* and *YName*. 


{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientLoad="onChartLoad"> 
    <Series>
       <ej:Series XName="Month" YName="Sales">
          
       </ej:Series>
    </Series>
</ej:Chart>
 
{% endhighlight %}


{% highlight js %}

var chartData = [
          { month: 'Jan', sales: 35 }, { month: 'Feb', sales: 28 },  { month: 'Mar', sales: 34 },
          { month: 'Apr', sales: 32 },{ month: 'May', sales: 40 },{ month: 'Jun', sales: 32 },
          { month: 'Jul', sales: 35 },  { month: 'Aug', sales: 55 }, { month: 'Sep', sales: 38 },
          { month: 'Oct', sales: 30 }, { month: 'Nov', sales: 25 }, { month: 'Dec', sales: 32 }];
          
    function onChartLoad(sender) {
        var data = GetData();
        sender.model.series[0].dataSource = chartData;
        sender.model.series[0].xName = "month";
        sender.model.series[0].yName = "sales";
    }
   
{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img1.png)

[Click](http://asp.syncfusion.com/demos/web/chart/localbinding.aspx) here to view the local data binding online demo sample.


2.You can also plot data to chart using **Points** option in the series. Using this property you can customize each and every point in the data.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientLoad="onchartload"> 
    <Series>
       <ej:Series XName="Month" YName="Sales">
          <%--Adding data points using x and y field of points--%>
           <Points>
               <ej:Points X="John" Y="10000"></ej:Points>
               <ej:Points X="Jake" Y="12000"></ej:Points>
               <ej:Points X="Petter" Y="18000"></ej:Points>
               <ej:Points X="James" Y="11000"></ej:Points>
               <ej:Points X="Mary" Y="9700"></ej:Points>
           </Points>
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img2.png)

## Remote Data

You can bind the remote data to the chart by using the **DataSource** and you can use the **Query** property of the series to filter the data from the dataSource.


{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
       <ej:Series XName="ShipCity" YName="Freight" Query="ej.Query().from('Orders').take(10)">
         
       </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

{% highlight csharp %}

this.Chart1.Series[0].DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";

{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img3.png)

[Click](http://asp.syncfusion.com/demos/web/chart/remotebinding.aspx) here to view the remote data binding online demo sample.	


## AngularJS Data Binding

Typically, you will assign data directly to chart using **dataSource** property of the series. In AngularJS, you need to bind the variable, which contains data in the AngularJS scope object, to the dataSource property as illustrated in the following code example,


I> Essential JS includes AngularJS directives for all controls in the **ej.widget.angular.min.js** script file. 

N> All the properties in EjChart supports one way AngularJS binding except inner array properties like **series.points[]**, **series.trendlines[]**. [Click](http://help.syncfusion.com/js/angularjs) here to know more about Essential AngularJS and the properties which support two way AngularJS binding in chart.  

{% highlight html %}

<html ng-app="syncApp">
<head>
    <script type="text/javascript" src="http://cdn.syncfusion.com/js/assets/external/jquery-2.1.4.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/angular.min.js"></script>
    <script src="https://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js"></script>
	<script src="https://cdn.syncfusion.com/{{ site.releaseversion }}/js/common/ej.widget.angular.min.js"></script>
</head>
<body ng-controller="Chart">    
  <div id="chartContainer" style="width:100%" ej-chart
               e-size-width="800px" e-size-height="600px" 
                             e-title-text="AngularJS Support" >				           
    <e-series>              
      <e-series e-name="John" e-dataSource=dataSource e-xName="Day" e-yName="John">					 
	  </e-series>
    <e-series e-name="Hendry"  e-dataSource=dataSource e-xName="Day" e-yName="Hendry">					   
	  </e-series>
    </e-series>
 </div>            
</body>
</html>

{% endhighlight %}


{% highlight js %}

       //Data source for chart.
        var obj = [
                { "Day": 1, "John": 57, "Henry": 43 },
                { "Day": 2, "John": 73, "Henry": 27 },
                { "Day": 3, "John": 49, "Henry": 51 },
                { "Day": 4, "John": 63, "Henry": 37 },
                { "Day": 5, "John": 44, "Henry": 56 },
                { "Day": 6, "John": 49, "Henry": 51 },
                { "Day": 7, "John": 61, "Henry": 39 },
                { "Day": 8, "John": 35, "Henry": 65 },
                { "Day": 9, "John": 45, "Henry": 55 },
                { "Day": 10, "John": 37, "Henry": 63 }
        ];
        
        angular.module('syncApp', ['ejangular'])
            .controller('Chart', function ($scope) {
                //Assigning data to the dataSource variable in the $scope object.
                $scope.dataSource = obj;
            });

{% endhighlight %}


![](Working-with-Data_images/Working-with-Data_img4.png)

[Click](http://ngjq.syncfusion.com/#/chart/line) here to view the AngularJS data binding online demo sample.	