---
layout: post
title: Axis | Chart | ASP.NET Webforms | Syncfusion
description: axis
platform: aspnet
control: Chart
documentation: ug
---

# Axis

Charts typically have two axes that are used to measure and categorize data: a vertical (y) axis, and a horizontal (x) axis. To make a Chart easier to understand, you can add axis titles, tick marks, and labels. You can also change the alignment of axis title and format the labels that are displayed on axes. By default horizontal (x) axis and vertical (y) axis gets added to the Chart with axis labels, gridlines, and tick lines. You can also customize these axis explicitly by adding axis title or removing gridlines, tick lines that are added to the axis by default.

Chart Axis supports the following types:

* Double
* DateTime
* Category
* Logarithmic

You can choose any of the Chart axis type using the” ValueType” property in axis. Axis calculates the range and interval automatically based on the series data points.


{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

        <PrimaryXAxis MajorTickLines-Visible="false" Title-Text="Country" />

        <PrimaryYAxis Title-Text="Production" />

 </ej:Chart>

{% endhighlight %}





![](Axis_images/Axis_img1.png) 



## Double 

By default the ValueType of the axis is double and it represents the numerical data.

{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

        <PrimaryXAxis MajorTickLines-Visible="false" Title-Text="Year" ValueType="Double"/>

          <series>

                <ej:Series>

                     <Points>

                        <ej:Points  X="200" Y="10"/>

                        <ej:Points  X="210" Y="13"/>

                        <ej:Points  X="220" Y="18"/>

                        <ej:Points  X="230" Y="13"/>

                        <ej:Points  X="240" Y="15"/>

                        <ej:Points  X="250" Y="13"/>

                        <ej:Points  X="260" Y="16"/>

                        <ej:Points  X="270" Y="10"/>

                        <ej:Points  X="280" Y="18"/>

                    </Points>

                </ej:Series>

            </series>

 </ej:Chart>



{% endhighlight %}



With the default auto range calculation, the range padding properties allows you to customize the automatic range calculation.

### Range Padding:

### None:

By default, the RangePadding for Numerical Axis is none.

The following screenshot displays a Chart’s x-axis with RangePadding set to None.



![](Axis_images/Axis_img2.png)



### Additional:

If RangePadding for Numerical Axis is set to Additional, the interval of the axis is added as padding.

The following screenshot illustrates a Chart’s x-axis with RangePadding set to Additional.



![](Axis_images/Axis_img3.png)



### Normal:

Normal RangePadding for a Numerical Axis is used mostly for the y-axis to have padding based on the Range calculation.

The following screenshot illustrates a Chart’s y-axis with RangePadding set to Normal.



![](Axis_images/Axis_img4.png)



### Round:

Round RangePadding for a Numerical Axis rounds the range of the Chart axis to the nearest possible value divisible by the interval.

The following screenshot illustrates a Chart’s x-axis with RangePadding set to Round.



![](Axis_images/Axis_img5.png)



## DateTime Axis

The DateTime Axis has a property IntervalType that sets the DateTime interval to one of the following:

* Days
* Hours
* Milliseconds
* Minutes 
* Months
* Seconds
* Years

The Interval property of DateTime Axis can be any double value based on the IntervalType.

{% tabs %}

{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">

            <PrimaryXAxis ValueType="Datetime" Title-Text="Years" /> 

             <Series>

               <ej:Series EnableAnimation="True" Type="Line" Name="Sales" XName="Xvalue" YName="YValue1">   

               </ej:Series>

              </Series>

        </ej:Chart>

{% endhighlight  %}

{% highlight c# %}


     this.Chart1.PrimaryXAxis.Range.Min = new DateTime(2000, 6, 1);

      this.Chart1.PrimaryXAxis.Range.Max = new DateTime(2010, 6, 1);

      this.Chart1.PrimaryXAxis.Range.Interval = 1;



      List<DatetimeData> data = new List<DatetimeData>();



      data.Add(new DatetimeData(new DateTime(2000, 06, 11), 10));

      data.Add(new DatetimeData(new DateTime(2002, 03, 07), 30));

      data.Add(new DatetimeData(new DateTime(2004, 03, 06), 15));

      data.Add(new DatetimeData(new DateTime(2006, 03, 30), 65));

      data.Add(new DatetimeData(new DateTime(2008, 03, 08), 90));

      data.Add(new DatetimeData(new DateTime(2010, 03, 08), 85));



      this.Chart1.DataSource = data;

      this.Chart1.DataBind();



[Serializable]

    public class DatetimeData

    {

        public DatetimeData(DateTime xval, double yvalue1)

        {

            this.Xvalue = xval;

            this.YValue1 = yvalue1;





        }

        public DateTime Xvalue

        {

            get;

            set;

        }

        public double YValue1

        {

            get;

            set;

        }

    }


{% endhighlight %}

{% endtabs %}


![](Axis_images/Axis_img6.png)



With the default auto range calculation, the RangePadding properties for date-time axis allow you to customize the automatic range calculation.

### Range Padding:

### None:

By default, the RangePadding for a DateTime Axis is None.

The following screenshot illustrates a Chart’s x-axis with RangePadding set to None. 



![](Axis_images/Axis_img7.png)



### Additional:

If RangePadding for DateTime Axis is set to Additional, the DateTime interval of the axis is added as padding.

The following screenshot illustrates a Chart’s x-axis with RangePadding set to Additional.



![](Axis_images/Axis_img8.png)



### Round:

Round RangePadding for a DateTime Axis rounds the range of the Chart axis to the nearest possible Date Time value.

The following screenshot illustrates a Chart’s x-axis with RangePadding set to Round.



![](Axis_images/Axis_img9.png)



## Category Axis

Category (x) axis displays text labels instead of numerical intervals. By default, the interval is 1 for which all the labels are displayed. To display every nth label, you can set that in Interval property. For example, to display every 2nd label, you can set Interval as 2

{% tabs %}

{% highlight html %}


<ej:Chart ID="Chart1" runat="server" >

    <PrimaryYAxis Title-Text="Medals"/>       

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

           </Series>

      </ej:Chart>


{% endhighlight %}

{% highlight c# %}


      this.Chart1.PrimaryYAxis.Range.Min =0;

      this.Chart1.PrimaryYAxis.Range.Max = 80;

      this.Chart1.PrimaryYAxis.Range.Interval = 20; 


{% endhighlight  %}

{% endtabs %}


![](Axis_images/Axis_img10.png) 



## Logarithmic Axis

An axis displaying a logarithmic scale is very useful when your data values span orders of magnitude. Log axis is enabled using ValueType property.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

         <PrimaryYAxis Title-Text="Medals" ValueType="Logarithmic"/>



           <Series>

             <ej:Series Name="India">

                   <Points>

                        <ej:Points  X="1990" Y="80"/>

                        <ej:Points  X="1991" Y="200"/>

                        <ej:Points  X="1992" Y="400"/>

                        <ej:Points  X="1993" Y="600"/>

                        <ej:Points  X="1994" Y="900"/>

                        <ej:Points  X="1995" Y="1400"/>

                        <ej:Points  X="1996" Y="2000"/>

                        <ej:Points  X="1997" Y="4000"/>

                        <ej:Points  X="1998" Y="6000"/>

                        <ej:Points  X="1999" Y="8000"/>

                        <ej:Points  X="2000" Y="9000"/>

                    </Points>

             </ej:Series>



         </Series>



      </ej:Chart>

{% endhighlight  %}


![](Axis_images/Axis_img11.png) 


### Chart Axis Properties:

Chart Axis Properties Table

<table>
<tr>
<th>
{{ '**Chart Axis Properties**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
DesiredIntervals</td><td>
An integer property used to indicate the preferred total number of intervals to be displayed for auto range calculation.</td></tr>
<tr>
<td>
MaximumLabels</td><td>
An Integer property used to indicate number of labels per 100 pixels. By default, 3 labels renders for 100 pixels of length.</td></tr>
</table>




## Multiple Axis

In cases of multiple series, a Chart can have multiple x and y axes to represent each series. The axes can be arranged in stacking or side-by-side mode. By default, the axes are arranged in side-by-side mode. In order to arrange the axis in a stacking mode, you can split the Chart into number of rows or columns using RowDefinitions and ColumnDefinitions and then you can place the required axis in the desired row and column. Heights of the vertical axes are customized using the RowHeight property in RowDefinitions and the widths of the horizontal axes are customized using ColumnWidth property in ColumnDefinitions. 
{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true">

            <RowDefinitions>

                <ej:RowDefinitions Unit="percentage" RowHeight="50" />

                <ej:RowDefinitions Unit="percentage" RowHeight="50" />

            </RowDefinitions>

            <PrimaryXAxis Title-Text="Month" />

            <PrimaryYAxis Title-Text="Temperature(Fahrenheit)" LabelFormat="{value}F" />

            <Axes>              

                <ej:Axis RowIndex="1" PlotOffset="20" OpposedPosition="false" Name="yAxis1"      

                       Title-Text="Temperature(Celsius)" />

            </Axes>            

           <Series>

             <ej:Series Name="Germany">

                  <Points>

                        <ej:Points  X="Jan" Y="15"/>

                        <ej:Points  X="Feb" Y="20"/>

                        <ej:Points  X="Mar" Y="35"/>

                        <ej:Points  X="Apr" Y="40"/>

                        <ej:Points  X="May" Y="30"/>

                        <ej:Points  X="Jun" Y="40"/>

                        <ej:Points  X="Jul" Y="43"/>

                        <ej:Points  X="Aug" Y="35"/>



                    </Points>

             </ej:Series>

             <ej:Series Name="India"  YAxisName="yAxis1">

                  <Points>

                        <ej:Points  X="Jan" Y="33"/>

                        <ej:Points  X="Feb" Y="31"/>

                        <ej:Points  X="Mar" Y="30"/>

                        <ej:Points  X="Apr" Y="28"/>

                        <ej:Points  X="May" Y="29"/>

                        <ej:Points  X="Jun" Y="30"/>

                        <ej:Points  X="Jul" Y="33"/>

                        <ej:Points  X="Aug" Y="32"/>



                    </Points>

             </ej:Series>



           </Series>

        </ej:Chart>




{% endhighlight  %}


![](Axis_images/Axis_img12.png)



In the above code, you can remove the RowDefinition and RowIndex from axis to arrange the axes in the side-by- side mode.



![](Axis_images/Axis_img13.png)



### Spanning Axis:

Charts having multiple series have multiple x and y axis to represent each series. By default, the axes are arranged in the corresponding row/column position. Spanning feature allows you to span the axis across multiple panes/rows. 
{% highlight html %}

<ej:Chart ID="Chart1" runat="server" Width="970" Height="600" CanResize="true" >

            <RowDefinitions>

                <ej:RowDefinitions RowHeight="25" Unit="percentage" />

                <ej:RowDefinitions RowHeight="25" Unit="percentage" />

                 <ej:RowDefinitions RowHeight="50" Unit="percentage" />

            </RowDefinitions>

            <PrimaryXAxis MajorGridLines-Visible="false" />

            <PrimaryYAxis RowIndex="0" RowSpan="2" Title-Text="Million USD" />

            <Axes>

                <ej:Axis RowIndex="1" RowSpan="2" Font-FontSize="14px" Name="y1SecondQuater" Title-Text="Million USD" />

                 <ej:Axis RowIndex="0"  RowSpan="3" Font-FontSize="14px" Name="y2SecondQuater" Title-Text="Million USD" />

            </Axes>

            <CommonSeriesOptions EnableAnimation="True"></CommonSeriesOptions>

             <Series>

                  <ej:Series Name="Gold" Type="Column">

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

             <ej:Series Name="India" Type="Line" YAxisName="y1SecondQuater" >

                    <Points>

                         <ej:Points  X="USA" Y="70"/>

                        <ej:Points  X="China" Y="60"/>

                        <ej:Points  X="Japan" Y="40"/>

                        <ej:Points  X="Australia" Y="30"/>

                        <ej:Points  X="France" Y="25"/>

                        <ej:Points  X="Germany" Y="40"/>

                        <ej:Points  X="Italy" Y="35"/>

                        <ej:Points  X="Sweden" Y="25"/>

                    </Points>

             </ej:Series>

             <ej:Series Name="Canada" Type="Spline" YAxisName="y2SecondQuater">

                    <Points>

                        <ej:Points  X="USA" Y="10"/>

                        <ej:Points  X="China" Y="19"/>

                        <ej:Points  X="Japan" Y="40"/>

                        <ej:Points  X="Australia" Y="70"/>

                        <ej:Points  X="France" Y="35"/>

                        <ej:Points  X="Germany" Y="82"/>

                        <ej:Points  X="Italy" Y="57"/>

                        <ej:Points  X="Sweden" Y="97"/>

                    </Points>

             </ej:Series>

              </Series>



        </ej:Chart>



{% endhighlight %}



![](Axis_images/Axis_img14.png)



## Axis Title

You can customize the ejChart Axis title text, font styles and color using “Title” property of axis.


{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

           <PrimaryXAxis Title-Text="Expenditure" Title-Font-Color="#AA3EEF" Title-Font-FontSize="16px" Title-Font-FontStyle="Normal" Title-Font-Opacity="1"  />

         <PrimaryYAxis Title-Text="Expense" Title-Font-Color="#AA3EEF" Title-Font-FontSize="16px" Title-Font-FontStyle="Normal" Title-Font-Opacity="1"  />      

      </ej:Chart>



{% endhighlight %}



![](Axis_images/Axis_img15.png)



### Trim Title

Essential Chart supports TrimmingAxisTitles with the properties, EnableTrim and MaximumTitleWidth. These are useful for shortening the lengthy titles. On hovering with the mouse, you can see the full title in the tooltip.

![](Axis_images/Axis_img16.png)



![](Axis_images/Axis_img17.png)



{% highlight html %}



<ej:Chart  ID="Chart1" runat="server">





    <PrimaryXAxis Title-Text ="List of countries which are using solar power in the year 2014" />



    <PrimaryYAxis Title-Text ="Measurements of Solar power used in different countries in the year 2014( in GW)" LabelFormat ="{value}GW"/>



    <CommonSeriesOptions Type="Column" EnableAnimation="true" Tooltip-Visible="true"/>



//.......



</ ej:Chart>


{% endhighlight %}

## Labels

The axis labels are present along the axis showing the value of the data it corresponds to. You can further customize the Chart axis labels using “Font” and “LabelFormat” properties of the axis.  

{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

      <PrimaryXAxis Title-Text="Expenditure" Font-Color="red" Font-FontSize="16px" 

            Font-FontStyle="Normal" Font-Opacity="1"  />

      <PrimaryYAxis Title-Text="Expense" Font-Color="red" Font-FontSize="16px" 

           Font-FontStyle="Normal" Font-Opacity="1"  />      

   </ej:Chart>



{% endhighlight %}

![](Axis_images/Axis_img18.png)



### LabelPlacement:

The category axis includes the LabelPlacement property that is used to set the labels of the axis between the tick lines or on the tick lines of the category axis. By default the LabelPlacement value for the category axis is BetweenTicks.

There are two types of LabelPlacement:

* BetweenTicks
* OnTicks

{% highlight html %}

<ej:Chart ID="Chart1" runat="server">

           <PrimaryXAxis Title-Text="'Countries' " LabelPlacement="onticks" Font-Color="red" 

            Font-FontSize="11px" />           

 </ej:Chart>




{% endhighlight %}


![](Axis_images/Axis_img19.png)





![](Axis_images/Axis_img20.png)



### Label Position

Axis labels can further be customized to render inside the chart area using the property LabelPosition. By default, it is set as Outside. This helps to display labels in a proper manner while multiple axes are used in the chart.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

   <PrimaryXAxis AxislabelPosition="Inside" />

   <PrimaryYAxis AxislabelPosition="Inside"/>

</ej:Chart>

{% endhighlight %}

![](Axis_images/Axis_img21.png) 

### Axis label trimming

Chart provides support for trimming y axis labels and x axis labels by using the properties EnableTrim and MaximumLabelWidth. These are used to show the lengthy labels in a shorter form. On mouse hover, it shows the full label in the tooltip.


{% highlight html %}
 

<ej:Chart ID="Chart1" runat="server" >

 <PrimaryXAxis  EnableTrim ="true" MaximumLabelWidth="34" />

 <PrimaryYAxis  EnableTrim="true" MaximumLabelWidth ="34" />

</ej:Chart>



{% endhighlight  %}

The following screenshot displays the Chart Axis with trimming

![](Axis_images/Axis_img22.png)



## Tick Marks

Tick lines are displayed horizontally and vertically in Chart axis based on the orientation of the axis.

### Major Tick Lines
It is rendered in Chart axis for each interval of axis range. By default, it is visible. You can collapse it by setting ‘Visible’ as false. You can customize the major tick lines width, opacity, and color.

### Minor Tick Lines

It is rendered between the major tick lines of Chart axis. To display MinorTickLines in Chart axis enable Visible property of “MinorTickLines” and set values to “MinorTicksPerInterval” in the respective axis. By default, it is invisible. You can customize the minor tick lines width, and color.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

    <PrimaryXAxis  MajorTickLines-Width="1.5" MajorTickLines-Visible="true" MajorTickLines-Size="6" MinorTickLines-Width="1" MinorTickLines-Size="4" MinorTicksPerInterval="5" />

    <PrimaryYAxis   MajorTickLines-Width="1.5" MajorTickLines-Visible="true"  MajorTickLines-Size="6" MinorTickLines-Width="1" MinorTickLines-Size="4" MinorTicksPerInterval="5" />                    

 </ej:Chart>


{% endhighlight %}


![](Axis_images/Axis_img23.png)



### Tick lines placement

You can customize tick lines and render them inside the chart area using the property TickLinesPosition. By default, it is set as outside. This property will be used when labels are inside.

{% highlight html %}



<ej:Chart ID="Chart1" runat="server">

   <PrimaryXAxis TickLinesPosition ="Inside" />

   <PrimaryYAxis TickLinesPosition ="Inside"/>

</ej:Chart>


{% endhighlight %}
![](Axis_images/Axis_img24.png)



## Grid Lines	

Grid lines are displayed in horizontal and vertical position in Chart area based on the intervals.

### Major Grid Lines

It is rendered in Chart area for each interval of axis range. By default, it is visible. You can collapse it by setting ‘Visible’ property to false. You can customize the major gridlines width, opacity, and dashArray of gridline.

### Minor Grid Lines

It is rendered between the major gridlines of Chart area.To display minor grid lines in Chart area enable Visible property of “MinorGridLines” and set values to “MinorTicksPerInterval” in the respective axis. By default, ‘Visible’ property is set to “false”. You can customize the minor grid lines width, and dashArray of gridline.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">

     <PrimaryXAxis  MajorGridLines-Width="2" MajorGridLines-Visible="true"  

          MajorGridLines-DashArray="" MinorGridLines-Width="1" MinorGridLines-Visible="true" 

          MinorGridLines-DashArray=""/>  

     <PrimaryYAxis   MajorGridLines-Width="2" MajorGridLines-Visible="true" 

       MajorGridLines-DashArray=""  MinorGridLines-Width="1" MinorGridLines-Visible="true"   

       MinorGridLines-DashArray="" />                    

      </ej:Chart>


{% endhighlight %}


![](Axis_images/Axis_img25.png) 



### Alternate Grid Band

Grid Band is the distance between two adjacent major grid lines which are displayed in horizontal and vertical position.

### Even Grid Band

Even Grid Band are counted from axes lines, i.e the band which is immediate adjacent for axes lines. By default, the even grid band color is transparent. You can highlight the even grid band by setting Fill property of Even. You can customize the Opacity of the even grid band color.

### Odd Grid Band

Immediate adjacent band of every even grid bands are Odd Grid Bands. You can discriminate the odd grid band from even by setting Fill property of Odd. You can customize the Opacity of the odd grid band color.
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">



            <PrimaryXAxis>



                <AlternateGridBand Even-Fill="#E896E8" Even-Opacity="0.5" />



            </PrimaryXAxis>



            <PrimaryYAxis>



                <AlternateGridBand Odd-Fill="#E6F0E7" Odd-Opacity="0.5" />



            </PrimaryYAxis> 



</ej:Chart>

{% endhighlight  %}


![C:/Users/dineshkumarn/Desktop/ug line.png](Axis_images/Axis_img26.png)

## Inversed Axis

You can display the Chart series in to inversed position using “IsInversed” property of Chart Axis. This is illustrated in the following code. 
{% highlight html %}


<ej:Chart ID="Chart1" runat="server">          

          <PrimaryYAxis IsInversed="true" />                    

 </ej:Chart>

{% endhighlight  %}



![](Axis_images/Axis_img27.png)



## Opposed Position

By default, the x-axis is arranged horizontally at the bottom of the Chart and the y-axis is arranged vertically at the left side of the Chart. You can change the alignment of the axis by setting OpposedPosition to true, which arranges the x-axis at the top and the y-axis at the right of the Chart.  
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server">       

        <PrimaryXAxis  OpposedPosition="true" />    

        <PrimaryYAxis  OpposedPosition="true" /> 

   </ej:Chart>


{% endhighlight  %}


![](Axis_images/Axis_img28.png)



## Smart Axis Labels

Sometimes the Chart dimensions could cause the labels to intersect. You can avoid overlapping labels using “LabelIntersectAction” property of char axis. The Chart by default renders the texts one over the other. But, it also has some built-in capabilities to work around this overlap and lets you dictate the technique to follow. Refer to the following properties.

* Rotate45 – Rotate the labels to 45 degree.
* Rotate90 – Rotate the labels to 90 degree
* Trim – Intersecting labels will be trim and mouse over the labels, it displays the trimmed text like tooltip.
* MultipleRows – Split the intersecting labels in to multiple rows and display on the axis
* Wrap – Wrap the intersecting text and display
* Hide – It doesn’t display the intersecting label texts on the axis.
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server">       

        <PrimaryXAxis  LabelIntersectAction="Rotate45" />    

         <PrimaryYAxis  LabelIntersectAction="None" />                    

     </ej:Chart>


{% endhighlight %}


![](Axis_images/Axis_img29.png)



