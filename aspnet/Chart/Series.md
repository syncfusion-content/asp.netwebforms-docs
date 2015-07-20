---
layout: post
title: Series
description: series
platform: aspnet
control: Chart
documentation: ug
---

# Series

The Series property provides access to a collection of all series that are defined explicitly within a Chart control. Each series is assigned with series type and name. It contains collection of data point and each point contains x value and y value(s).

## Multiple Series

You can plot multipleseries on the same Chart. Series are defined by adding them to the "series" array and rendering order of each series can be controlled using the ZOrder properties of the series. Series with 0 as ZOrder renders first. 
{% highlight html %}
[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true"&gt;



           &lt;Series&gt;

             &lt;ej:Series Name="Gold"&gt;

                   &lt;Points&gt;

                        &lt;ej:Points  X="USA" Y="50"/&gt;

                        &lt;ej:Points  X="China" Y="40"/&gt;

                        &lt;ej:Points  X="Japan" Y="70"/&gt;

                        &lt;ej:Points  X="Australia" Y="60"/&gt;

                        &lt;ej:Points  X="France" Y="50"/&gt;

                        &lt;ej:Points  X="Germany" Y="40"/&gt;

                        &lt;ej:Points  X="Italy" Y="40"/&gt;

                        &lt;ej:Points  X="Sweden" Y="30"/&gt;

                    &lt;/Points&gt;

             &lt;/ej:Series&gt;

                &lt;ej:Series Name="Silver"&gt;

                   &lt;Points&gt;

                        &lt;ej:Points  X="USA" Y="70"/&gt;

                        &lt;ej:Points  X="China" Y="60"/&gt;

                        &lt;ej:Points  X="Japan" Y="40"/&gt;

                        &lt;ej:Points  X="Australia" Y="36"/&gt;

                        &lt;ej:Points  X="France" Y="25"/&gt;

                        &lt;ej:Points  X="Germany" Y="30"/&gt;

                        &lt;ej:Points  X="Italy" Y="35"/&gt;

                        &lt;ej:Points  X="Sweden" Y="30"/&gt;

                    &lt;/Points&gt;

             &lt;/ej:Series&gt;



         &lt;/Series&gt;



      &lt;/ej:Chart&gt;


{% endhighlight  %}


![](Series_images/Series_img1.png)
{:.image }


CommonSeriesOptions

You can specify the properties common to all series of the Chart in CommonSeriesOptions.
{% highlight html %}
 [ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true"&gt;

       &lt;CommonSeriesOptions Type="Column" Border-Width="2" Border-Color="black" /&gt;

           &lt;Series&gt;

             &lt;ej:Series Name="Gold"&gt;

                   &lt;Points&gt;

                        &lt;ej:Points  X="USA" Y="50"/&gt;

                        &lt;ej:Points  X="China" Y="40"/&gt;

                        &lt;ej:Points  X="Japan" Y="70"/&gt;

                        &lt;ej:Points  X="Australia" Y="60"/&gt;

                        &lt;ej:Points  X="France" Y="50"/&gt;

                        &lt;ej:Points  X="Germany" Y="40"/&gt;

                        &lt;ej:Points  X="Italy" Y="40"/&gt;

                        &lt;ej:Points  X="Sweden" Y="30"/&gt;

                    &lt;/Points&gt;

             &lt;/ej:Series&gt;

             &lt;ej:Series Name="Silver"&gt;

                   &lt;Points&gt;

                        &lt;ej:Points  X="USA" Y="70"/&gt;

                        &lt;ej:Points  X="China" Y="60"/&gt;

                        &lt;ej:Points  X="Japan" Y="40"/&gt;

                        &lt;ej:Points  X="Australia" Y="36"/&gt;

                        &lt;ej:Points  X="France" Y="25"/&gt;

                        &lt;ej:Points  X="Germany" Y="30"/&gt;

                        &lt;ej:Points  X="Italy" Y="35"/&gt;

                        &lt;ej:Points  X="Sweden" Y="30"/&gt;

                    &lt;/Points&gt;

             &lt;/ej:Series&gt;



         &lt;/Series&gt;



      &lt;/ej:Chart&gt;


{% endhighlight %}


![](Series_images/Series_img2.png)
{:.image }


## Combination Series

A combination Chart combines two or more Charts types in single Charts. For example, column series with line/spline series. There are some limitations in the combination series.

1. You cannot combine Column and Bar series
2. Pie, Doughnut Series cannot be used with other series types.


{% highlight html %}
[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true"&gt;

            &lt;PrimaryXAxis Title-Text="Month" /&gt;

            &lt;PrimaryYAxis Title-Text="Unit Sold" /&gt;

            &lt;CommonSeriesOptions Tooltip-Visible="true" EnableAnimation="True"/&gt;

            &lt;Axes&gt;

                &lt;ej:Axis MajorGridLines-Visible="false" OpposedPosition="true" AxisLine-Visible="false" RangePadding="Normal" Name="yAxis" LabelFormat="${value}" Title-Text="Total Transactions" /&gt;

            &lt;/Axes&gt;



            &lt;Series&gt;

                &lt;ej:Series Name="Unit Sold" XName="Xvalue" YName="YValue1"  Type="Column" EnableAnimation="True"&gt;&lt;/ej:Series&gt;

                &lt;ej:Series Name="Total Transaction" XName="Xvalue" YName="YValue2" Type="Line" EnableAnimation="True" YAxisName="yAxis"&gt;&lt;/ej:Series&gt;

            &lt;/Series&gt;

        &lt;/ej:Chart&gt;


{% endhighlight %}
{% highlight c# %}
[CS]

           List<CombinationChartData> data = new List<CombinationChartData>();



            data.Add(new CombinationChartData("Jan", 45, 1000));

            data.Add(new CombinationChartData("Feb", 100, 3000));

            data.Add(new CombinationChartData("March", 25, 1000));

            data.Add(new CombinationChartData("April", 100, 7000));

            data.Add(new CombinationChartData("May", 85, 5000));

            data.Add(new CombinationChartData("June", 145,7000));



            this.Chart1.DataSource = data;

            this.Chart1.DataBind();



  public class CombinationChartData

    {

        public CombinationChartData(string xval, double yvalue1, double yvalue2)

        {

            this.Xvalue = xval;

            this.YValue1 = yvalue1;

            this.YValue2 = yvalue2;

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



    }

{% endhighlight  %}

![](Series_images/Series_img3.png)
{:.image }


## Customize Series

You can customize the Chart series using fill, border width and border color. You can customize the series color using ‘Fill’ property of series, the stroke-width of the line, spline series using ‘Width’ property of series, the border color and width of the column/bar using ‘Border’ property of series and rect in the column/bar Chart using the ‘Fill’ and ‘Border’ property of each point.
{% highlight html %}
 [ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true"&gt;

       &lt;CommonSeriesOptions Type="Column" Border-Width="2" Border-Color="black" /&gt;

           &lt;Series&gt;

             &lt;ej:Series Name="Gold" Fill="#69D2E7"&gt;

                   &lt;Points&gt;

                        &lt;ej:Points  X="Jan" Y="45"/&gt;

                        &lt;ej:Points  X="Feb" Y="100" Border-Width="2" Border-Color="red"/&gt;

                        &lt;ej:Points  X="Mar" Y="25"/&gt;

                        &lt;ej:Points  X="Apr" Y="100"/&gt;

                        &lt;ej:Points  X="May" Y="85"/&gt;

                        &lt;ej:Points  X="June" Y="140"/&gt;



                    &lt;/Points&gt;

             &lt;/ej:Series&gt;

         &lt;/Series&gt;



      &lt;/ej:Chart&gt;





{% endhighlight  %}

![](Series_images/Series_img4.png)
{:.image }


## Data Labels

Data labels refer to the y values of data points that appear on each point. You can also display category names or custom text in data label by applying template for the dataLabel. HorizontalTextAlignment and VerticalTextAlignment in dataLabel is used to align the label. 
{% highlight html %}
 [ASP.NET] 



&lt;div id="template"&gt;

     &lt;div id="point"&gt;#point.x#:#point.y#%&lt;/div&gt;

 &lt;/div&gt;

<ej:Chart ID="Chart1" runat="server

              &lt;Series&gt;

             &lt;ej:Series Name="India" Fill="#8CC640" Marker-Visible="true" Marker-DataLabel-Visible="true" Marker-DataLabel-Template="template"&gt;

                    &lt;Points &gt;

                      &lt;ej:Points X="2006" Y="29.2"/&gt;  

                        &lt;ej:Points X="2007" Y="33.9"/&gt;  

                        &lt;ej:Points X="2008" Y="36"/&gt;  

                        &lt;ej:Points X="2009" Y="32.4"/&gt;

                        &lt;ej:Points X="2010" Y="32"/&gt; 



                 &lt;/Points&gt;

             &lt;/ej:Series&gt;

             &lt;ej:Series Name="Singapore" Fill="#CBA4C7" Marker-Visible="true" Marker-DataLabel-Visible="true" Marker-DataLabel-Shape="Rectangle"&gt;

                    &lt;Points &gt;

                        &lt;ej:Points  X="2006" Y="21.8"/&gt;  

                        &lt;ej:Points  X="2007" Y="24.9"/&gt;  

                        &lt;ej:Points  X="2008" Y="28.5"/&gt;  

                        &lt;ej:Points  X="2009" Y="27.2"/&gt;

                        &lt;ej:Points  X="2010" Y="23.4"/&gt;  

                    &lt;/Points&gt;

             &lt;/ej:Series&gt;        

         &lt;/Series&gt;



        &lt;/ej:Chart&gt;


{% endhighlight %}


![](Series_images/Series_img5.png)
{:.image }


ConnectorLine:

ConnectorLine in data Label is used to customize the line that connects the outside labels of the pie series in terms of color, height, width and type of line. 
{% highlight html %}
[ASP.NET] 

&lt;ej:Chart ID="Chart1" runat="server&gt;           

        &lt;Series&gt;

                &lt;ej:Series EnableAnimation="True" Marker-DataLabel-Visible="True" Marker-DataLabel-Shape="None" Marker-DataLabel-ConnectorLine-Type="Bezier" Marker-DataLabel-ConnectorLine-Color="Black" Name="Expenses" XName="Xvalue" YName="YValue1" Type="Pie" LabelPosition="OutsideExtended" EnableSmartLabels="True" StartAngle="145"&gt;

                &lt;Points&gt;

                 &lt;ej:points Text="Other Personal, 88.47%" X="Other Personnal" Y="94658" /&gt;

                 &lt;ej:points Text="Medical care, 8.49%" X="Medical care" Y="9090"/&gt;

                 &lt;ej:points Text="Housing, 2.40%" X="Housing" Y="2577"/&gt;

                  &lt;ej:points Text="Transportation, 0.44%" X="Transportation" Y="473"/&gt;

                  &lt;ej:points Text="Education, 0.11%" X="Education" Y="120"/&gt;

                  &lt;ej:points Text="Electronics, 0.06%" X="Electronics" Y="70"/&gt;

                    &lt;/Points&gt;

                &lt;/ej:Series&gt;

            &lt;/Series&gt;

        &lt;/ej:Chart&gt;





{% endhighlight %}

![](Series_images/Series_img6.png)
{:.image }


Data labels Rotation

_Data labels_ refer to the y values of data points, which appear on each point. You can rotate data labels with positive and negative angles using Angle property.



![](Series_images/Series_img7.png)
{:.image }

{% highlight html %}
[ASP.NET]

&lt;ej:Chart ID="Chart1" runat="server"&gt;



&lt;CommonSeriesOptions Type="Column" EnableAnimation="True" Marker-Border-Width="2" Marker-DataLabel-Visible="True" Marker-DataLabel-TextPosition="Middle" Marker-DataLabel-Angle="90" Marker-DataLabel-Font-Color="white" Marker-DataLabel-FontSize="16px" &gt;





&lt;/CommonSeriesOptions&gt;



   &lt;Series&gt;



&lt;ej:Series Name="Marketing"&gt;



&lt;Points &gt;   



 &lt;ej:Points X="Print Ads" Y="110"/&gt; 



 &lt;ej:Points X="Online Ads" Y="125"/&gt; 



 &lt;ej:Points X="Content Marketing" Y="95"/&gt; 



 &lt;ej:Points X="Tradeshows" Y="60"/&gt;



 &lt;/Points&gt;



&lt;/ej:Series&gt;



 &lt;/ej:Chart&gt;
{% endhighlight %}


