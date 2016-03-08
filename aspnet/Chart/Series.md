---
layout: post
title: Series | Chart | ASP.NET Webforms | Syncfusion
description: series
platform: aspnet
control: Chart
documentation: ug
---

# Series

The Series property provides access to a collection of all series that are defined explicitly within a Chart control. Each series is assigned with series type and name. It contains collection of data point and each point contains x value and y value(s).

## Multiple Series

You can plot multiple series on the same Chart. Series are defined by adding them to the "series" array and rendering order of each series can be controlled using the ZOrder properties of the series. Series with 0 as ZOrder renders first. 
{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">



           <Series>

             <ej:Series Name="Gold">

                   <Points>

                        <ej:Points  X="USA" Y="50"/>

                        <ej:Points  X="China" Y="40"/>

                        <ej:Points  X="Japan" Y="70"/>

                        <ej:Points  X="Australia" Y="60"/>

                        <ej:Points  X="France" Y="50"/>

                        <ej:Points  X="Germany" Y="40"/>

                        <ej:Points  X="Italy" Y="40"/>

                        <ej:Points  X="Sweden" Y="30"/>

                    </Points>

             </ej:Series>

                <ej:Series Name="Silver">

                   <Points>

                        <ej:Points  X="USA" Y="70"/>

                        <ej:Points  X="China" Y="60"/>

                        <ej:Points  X="Japan" Y="40"/>

                        <ej:Points  X="Australia" Y="36"/>

                        <ej:Points  X="France" Y="25"/>

                        <ej:Points  X="Germany" Y="30"/>

                        <ej:Points  X="Italy" Y="35"/>

                        <ej:Points  X="Sweden" Y="30"/>

                    </Points>

             </ej:Series>



         </Series>



      </ej:Chart>


{% endhighlight  %}


![](Series_images/Series_img1.png)



### CommonSeriesOptions

You can specify the properties common to all series of the Chart in CommonSeriesOptions.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">

       <CommonSeriesOptions Type="Column" Border-Width="2" Border-Color="black" />

           <Series>

             <ej:Series Name="Gold">

                   <Points>

                        <ej:Points  X="USA" Y="50"/>

                        <ej:Points  X="China" Y="40"/>

                        <ej:Points  X="Japan" Y="70"/>

                        <ej:Points  X="Australia" Y="60"/>

                        <ej:Points  X="France" Y="50"/>

                        <ej:Points  X="Germany" Y="40"/>

                        <ej:Points  X="Italy" Y="40"/>

                        <ej:Points  X="Sweden" Y="30"/>

                    </Points>

             </ej:Series>

             <ej:Series Name="Silver">

                   <Points>

                        <ej:Points  X="USA" Y="70"/>

                        <ej:Points  X="China" Y="60"/>

                        <ej:Points  X="Japan" Y="40"/>

                        <ej:Points  X="Australia" Y="36"/>

                        <ej:Points  X="France" Y="25"/>

                        <ej:Points  X="Germany" Y="30"/>

                        <ej:Points  X="Italy" Y="35"/>

                        <ej:Points  X="Sweden" Y="30"/>

                    </Points>

             </ej:Series>



         </Series>



      </ej:Chart>


{% endhighlight %}


![](Series_images/Series_img2.png)



## Combination Series

A combination Chart combines two or more Charts types in single Charts. For example, column series with line/spline series. There are some limitations in the combination series.

1. You cannot combine Column and Bar series
2. Pie, Doughnut Series cannot be used with other series types.

{% tabs %}

{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">

            <PrimaryXAxis Title-Text="Month" />

            <PrimaryYAxis Title-Text="Unit Sold" />

            <CommonSeriesOptions Tooltip-Visible="true" EnableAnimation="True"/>

            <Axes>

                <ej:Axis MajorGridLines-Visible="false" OpposedPosition="true" AxisLine-Visible="false" RangePadding="Normal" Name="yAxis" LabelFormat="${value}" Title-Text="Total Transactions" />

            </Axes>



            <Series>

                <ej:Series Name="Unit Sold" XName="Xvalue" YName="YValue1"  Type="Column" EnableAnimation="True"></ej:Series>

                <ej:Series Name="Total Transaction" XName="Xvalue" YName="YValue2" Type="Line" EnableAnimation="True" YAxisName="yAxis"></ej:Series>

            </Series>

        </ej:Chart>


{% endhighlight %}
{% highlight c# %}


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

{% endtabs %}

![](Series_images/Series_img3.png)



## Customize Series

You can customize the Chart series using fill, border width and border color. You can customize the series color using ‘Fill’ property of series, the stroke-width of the line, spline series using ‘Width’ property of series, the border color and width of the column/bar using ‘Border’ property of series and rect in the column/bar Chart using the ‘Fill’ and ‘Border’ property of each point.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">

       <CommonSeriesOptions Type="Column" Border-Width="2" Border-Color="black" />

           <Series>

             <ej:Series Name="Gold" Fill="#69D2E7">

                   <Points>

                        <ej:Points  X="Jan" Y="45"/>

                        <ej:Points  X="Feb" Y="100" Border-Width="2" Border-Color="red"/>

                        <ej:Points  X="Mar" Y="25"/>

                        <ej:Points  X="Apr" Y="100"/>

                        <ej:Points  X="May" Y="85"/>

                        <ej:Points  X="June" Y="140"/>



                    </Points>

             </ej:Series>

         </Series>



      </ej:Chart>





{% endhighlight  %}

![](Series_images/Series_img4.png)



## Data Labels

Data labels refer to the y values of data points that appear on each point. You can also display category names or custom text in data label by applying template for the dataLabel. HorizontalTextAlignment and VerticalTextAlignment in dataLabel is used to align the label. 
{% highlight html %}




<div id="template">

     <div id="point">#point.x#:#point.y#%</div>

 </div>

<ej:Chart ID="Chart1" runat="server

              <Series>

             <ej:Series Name="India" Fill="#8CC640" Marker-Visible="true" Marker-DataLabel-Visible="true" Marker-DataLabel-Template="template">

                    <Points >

                      <ej:Points X="2006" Y="29.2"/>  

                        <ej:Points X="2007" Y="33.9"/>  

                        <ej:Points X="2008" Y="36"/>  

                        <ej:Points X="2009" Y="32.4"/>

                        <ej:Points X="2010" Y="32"/> 



                 </Points>

             </ej:Series>

             <ej:Series Name="Singapore" Fill="#CBA4C7" Marker-Visible="true" Marker-DataLabel-Visible="true" Marker-DataLabel-Shape="Rectangle">

                    <Points >

                        <ej:Points  X="2006" Y="21.8"/>  

                        <ej:Points  X="2007" Y="24.9"/>  

                        <ej:Points  X="2008" Y="28.5"/>  

                        <ej:Points  X="2009" Y="27.2"/>

                        <ej:Points  X="2010" Y="23.4"/>  

                    </Points>

             </ej:Series>        

         </Series>



        </ej:Chart>


{% endhighlight %}


![](Series_images/Series_img5.png)



### ConnectorLine:

ConnectorLine in data Label is used to customize the line that connects the outside labels of the pie series in terms of color, height, width and type of line. 
{% highlight html %}


<ej:Chart ID="Chart1" runat="server>           

        <Series>

                <ej:Series EnableAnimation="True" Marker-DataLabel-Visible="True" Marker-DataLabel-Shape="None" Marker-DataLabel-ConnectorLine-Type="Bezier" Marker-DataLabel-ConnectorLine-Color="Black" Name="Expenses" XName="Xvalue" YName="YValue1" Type="Pie" LabelPosition="OutsideExtended" EnableSmartLabels="True" StartAngle="145">

                <Points>

                 <ej:points Text="Other Personal, 88.47%" X="Other Personnal" Y="94658" />

                 <ej:points Text="Medical care, 8.49%" X="Medical care" Y="9090"/>

                 <ej:points Text="Housing, 2.40%" X="Housing" Y="2577"/>

                  <ej:points Text="Transportation, 0.44%" X="Transportation" Y="473"/>

                  <ej:points Text="Education, 0.11%" X="Education" Y="120"/>

                  <ej:points Text="Electronics, 0.06%" X="Electronics" Y="70"/>

                    </Points>

                </ej:Series>

            </Series>

        </ej:Chart>





{% endhighlight %}

![](Series_images/Series_img6.png)



### Data labels Rotation

Data labels refer to the y values of data points, which appear on each point. You can rotate data labels with positive and negative angles using Angle property.



![](Series_images/Series_img7.png)


{% highlight html %}


<ej:Chart ID="Chart1" runat="server">



<CommonSeriesOptions Type="Column" EnableAnimation="True" Marker-Border-Width="2" Marker-DataLabel-Visible="True" Marker-DataLabel-TextPosition="Middle" Marker-DataLabel-Angle="90" Marker-DataLabel-Font-Color="white" Marker-DataLabel-FontSize="16px" >





</CommonSeriesOptions>



   <Series>



<ej:Series Name="Marketing">



<Points >   



 <ej:Points X="Print Ads" Y="110"/> 



 <ej:Points X="Online Ads" Y="125"/> 



 <ej:Points X="Content Marketing" Y="95"/> 



 <ej:Points X="Tradeshows" Y="60"/>



 </Points>



</ej:Series>



 </ej:Chart>
{% endhighlight %}


