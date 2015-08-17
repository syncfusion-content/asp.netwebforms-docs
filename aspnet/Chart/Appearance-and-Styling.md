---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: aspnet
control: Chart
documentation: ug
---

# Appearance and Styling

Essential Chart is enriched with lots of customization options to develop high quality graphic rich Charts.

## Tooltip Template

You can customize a tooltip with required template by adding a “div” element with an “id” to the web page and assigning the “id” to the property “Template” under “Tooltip” as illustrated in the following code example.
{% highlight html %}

<div id="Tooltip" style="display: none;">

<div id="icon">

       <div id="grain"></div>

</div>

        <div id="value">

            <div>

            <div id="efpercentage">#point.x#</div>

                <div id="ef">#point.y#</div>

             </div>

        </div>



    </div>

{% endhighlight %}
{% highlight css %}
<style class="cssStyles">

        .tooltipDiv {

            background-color:#C1272D !important;        

            color: white;

width:100px;

        }

        #Tooltip >div:first-child {

            float: left;

        }

        #Tooltip #value {

            float: right;

            height: 50px;

            width: 50px;

            background-color:#C1272D

        }

        #Tooltip #value >div {

            margin: 3px 5px 5px 5px;



        }

        #Tooltip #efpercentage {

            font-size: 12px;

            font-family: segoe ui;

            color:#E7C554;

font-weight: bold;

        }

         #Tooltip #ef {

             font-size: 20px;

             font-family: segoe ui;

font-weight: bold;



        }

        #grain {

            background-image: url("../images/chart/grain.png");

            height: 50px;

            width: 50px;

            background-repeat: no-repeat;

        }

    </style>

{% endhighlight  %}
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server">       

  <Series>

              <ej:Series Name="India" Tooltip-Visible="true" Tooltip-Template="Tooltip">

                  <Points>

                        <ej:Points X="2002" Y="1.61" />

                    <ej:Points X="2003" Y="2.31" />

                    <ej:Points X="2004" Y="2.16" />

                    <ej:Points X="2005" Y="2.10"/>

                    <ej:Points X="2006" Y="2.81" />

                    <ej:Points X="2007" Y="2.05" />

                    <ej:Points X="2008" Y="2.50" />

                    <ej:Points X="2009" Y="2.22" />

                    <ej:Points X="2010" Y="2.21" />

                    <ej:Points X="2011" Y="2.00" />

                    <ej:Points X="2012" Y="2.27" />

                  </Points>



              </ej:Series>

     </Series>

  </ej:Chart>

{% endhighlight %}

![F:/Skype Download/IMG_14052014_050616.png](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)



## Label Template

You customize a data label with required template by adding a “div” element with an “id” to the web page and assigning the “id” to the property “Template” under “DataLabel” as illustrated in the following code example.

{% highlight html %}

<div id="template">

        <div id="left">

            <img src="../images/chart/icon_investments.png"/>

        </div>

        <div id="right">

            <div id="point">#point.y#%</div>

        </div>

    </div>

{% endhighlight  %}
{% highlight css %}
    <style>

        #point {

            font-family: segoe ui;

            font-size: 16px;

            color: black;

        }

        #left, #right {

            float: left;   

        }

        img {

            height: 25px;

            width: 30px;

        }

        #left{

            background-color: #8CC640;   

        }

        #right{

            background-color: #C3C3C3; 

            height: 30px;

            border-style:solid;

            border-color:#8CC640;

            border-width: 1px;				

        }

        #template {

            display:none;

        }

    </style>

{% endhighlight  %}
{% highlight html %}
 

  <ej:Chart ID="Chart1" runat="server">       

    <Series>

             <ej:Series Name="India" Fill="#8CC640" Marker-Visible="true" Marker-DataLabel-Visible="true" Marker-DataLabel-Template="template">

            <Points >

            <ej:Points X="2005" Y="28.1" Marker-DataLabel-Visible="false" Marker-Fill="" />    

            <ej:Points X="2006" Y="29.2"/>  

            <ej:Points X="2007" Y="33.9"/>  

            <ej:Points X="2008" Y="36"/>  

            <ej:Points X="2009" Y="32.4"/>

           <ej:Points X="2010" Y="32"/> 

           <ej:Points X="2011" Y="32.8" Marker-DataLabel-Visible="false" Marker-Fill="" /                 

           </Points>

         </ej:Series>

  </ej:Chart>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)



