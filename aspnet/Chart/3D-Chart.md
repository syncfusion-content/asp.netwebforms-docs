---
layout: post
title: 3D-Chart
description: 3d chart
platform: aspnet
control: Chart
documentation: ug
---

## 3D Chart

Now Essential Chart allows you to create stunning 3D Charts for Bar, Column, StackingBar, StackingColumn, Pie and Doughnut series. The representation of data in 3D Chart is very clear and easy to understand when compared to 2D charts. Three dimensions of the series are seen by rotating them. The following properties enhance the perception of 3D Charts.

Enable3D:

The property Enable3D renders 3D Charts and accepts only the Boolean values.

WallSize:

In 3D, Cartesian axes lines are represented as walls. The property WallSize defines the width of the wall. The WallSize property does not support for 3D Pie or Doughnut series because they do not have Cartesian axes lines. 

Depth:

The Depth property defines the depth of the 3D Chart from front view of the series to wall.

Tilt:

The Tilt property defines the angle of the slope of 3D Chart. The positive and negative values declare the side where the slope is present.

Rotation:

The Rotation property is used to spin the 3D chart. The direction of the spin depends upon the positive and negative values of Rotation property.

EnableRotation:

The EnableRotation property allows rotation of the 3D Chart dynamically by dragging the mouse on 3D Chart. Accepting value of this property is Boolean.

PerspectiveAngle:

The perspectiveAngle declares the appearance of the height, width, depth and wall of the 3D Chart. When the PerspectiveAngle is decreased, the 3D object appears closer to viewer. But when it is increased, the 3D object appears far away from the viewer.

SideBySideSeriesPlacement:

The SideBySideSeriesPlacement property defines the appearance of the different sets of data on 3D Chart. When it is set to true, the data is displayed side by side, otherwise it is displayed one by one.

### 3D Series Types

The following are 3D series types:

#### 3D Column Chart

Column charts represent data in a vertical rectangular shape. The size of the shape depends upon the data. Different sets of data are compared by using column chart. The comparison is easy when it is set in 3 Dimensional view. Now Essential Chart gives its support for 3D by setting the property Enable3D to true. For clear perception, rotate the 3D column chart to 360 degrees by giving the value as true for EnableRotation property. The depth, wall size, tilt, and rotation of the 3D chart are customized by setting the property Depth, WallSize, Tilt, and rotation respectively.      



