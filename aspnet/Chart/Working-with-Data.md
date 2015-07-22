---
layout: post
title: Working-with-Data
description: working with data
platform: aspnet
control: Chart
documentation: ug
---

# Working with Data

Chart gets data either locally or remotely. To populate the Chart with data, you can use the DataSource in series properties.

## Local Data

Essential Chart provides you an option to bind the data to the Chart using the DataSource property of the series. 
{% highlight html %}
[ASP.NET] 

// xName:  xName specifies the field in the datasource that provide the arguments for series.

// yName:  yName specifies the field in the datasource that provide the values for series.

  &lt;ej:Chart ID="Chart1" runat="server" Width="970" CanResize="true" Height="600"&gt;

            &lt;Series&gt;

                &lt;ej:Series Name="Product A" XName="Xvalue" YName="YValue1" &gt;&lt;/ej:Series&gt;

               &lt;ej:Series Name="Product B" XName="Xvalue" YName="YValue2"&gt; &lt;/ej:Series&gt;

               &lt;ej:Series Name="Product C" XName="Xvalue" YName="YValue3"&gt;&lt;/ej:Series&gt;

               &lt;/Series&gt;



        &lt;/ej:Chart&gt;
{% endhighlight  %}
{% highlight c# %}
[CS]

          List<ChartData> data = new List<ChartData>();



            data.Add(new ChartData("CHEESE BURGER", 100, 15, 15));

            data.Add(new ChartData("PIZZA", 100, 15, 9));

            data.Add(new ChartData("CHICKEN NOODLE", 50, 4, 2));

            data.Add(new ChartData("YOGURT", 75, 10, 2));

            data.Add(new ChartData("BEEF SANDWICH", 125, 22, 13));



            this.Chart1.DataSource = data;

            this.Chart1.DataBind();



public class ChartData

    {

        public ChartData(string xval, double yvalue1, double yvalue2, double yvalue3)

        {

            this.Xvalue = xval;

            this.YValue1 = yvalue1;

            this.YValue2 = yvalue2;

            this.YValue3 = yvalue3;



        }

        public string Xvalue

        {

            get;

            set;

        }

        public double YValue1

        {

            get;

            set;

        }

        public double YValue2

        {

            get;

            set;

        }

        public double YValue3

        {

            get;

            set;

        }





    }
{% endhighlight %}


![](Working-with-Data_images/Working-with-Data_img1.png)
{:.image }


## Remote Data

You can bind the Essential Chart to remote data using DataManager and the Query in series that is used to retrieve the data by creating queries. Data manager supports the following types of data binding.

1. JSON
2. Web Services
3. oData

The following code example illustrates binding Essential Chart to oData service.   
{% highlight html %}
[ASP.NET] 

&lt;ej:Chart ID="Chart1" OnClientLoad="onchartload"&gt;

        &lt;Series&gt;

            &lt;ej:Series Name="Country" Type="Column"/&gt;

        &lt;/Series&gt;

    &lt;/ej:Chart&gt;

[Script] 

    &lt;script type="text/javascript" language="javascript"&gt;



        var dataManger = new ej.DataManager({

           url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"



            });

            // Query creation

            var query = ej.Query().from("Orders").take(10);



            function onchartload(sender) {

                sender.model.series[0].dataSource = dataManger;

                sender.model.series[0].xName = "ShipCity";

                sender.model.series[0].yName = "Freight";

                sender.model.series[0].query = query;

            }

 &lt;/script&gt;




{% endhighlight  %}
![](Working-with-Data_images/Working-with-Data_img2.png)
{:.image }


