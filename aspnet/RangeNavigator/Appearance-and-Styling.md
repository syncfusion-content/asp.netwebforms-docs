---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: aspnet
control: RangeNavigator
documentation: ug
---

# Appearance and Styling

RangeNavigator is enriched with lots of customization options for labels, gridlines and slider to develop high quality graphic rich control.

## Customize labels

The labels are found along the range, displaying the value of the data it correspond, both on (higher level label) and below (lower level label) the RangeNavigator. RangeNavigator labels are further customized using “Font” property in label Settings. 


{% highlight html %}

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="onchartloaded"&gt;

     &lt;LabelSettings&gt;

                &lt;HigherLevel&gt;

                    &lt;Style Font-Color="#ff0000" Font-Opacity="1" Font-FontSize="12px" Font-Style="Normal" Font-Weight="Regular"&gt;                        

                    &lt;/Style&gt;

                &lt;/HigherLevel&gt;

                &lt;LowerLevel&gt;

                    &lt;Style Font-Color="#ff0000" Font-Opacity="1" Font-FontSize="12px" Font-Style="Normal" Font-Weight="Regular"&gt;&lt;/Style&gt;

                &lt;/LowerLevel&gt;

     &lt;/LabelSettings&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png)
{:.image }


_Figure 22: Customize labels_

## Label Placement:

Labels in RangeNavigator are placed inside or outside of the control. You can customize both the higher and lower level labels using LabelPlacement property in LabelSettings of RangeNavigator. By default LabelPlacement is “outside” for the both higher and lower level labels.

The following screen shot illustrates both the lower and higher level labels that are placed outside the control with LabelPlacement specified as outside. 

{% highlight html %}

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="onchartloaded"&gt;

     &lt;LabelSettings&gt;

               &lt;HigherLevel LabelPlacement="inside"&gt;                   

                &lt;/HigherLevel&gt;

                &lt;LowerLevel LabelPlacement="inside"&gt;                   

                &lt;/LowerLevel&gt;

     &lt;/LabelSettings&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

{% endhighlight %}

The following screenshot illustrates a RangeNavigator with labels inside the control after specifying the labelPlacement as inside.



![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)
{:.image }


## Customize RangeNavigator

RangeNavigator is customized using NavigatorStyleSettings properties. You can customize the selected and unselected region color using SelectedRegionColor, UnselectedRegionColor in NavigatorStyleSettings and the thumb of the slider using ThumbColor, ThumbRadius and ThumbStorke in NavigatorStyleSettings.  MajorGridLineStyle and MinorGridLineStyle are used to customize the grid line color and visibility. 

{% highlight html %}

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" onClientSideRangeChanged="onchartloaded"&gt;

  &lt;LabelSettings&gt;

     &lt;HigherLevel&gt;

                    &lt;Style HorizontalAlignment="Left" Font-Color="#ff0000" Font-Opacity="1" Font-FontSize="13px" Font-Style="Normal" Font-Weight="Regular"&gt; &lt;/Style&gt;

     &lt;/HigherLevel&gt;

  &lt;LowerLevel&gt;

                    &lt;Style HorizontalAlignment="Left" Font-Color="#ff0000" Font-Opacity="1" Font-FontSize="12px" Font-Style="Normal" Font-Weight="Regular"&gt;&lt;/Style&gt;

   &lt;/LowerLevel&gt;

&lt;/LabelSettings&gt;



&lt;NavigatorStyleSettings UnselectedRegionColor="white" SelectedRegionColor="#5EABDE" ThumbRadius="10" ThumbColor="white" Background="transparent"&gt;

        &lt;Border Color="black" Width="3"&gt;&lt;/Border&gt;

       &lt;MajorGridLineStyle Color="transparent" Visible="true"&gt;&lt;/MajorGridLineStyle&gt;

        &lt;MinorGridLineStyle Color="transparent" Visible="true"&gt;&lt;/MinorGridLineStyle&gt;

&lt;/NavigatorStyleSettings&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)
{:.image }


## Themes

RangeNavigator theme is a set of pre-defined options that are applied to the control before each RangeNavigator is instantiated. Following predefined themes are available in ASP.NET RangeNavigator.

1. flatlight                  
2. flatdark                  
3. gradientlight           
4. gradientdark           
5. azure                      
6. azuredark               
7. lime 
8. limedark
9. saffron
10. saffrondark
11. gradientazure
12. gradientazuredark
13. gradientlime
14. gradientlimedark
15. gradientsaffron
16. gradientsaffrondark


{% highlight html %}

&lt;ej:RangeNavigator ID="RangeNavigator1" runat="server" Theme="azuredark"&gt;

  &lt;%--Code --%&gt;

  &lt;%--Code --%&gt;

&lt;/ej:RangeNavigator&gt;

{% endhighlight %}

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png) 
{:.image }