[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="100" WallSize="2" Tilt="0" 



Rotation="34" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



&lt;/ej:Chart&gt;







{ ![](3D-Chart_images/3D-Chart_img1.png) | markdownify }
{:.image }


#### 3D Bar Chart

3D Bar charts are similar to 3D Column charts, but it represents the data in horizontal rectangular shape. The size of the bar depends upon the data. You can customize the depth, wall size, tilt, and rotation of the 3D Bar chart by setting the property Depth, WallSize, Tilt, and rotation respectively

[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="100" WallSize="2" Tilt="0" 



Rotation="34" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



&lt;CommonSeriesOptions Type="Bar"/&gt;



&lt;/ej:Chart&gt;







{ ![](3D-Chart_images/3D-Chart_img2.png) | markdownify }
{:.image }


#### 3D Stacking Column Chart

3D Stacking Column Charts are similar to 3D Column Charts, but here the Y values of different sets of data are represented in a single vertical bar. You can set different colors and borders for different y values in a single vertical bar by setting the Fill and Border properties. You can customize the depth, wall size, tilt, and rotation of the 3D Stacking Column Chart by setting the property Depth, WallSize, Tilt, and rotation respectively. 

[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="100" WallSize="2" Tilt="0" 



Rotation="34" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



&lt;CommonSeriesOptions Type="StackingColumn"&gt;



   &lt;Series&gt;

                &lt;ej:Series Name="Google"&gt;



                    &lt;points&gt;

                        &lt;ej:points X="2006" Y="8"/&gt;

                        &lt;ej:points X="2007" Y="5"/&gt;

                        &lt;ej:points X="2008" Y="4"/&gt;

                        &lt;ej:points X="2009" Y="12"/&gt;

                        &lt;ej:points X="2010" Y="16"/&gt;

                        &lt;ej:points X="2011" Y="6"/&gt;

                        &lt;ej:points X="2012" Y="13"/&gt;

                    &lt;/points&gt;



                &lt;/ej:Series&gt;



                &lt;ej:Series Name="Bing"&gt;



                    &lt;points&gt;

                        &lt;ej:points X="2006" Y="5"/&gt;

                        &lt;ej:points X="2007" Y="6"/&gt;

                        &lt;ej:points X="2008" Y="7"/&gt;

                        &lt;ej:points X="2009" Y="10"/&gt;

                        &lt;ej:points X="2010" Y="14"/&gt;

                        &lt;ej:points X="2011" Y="14"/&gt;

                        &lt;ej:points X="2012" Y="15"/&gt;

                    &lt;/points&gt;



                &lt;/ej:Series&gt;

   &lt;/Series&gt;



&lt;/ej:Chart&gt;





{ ![](3D-Chart_images/3D-Chart_img3.png) | markdownify }
{:.image }


#### 3D Stacking Bar Chart

3D Stacking Bar Charts are similar to 3D Bar Charts, but here the Y values of different sets of data are represented in a single horizontal bar. So the comparison of different sets of data is easier than the normal bar chart. You can customize the depth, wall size, tilt, and rotation of the 3D Stacking Bar Chart by setting the property Depth, WallSize, Tilt, and Rotation respectively

[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="100" WallSize="2" Tilt="0" 



Rotation="34" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



       &lt;CommonSeriesOptions  Type="StackingBar"/&gt;



       &lt;Series&gt;

                &lt;ej:Series Name="Desktop Display"&gt;

                    &lt;points&gt;

                        &lt;ej:points X="2009" Y="2.9"/&gt;

                        &lt;ej:points X="2010" Y="3.8"/&gt;

                        &lt;ej:points X="2011" Y="4.9"/&gt;

                        &lt;ej:points X="2012" Y="6.5"/&gt;

                        &lt;ej:points X="2013" Y="7.1"/&gt;

                        &lt;ej:points X="2014" Y="7.5"/&gt;

                    &lt;/points&gt;

                &lt;/ej:Series&gt;

                &lt;ej:Series Name="Mobile"&gt;

                    &lt;points&gt;

                        &lt;ej:points X="2009" Y="0.1"/&gt;

                        &lt;ej:points X="2010" Y="0.5"/&gt;

                        &lt;ej:points X="2011" Y="1.4"/&gt;

                        &lt;ej:points X="2012" Y="2.9"/&gt;

                        &lt;ej:points X="2013" Y="4.9"/&gt;

                        &lt;ej:points X="2014" Y="6.8"/&gt;

                    &lt;/points&gt;

                &lt;/ej:Series&gt;



       &lt;/Series&gt;



&lt;/ej:Chart&gt;







{ ![](3D-Chart_images/3D-Chart_img4.png) | markdownify }
{:.image }


#### 3D Pie Chart

Pie Charts are circular with several segments. The segments are calculated from the y value of the series. Normally, in 2D only the front view of the pie chart can be seen. In 3D, there is an option to see the whole side of the pie chart by enabling the EnableRotation property. You can explode a particular segment of pie series by setting the ExplodeIndex property. You can customize the color of each segment by setting the Fill property, and can also customize the depth, perspective angle, rotation, tilt of the pie chart by setting the appropriate properties.   

[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="30" WallSize="10" Tilt="-30" 



Rotation="-30" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



   &lt;Series&gt;



      &lt;ej:Series Type="Pie" StartAngle="145" ExplodeIndex="1"&gt;



                    &lt;points&gt;



                        &lt;ej:points X="Housing" Y="31"/&gt;

                        &lt;ej:points X="Food" Y="16"/&gt;

                        &lt;ej:points X="Transportation" Y="14"/&gt;

                        &lt;ej:points X="Clothing" Y="6"/&gt;

                        &lt;ej:points X="Health care" Y="8"/&gt;

                        &lt;ej:points X="Education" Y="17"/&gt;

                        &lt;ej:points X="Miscellaneous" Y="8"/&gt;



                    &lt;/points&gt;



                    &lt;Border Width="2" Color="White" /&gt;



       &lt;/ej:Series&gt;



   &lt;/Series&gt; 



&lt;/ej:Chart&gt;





{ ![](3D-Chart_images/3D-Chart_img5.png) | markdownify }
{:.image }


#### 3D Doughnut Chart

3D Doughnut charts are similar to 3D Pie Charts with the difference of having a hole in the center of the Doughnut chart. The size of the hole is customized by using the DoughnutCoefficient property. The size of the doughnut is customized by using the DoughnutSize property. You can rotate the 3D doughnut chart to 360 degrees by enabling the EnableRotation property. You can customize each segment’s color and border by setting Fill and Border property. 

[ASP.NET]



<ej:Chart ID="Chart1" runat="server” Depth="30" WallSize="10" Tilt="-30" 



Rotation="-30" PerspectiveAngle="90" EnableRotation="true" Enable3D="true">



   &lt;Series&gt;



      <ej:Series Type="Doughnut" DoughnutCoefficient=”0.5”  



                 DoughnutSize=”0.8”  ExplodeIndex="4">



                    &lt;points&gt;



                        &lt;ej:points X="Watching TV" Y="31"/&gt;

                        &lt;ej:points X="Socializing" Y="16"/&gt;

                        &lt;ej:points X="Reading" Y="14"/&gt;

                        &lt;ej:points X="Sports" Y="6"/&gt;

                        &lt;ej:points X="Others" Y="8"/&gt;



                    &lt;/points&gt;



                    &lt;Border Width="2" Color="White" /&gt;



       &lt;/ej:Series&gt;



   &lt;/Series&gt; 



&lt;/ej:Chart&gt;



{ ![](3D-Chart_images/3D-Chart_img6.png) | markdownify }
{:.image }


### 100% 3D Stacking Column

100% 3D Stacking Column charts are similar to 3D stacking Column charts. But here, the combined contribution of Y values is the combined total of the vertical bar with 100 percent. You can customize the depth, wall size, tilt and rotate the 100% 3D Stacking Column by using the Depth, WallSize, Tilt and Rotation property respectively.



[ASP.NET]



  <ej:Chart ID="Chart2" runat="server" Depth="100" Wallsize="2"

        Tilt="0" Rotation="34" PerspectiveAngle="90"    

        EnableRotation="true"  Enable3D="true">



        &lt;CommonSeriesOptions EnableAnimation="true" Type="StackingColumn100"&gt;

        &lt;/CommonSeriesOptions&gt;       

        &lt;Series&gt;

          &lt;ej:Series Name="Australia"&gt;

              &lt;points&gt;

                   &lt;ej:points X="2006" Y="80000"/&gt;

                   &lt;ej:points X="2007" Y="22000"/&gt;

                   &lt;ej:points X="2008" Y="60000"/&gt;

                   &lt;ej:points X="2009" Y="39000"/&gt;

                   &lt;ej:points X="2010" Y="62000"/&gt;

                   &lt;ej:points X="2011" Y="90000"/&gt;                          

              &lt;/points&gt;

          &lt;/ej:Series&gt;

          &lt;ej:Series Name=”China”&gt;

              &lt;points&gt;

                   &lt;ej:points X="2006" Y="50000"/&gt;

                   &lt;ej:points X="2007" Y="41000"/&gt;

                   &lt;ej:points X="2008" Y="52000"/&gt;

                   &lt;ej:points X="2009" Y="43000"/&gt;

                   &lt;ej:points X="2010" Y="47000"/&gt;

                   &lt;ej:points X="2011" Y="93000"/&gt;                          

              &lt;/points&gt;

          &lt;/ej:Series&gt; 

        &lt;/Series&gt;          

  &lt;/ej:Chart&gt;



The following screenshot displays the 100% 3D Stacking Column.



{ ![F:/bar100/sshot-3.png](3D-Chart_images/3D-Chart_img7.png) | markdownify }
{:.image }


### 100% 3D Stacking Bar

100% 3D Stacking Bar charts are similar to 3D stacking Bar charts. But here, the combined contribution of Y values is the combined total of the horizontal bar with 100 percent. You can customize the depth, wall size, tilt and rotate the 100% 3D Stacking Bar by using the Depth, WallSize, Tilt and Rotation properties respectively.



[ASP.NET]



  <ej:Chart ID="Chart3" runat="server" Depth="100" Wallsize="2"

        Tilt="0" Rotation="34" PerspectiveAngle="90"    

        EnableRotation="true"  Enable3D="true">



        &lt;CommonSeriesOptions EnableAnimation="true" Type="StackingBar100"&gt;

        &lt;/CommonSeriesOptions&gt;



        &lt;Series&gt;

          &lt;ej:Series Name="Brazil"&gt;

              &lt;points&gt;

                   &lt;ej:points X="2006" Y="8000"/&gt;

                   &lt;ej:points X="2007" Y="12000"/&gt;

                   &lt;ej:points X="2008" Y="20000"/&gt;

                   &lt;ej:points X="2009" Y="21000"/&gt;

                   &lt;ej:points X="2010" Y="28000"/&gt;

                   &lt;ej:points X="2011" Y="29000"/&gt;                          

              &lt;/points&gt;

          &lt;/ej:Series&gt;

          &lt;ej:Series Name="Nigeria"&gt;

              &lt;points&gt;

                   &lt;ej:points X="2006" Y="5000"/&gt;

                   &lt;ej:points X="2007" Y="15000"/&gt;

                   &lt;ej:points X="2008" Y="19000"/&gt;

                   &lt;ej:points X="2009" Y="25000"/&gt;

                   &lt;ej:points X="2010" Y="26000"/&gt;

                   &lt;ej:points X="2011" Y="30000"/&gt;                          

              &lt;/points&gt;

          &lt;/ej:Series&gt; 

        &lt;/Series&gt;   

  &lt;/ej:Chart&gt;



The following screenshot displays the 100% 3D Stacking Bar.



{ ![F:/bar100/sshot-2.png](3D-Chart_images/3D-Chart_img8.png) | markdownify }
{:.image }


