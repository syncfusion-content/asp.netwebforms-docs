---
layout: post
title: Chart Title |Chart  | ASP.NET Webforms | Syncfusion
description: How to customize the chart title.
platform: aspnet
control: Chart
documentation: ug
---

# Chart Title & Subtitle

## Title

By using the **Title** option, you can add the *Text* as well as customize its *Border, Background and Font*.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <%--Adding text to chart title--%>
   <Title Text="'Efficiency of oil-fired power production" Background="lightblue">
       <%--Customizing Chart title border--%>
       <Border Color="blue" Width="2" Opacity="0.5" CornerRadius="4" />
       <%--Customizing Chart title font --%>
       <Font Opacity="1" FontFamily="Arial" FontStyle="Italic" FontWeight="Regular" Color="#E27F2D" FontSize="23px">
       </Font>
   </Title>
</ej:Chart> 


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img1.png)


[Click](http://asp.syncfusion.com/demos/web/chart/subtitle.aspx) here to view the Chart Title online demo sample.




We can trim, wrap and wrapAndTrim to the chart title using textOverflow property. The original text will be displayed as tooltip on mouse hover.


{% highlight javascript %}

<ej:Chart ID="Chart1" runat="server"> 
       //……
              <Title Text="Efficiency of oil-fired power production " EnableTrim= ”true” 
                              MaximumWidth=150 TextOverflow="trim" >
               </Title>             
 
      //….…
</ej:Chart>




{% endhighlight %}

![](Chart-Title_images/Chart-Title_img5.png)


### Title Alignment

You can change the title alignment to *Center*, *Far* and *Near* by using the **TextAlignment** property of the chart title. 

{% highlight html %}

<ej:Chart ID="Chart1" runat="server">  
    <%--Change title text alignment --%>
    <Title TextAlignment="Near">     
    </Title>
</ej:Chart>

{% endhighlight %} 

![](Chart-Title_images/Chart-Title_img2.png)


## Add Subtitle to the chart

By using the **SubTitle** option, you can add the SubTitle to the chart title and customize its *Border, Background and Font*.

{% highlight html %}

<ej:Chart ID="Chart" runat="server">
   <Title>
    <%--Adding text to chart title--%>
       <SubTitle Text="( in a week )" Background="lightblue">
           <%--Customizing Chart subtitle border--%>
           <Border Color="blue" Width="2" Opacity="0.2" CornerRadius="4" />
           <%--Customizing Chart subtitle font --%>
           <Font Opacity="1" FontFamily="Arial" FontStyle="Italic" FontWeight="Regular" Color="#E27F2D" FontSize="12px">
           </Font>
       </SubTitle>
   </Title>
</ej:Chart> 


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img3.png)

We can trim, wrap and wrapAndTrim to the chart sub title using textOverflow property. The original text will be displayed as tooltip on mouse hover.


{% highlight javascript %}

<ej:Chart ID="Chart1" runat="server"> 
       //……
              <Title>
                     <SubTitle Text="( in a week ) " EnableTrim= ”true”   MaximumWidth=150                                       
                                   TextOverflow="wrap"> 
                     </SubTitle >
              </Title>             
 
      //….…
</ej:Chart>


{% endhighlight %}

![](Chart-Title_images/Chart-Title_img6.png)

### Subtitle Alignment

You can change the SubTitle alignment to *Center*, *Far* and *Near* by using the **TextAlignment** property of the SubTitle.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server">  

    <Title>     
        <%--Change sub title text alignment--%>
        <SubTitle TextAlignment="Center">
        </SubTitle>
    </Title>
</ej:Chart>

{% endhighlight %}

![](Chart-Title_images/Chart-Title_img4.png)