## Label Formatting

### Numerical Axis:

By default, the label texts are automatically determined based on the axis data points and the generated intervals. You can make the Chart readable and understandable by formatting axes labels. For example, add "$" prefix when values are given in dollars and add "°F" postfix when values are given in Fahrenheit degrees. To achieve this “LabelFormat” property in axis is used.

{% highlight html %}



  <ej:Chart ID="Chart1" runat="server">       

         <PrimaryYAxis LabelFormat="{value}%" />

  </ej:Chart>
{% endhighlight %}
### Date time Axis:

For datetime axis, all globalized date time formats are supported. By default, based on the interval type the LabelFormat is calculated. When the IntervalType is “Year” then the LabelFormat is 'MMM, yyyy'.

Some of the LabelFormat for datetime axis:

* 'MMM, yyyy'
* 'dd, MMM'
* 'dd/MM/yyyy'
* 'dd, hh:mm'
* 'hh:mm:ss'
* 'hh:mm:ss:tt'

{% highlight html %}

 

  <ej:Chart ID="Chart1" runat="server">       

    <PrimaryXAxis ValueType="Datetime" LabelFormat="MMM-yyyy"/>

  </ej:Chart>

{% endhighlight  %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)





## Title and Subtitle

Essential Chart provides Title and Subtitle support that is used to give additional information about the chart data. It also has various options to customize the font alignment of the Title and Subtitle. 
{% highlight html %}




<ej:Chart ID="Chart1" runat="server">

<Title Text="Efficiency of oil-fired power production">

              <SubTitle Text="(in a week)" TextAlignment="Far">

                  <Font Color="green" FontSize="14px"></Font>

              </SubTitle>

          </Title></ej:Chart>


{% endhighlight  %}
The following screenshot shows the Title and Subtitle in Chart control.

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png) 



## Chart Background and Foreground

You can customize the background for different portion of Chart.

### To Chart:

Using the Background property you can customize the background color of the Chart.

### Code: 
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server" Background="#1E90FF">       

  </ej:Chart>


{% endhighlight %}
![](Appearance-and-Styling_images/Appearance-and-Styling_img5.png)



### To Chart Area:

Using Background property in ChartArea you can customize the background color of the Chart area.

### Code: 
{% highlight html %}


<ej:Chart ID="Chart1" runat="server" Background="#1E90FF">       

         <ChartArea Background="#cc3333" />

</ej:Chart>

{% endhighlight  %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img6.png)



### BackGround Image:

Essential Chart allows you to add background image for your Chart using BackGroundImageUrl property.

{% highlight html %}



 <ej:Chart ID="Chart1" runat="server"  BackgroundImgUrl="../images/chart/wheat.png">       



         </ej:Chart>


{% endhighlight %}
![](Appearance-and-Styling_images/Appearance-and-Styling_img7.png)



## Theme

Chart has built-in theme support. The theme configures the colors of following Chart element.

1. Fonts
2. Axis lines
3. Series color
4. Legend
5. Tooltip
6. Background

### Code: 
{% highlight html %}
 

 <ej:Chart ID="Chart1" runat="server" Theme="GradientLight">       



 </ej:Chart>


{% endhighlight  %}
Following predefined themes are available in JS Chart.

1. FlatLight     
2. FlatDark
3. GradientLight
4. GradientDark
5. Azure
6. AzureDark
7. Lime
8. LimeDark
9. Saffron
10. SaffronDark

![](Appearance-and-Styling_images/Appearance-and-Styling_img8.png)



## Custom Color palette 

Apart from the themes, to define custom set of color you can use “Palette” property. Palette customizes the color of series in the Chart. 


{% highlight html %}


        <ej:Chart ID="Chart1" Palette="#69D2E7, #E27F2D, #6A4B82" runat="server">            

        </ej:Chart>

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img9.png) 



