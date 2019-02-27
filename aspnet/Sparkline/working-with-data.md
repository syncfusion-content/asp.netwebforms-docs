---
layout: post
title: Data binding
description: Learn how to bind Sparkline with local data.
platform: aspnet
control: Sparkline
documentation: ug
---

# Working with Data

## Local Data

1. You can bind the data to the Sparkline by using `DataSource`property and then you need to map the **X** and **Y** value with `XName` and `YName` properties respectively.

{% highlight C# %}

public partial class Sparkline : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            // Create dataSource to sparkline
            List<SparklineData> data = new List<SparklineData>();
            data.Add(new SparklineData("Jan", 35));
            data.Add(new SparklineData("Feb", 28));
            data.Add(new SparklineData("Mar", 34));
            data.Add(new SparklineData("Apr", 32));
            data.Add(new SparklineData("May", 40));
            data.Add(new SparklineData("Jun", 32));
            data.Add(new SparklineData("Jul", 35));
            data.Add(new SparklineData("Aug", 55));
            data.Add(new SparklineData("Sep", 38));
            data.Add(new SparklineData("Oct", 30));
            data.Add(new SparklineData("Nov", 25));
            data.Add(new SparklineData("Dec", 32));
            this.Sparkline1.DataSource = data;
            this.DataBind();
       }
   }

   [Serializable]
    public class SparklineData {
        public string Month;
        public double Sales;
        public SparklineData(string month, double sales)
        {
            this.Month = month;
            this.Sales = sales;
        }
    }

{% endhighlight %}

{% highlight html %}

<ej:Sparkline ClientIDMode="Static" ID="Sparkline1" XName="Month" YName="Sales" runat="server">
</ej:Sparkline>

{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img1.png)

2. You can also bind an array of data to Sparkline by using `DataSource` property.

{% highlight html %}

public partial class Sparkline : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<SparklineData> data = new List<SparklineData>();
            Double[] y1 = { 2, 6, -1, 1, 12, 5, -2, 7, -3, 5, 8, 10};
            data.Add(new SparklineData(0, y1));
            this.Sparkline1.DataSource = data;
            this.Sparkline1.DataBind();
        }
    }

{% endhighlight %}

![](Working-with-Data_images/Working-with-Data_img2.png)


