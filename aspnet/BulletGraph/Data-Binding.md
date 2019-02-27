---
layout: post
title: Data Binding | BulletGraph | ASP.NET Webforms | Syncfusion
description: data binding
platform: aspnet
control: BulletGraph
documentation: ug
---

# Data Binding

Bullet Graph supports binding JSON data from a remote server or data created in client-side. You can use the Fields property to customize the data bound with Bullet Graph.

## Local Data

Data available in client-side (local data) can be bound with Bullet Graph using Fields property. This property provides option to specify data source, fields representing progress measure bar value, comparative measure value and category value.
{% tabs %}

{% highlight c# %}


    [Serializable]
    public class BulletData

    {

        public double BulletValue

        { get; set; }

        public double ComparisonValue

        { get; set; }

        public string Category

        { get; set; }

    }



            List<BulletData> data = new List<BulletData>();

            data.Add(new BulletData() { BulletValue=9.5, ComparisonValue=7.5, Category="2001"  });

            data.Add(new BulletData() { BulletValue = 9.5, ComparisonValue = 5, Category = "2002" });

            this.BulletGraph1.DataSource = data;

            this.BulletGraph1.DataBind();
{% endhighlight %}

{% highlight html %}

<ej:BulletGraph ID="BulletGraph1" Width="600px" Height="120px" runat="server">

            <QuantitativeScaleSettings>

                <Location X="50" Y="20" />

            </QuantitativeScaleSettings>

            <Fields CategoryField="Category" ComparativeMeasureField="ComparisonValue" FeatureMeasureField="BulletValue" />

        </ej:BulletGraph>


{% endhighlight %}

{% endtabs %}
The following screenshot displays Bullet Graph with local data generated in code-behind.

![](Data-Binding_images/Data-Binding_img1.png)



## Remote Data

Bullet Graph provides option to bind data from a remote server using ejDataManager as data source in fields property. A query object should also be passed to query property when using data manager as data source.

{% highlight html %}


        <ej:BulletGraph ID="BulletGraph1" QualitativeRangeSize="60" Width="600px" Height="120px" runat="server">

            <QuantitativeScaleSettings Minimum="5" Maximum="45" Interval="10">

                <Location X="50" Y="20" />

            </QuantitativeScaleSettings>

            <QualitativeRanges>

                <ej:QualitativeRanges RangeEnd="25" />

                <ej:QualitativeRanges RangeEnd="37" />

                <ej:QualitativeRanges RangeEnd="45" />

            </QualitativeRanges>

            <Fields CategoryField="ProductID" ComparativeMeasureField="Quantity" FeatureMeasureField="UnitPrice" />

        </ej:BulletGraph>



        <script type="text/javascript">

            //Creating data manager instance

            var dataManger = new ej.DataManager({

                url: "http://mvc.syncfusion.com/Services/Northwnd.svc/"

            });



            // Query creation

            var query = ej.Query().from("Order_Details").take(3).where("UnitPrice", ej.FilterOperators.greaterThan, 18, false)

                .where("UnitPrice", ej.FilterOperators.lessThanOrEqual, 40, false)

                .where("Quantity", ej.FilterOperators.greaterThan, 5, false)

                .where("Quantity", ej.FilterOperators.lessThanOrEqual, 45, false);



            $("#BulletGraph1").ejBulletGraph({



                fields: {

                    dataSource: dataManger,

                    query: query,

                }

            });

        </script>

{% endhighlight  %}

The following screenshot displays a Bullet Graph bounded with data from a remote server

![](Data-Binding_images/Data-Binding_img2.png)



