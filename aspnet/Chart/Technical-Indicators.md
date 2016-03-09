---
layout: post
title: Technical Indicators | Chart | ASP.NET Webforms | Syncfusion
description: technical indicators
platform: aspnet
control: Chart
documentation: ug
---

# Technical Indicators

Technical indicators are the base of technical analysis, used to determine the future of financial, stock or economic trends. Indicators serve three broad functions: to alert, to confirm and to predict actions. Future price levels can be predicted easily with the help of given data and it also supports you to enter or exit a trade and enables to make a profit.

The following are the Technical indicators supported by Essential Chart.

## Accumulation Distribution Indicator

Accumulation distribution indicator is one of the technical indicator supported by Essential Chart. The indicator rendered is called signal line. Essential Chart also provides options to customize the width and color of the signal line. 
{% highlight html %}
 

 <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

  <Axes>

  <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

  </ej:Axis>

  </Axes>

 // ...

  <Indicators>

  <ej:ChartIndicator Type="AccumulationDistribution" YAxisName="yAxis"          		SeriesName="indicator">

  </ej:ChartIndicator>

  </Indicators>

        // ...

  </ej:Chart>

{% endhighlight  %}

The following screenshot displays Accumulation Distribution indicator.



![](Technical-Indicators_images/Technical-Indicators_img1.png) 



## Average True Range Indicator

Average true range Indicator is one of the technical indicator supported by Essential Chart. The indicator rendered is called as signal line. You can also customize the width and color of the signal line. 
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

<Axes>

    <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

    </ej:Axis>

</Axes>

 // ...

<Indicators>

     <ej:ChartIndicator Type="Atr” YAxisName="yAxis" SeriesName="indicator" Period="14">

      </ej:ChartIndicator>

</Indicators>

        // ...

</ej:Chart>
{% endhighlight  %}

The following screenshot displays the Average true range indicator.

![](Technical-Indicators_images/Technical-Indicators_img2.png)



## Bollinger Band Indicator

Bollinger Band Indicator is one of the technical indicator supported by Essential Chart. It contains three lines namely upper band, lower band and signal line. Upper band, lower band are calculated based on the standard deviations value. Signal band is calculated based on the simple moving average. You can also customize the width and color of the upper band, lower band and signal line. The default value of period is 14.The default value of standardDeviations is 2. 
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

  <Axes>

  <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

  </ej:Axis>

  </Axes>

 // ...

  <Indicators>

  <ej:ChartIndicator Type="Bollingerband" YAxisName="yAxis" SeriesName="indicator"    			Period="4" StandardDeviations="2">

  </ej:ChartIndicator>

  </Indicators>

        // ...

  </ej:Chart>


{% endhighlight  %}
The following screenshot displays the Bollinger Band indicator.

![](Technical-Indicators_images/Technical-Indicators_img3.png) 



## Exponential Moving Average Indicator

Exponential Moving Average Indicator is one of the technical indicator supported by Essential Chart. The indicator renders a line called signal line. You can also customize properties such as width, color etc., of the signal line.


{% highlight html %}


<ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



    <Axes>

      <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

      </ej:Axis>

    </Axes>

    <Indicators>

      <ej:ChartIndicator Type="ema" YAxisName="yAxis" SeriesName="indicator" Period="14">

      </ej:ChartIndicator>

    </Indicators>



</ej:Chart>

{% endhighlight %}

The following screenshot displays the Exponential Moving Average Indicator

![C:/Users/ApoorvahR/Desktop/1.png](Technical-Indicators_images/Technical-Indicators_img4.png) 



## Momentum Technical Indicator

Momentum is one of the technical indicator supported by Essential Chart. The indicator renders two lines namely upper band and signal line. Upper band always render at value 100 and signal band is calculated based on the momentum formula. Essential Chart also provide options to customize the width and color of the upper band and signal line. You can also change the value for period. The default value of period is 14. 
{% highlight html %}


  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

<Axes>

    <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

    </ej:Axis>

</Axes>

 // ...

<Indicators>

     <ej:ChartIndicator Type="Momentum" YAxisName="yAxis" SeriesName="indicator" Period="4">

      </ej:ChartIndicator>

</Indicators>

        // ...

</ej:Chart>

{% endhighlight %}

The following screenshot displays the momentum technical indicator.

![C:/Users/ApoorvahR/Desktop/1.png](Technical-Indicators_images/Technical-Indicators_img5.png)



## Moving Average Convergence Divergence Indicator

MACD is one of the technical indicator supported by Essential Chart. It contains three lines namely Macd line, Signal line and Histogram column series that is used to differentiate macd and signal line. And also enumeration property: MacdType,Line, Histogram and Both. By default, line series contain macd and signal line. Enumeration type Both contain line and histogram series. Macd and signal line is calculated based on the ShortPeriod,LongPeriod and Trigger value with indicator formula and histogram displays the difference between them. Essential Chart also provides options to customize the width and color of the macd and signal line and histogram with tooltip and animation options. The value for short, long period and trigger value can also be changed.

{% highlight html %}

 

  <ej:Chart ID="Chart1" runat="server">   



      // ...

<Axes>

    <ej:Axis Name=" yAxis1" OpposedPosition="true" Orientation="vertical">

    </ej:Axis>

</Axes>

 // ...

<Indicators>

   <ej:ChartIndicator Type="Macd" YAxisName="yAxis1" MacdType="Both" 

            ShortPeriod="12" LongPeriod="26" Trigger="9" SeriesName="Hilo">

                 <Histogram Fill="red" Opacity="1">

                        <Border Color="red" Width="1" />

                 </Histogram>

    </ej:ChartIndicator>

</Indicators>

// ...

</ej:Chart>

{% endhighlight %}

The following screenshot displays the MACD technical indicator

![C:/Users/ApoorvahR/Desktop/1.png](Technical-Indicators_images/Technical-Indicators_img6.png) 



## Relative Strength Index Indicator

RSI is one of the technical indicator supported by Essential Chart. It contains three lines namely upper band, lower band and signal line. Upper and lower band always render at value 70 and 30 respectively and signal band is calculated based on the RSI formula. You can also customize the width and color of the upper band, lower band and signal line with tooltip and animation options. 
{% highlight html %}




  <ej:Chart ID="Chart1" runat="server">   



      // ...

<Axes>

    <ej:Axis Name=" yAxis1" OpposedPosition="true" Orientation="vertical">

    </ej:Axis>

</Axes>

 // ...

<Indicators>

  <ej:ChartIndicator Type="Rsi" EnableAnimation="false" Period="14" 

            Fill="darkblue" Width="1" SeriesName="Hilo" YAxisName="yAxis1">

                    <UpperLine Fill="green" Width="1" />

                    <LowerLine Fill="red" Width="1" />

                    <Tooltip Visible="true"></Tooltip>



</Indicators>        

// ...

</ej:Chart>

{% endhighlight  %}

The following screenshot displays the RSI technical indicator

![C:/Users/ApoorvahR/Desktop/1.png](Technical-Indicators_images/Technical-Indicators_img7.png)



## Simple Moving Average Indicator

Simple Moving Average Indicator is one of the technical indicators supported by Essential Chart. The indicator rendered is called as signal line. Signal line is calculated based on the simple moving average. You can also customize the Period, width and color of the signal line. The default value of Period is 14.

{% highlight html %}









  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

    <Axes>



      <ej:Axis Name="indicator" OpposedPosition="true"             

       Orientation="vertical">

      </ej:Axis>



    </Axes>



// ...

    <Indicators>



      <ej:ChartIndicator Type="Sma" YAxisName="yAxis" 

       SeriesName="indicator" Period="14">

      </ej:ChartIndicator>



    </Indicators>



      // ...

  </ej:Chart>

{% endhighlight  %}

The following screenshot displays the Simple Moving Average Indicator.

![](Technical-Indicators_images/Technical-Indicators_img8.png) 



## Stochastic Technical Indicator

Stochastic technical indicator is one of the most common indicators used in technical analysis. The indicators render four lines namely upper line, lower line, stochastic line and signal line. Upper line always render at value 80 and lower line is render at value 20. Stochastic and Signal Lines are calculated based on stochastic formulas. You can also customize the width and color of the all lines. 

![C:/Users/ApoorvahR/Desktop/1.png](Technical-Indicators_images/Technical-Indicators_img9.png)


{% highlight html %}




  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



        // ...

       <Axes>

            <ej:Axis Name="indicator" 

                OpposedPosition="true" 

                Orientation="vertical">

            </ej:Axis>

     </Axes>



 // ...



     <Indicators>

          <ej:ChartIndicator Type="Stochastic"   

             YAxisName="yAxis"

             SeriesName="indicator"

             Period="14"

             KPKeriod="3"

             DPeriod="3">

         </ej:ChartIndicator>

    </Indicators>



        // ...



</ej:Chart>
{% endhighlight %}

## Triangular Moving Average Indicator

Triangular Moving Average Indicator is one of the technical indicator supported by ejChart. The indicator rendered is called as signal line. You can also customize the width and color of the signal line. 
{% highlight html %}




  <ej:Chart ID="Chart1" runat="server" EnableCanvasRendering="true">   



      // ...

  <Axes>

  <ej:Axis Name="indicator" OpposedPosition="true" Orientation="vertical">

  </ej:Axis>

  </Axes>

 // ...

  <Indicators>

  <ej:ChartIndicator Type="TMA" YAxisName="yAxis" SeriesName="indicator"   

              	Period="14">

  </ej:ChartIndicator>

  </Indicators>

        // ...

  </ej:Chart>

{% endhighlight  %}

The following screenshot displays the Triangular Moving Average indicator.

![](Technical-Indicators_images/Technical-Indicators_img10.png)



