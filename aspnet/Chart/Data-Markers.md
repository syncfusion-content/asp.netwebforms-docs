---
layout: post
title: Markers and data labels in Essential ASP.NET Webforms Chart
description: Learn how to add markers and data point labels to a Chart series.
platform: aspnet
control: Chart
documentation: ug
---

# Data Markers

Data markers are used to provide information about the data point to the user. You can add a shape and label to adorn each data point.

## Add Shapes

You can add shapes to any chart types but they are often used with line, area and spline series to indicate each data point. It is highlighted when you hover the mouse on the shape.

Shapes can be added to the chart by enabling the Visible option of the **Marker** property. There are different shapes you can add to the chart by using the **Shape** option such as Rectangle, Circle, Diamond etc.

The following code example explains on how to enable series marker and add shapes,

{% highlight html %}


<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <%--Adding shapes to series1--%>
            <Marker Visible="true" Shape="Diamond"></Marker>
        </ej:Series>
        <ej:Series>
            <%--Adding shapes to series2--%>
            <Marker Visible="true" Shape="Triangle"></Marker>
        </ej:Series>
        <ej:Series>
            <%--Adding shapes to series3--%>
            <Marker Visible="true" Shape="Hexagon"></Marker>
        </ej:Series>
    </Series>
</ej:Chart>


{% endhighlight %}

![](Data-Markers_images/Data-Markers_img1.png)


## Add image as marker

Apart from the shapes, you can also add images to mark the data point by using the **ImageUrl** option.

The following code example illustrates this,

{% highlight html %}


<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <%--Adding shapes to series1--%>
            <Marker Visible="true" Shape="Image" ImageUrl="sun_annotation.png">
                <Size Height="20" Width="20" />
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>


{% endhighlight %}

![](Data-Markers_images/Data-Markers_img2.png)


## Add labels

Data label can be added to a chart series by enabling the *Visible* property in the **DataLabel** option. The labels appear at the top of the data point, by default.

The following code example shows how to enable data label and set its horizontal and vertical text alignment. 

{% highlight html %}


<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <Marker>
                <%--Set text alignment to data label text--%>
                <DataLabel Visible="true" HorizontalTextAlignment="Center" VerticalTextAlignment="Far"></DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>


{% endhighlight %}

![](Data-Markers_images/Data-Markers_img3.png)


Label content can be formatted by using the template option. Inside the template, you can add the placeholder text *"point.x"* and *"point.y"* to display corresponding data points x & y value.

You can adorn the labels with background shapes by setting *Shape* option.

The following code example shows how to add background shapes and set template to data label.

{% highlight html %}


<div id="template">
     <div id="left">
	<img src="../images/chart/icon_investments.png"/>
     </div>
     <div id="right">
          <div id="point">#point.y#%</div>
     </div>
</div>

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <Marker>
                <%--Set template to data label--%>
                <DataLabel Visible="true" Template="template"></DataLabel>
            </Marker>
        </ej:Series>
         <ej:Series>
            <Marker>
                <%--Add background shape to the data label--%>
                <DataLabel Visible="true"  Shape="Rectangle">
                    <Border Width="1" Color="red" />
                </DataLabel>
            </Marker>
        </ej:Series>
         <ej:Series>
            <Marker>
                <DataLabel Visible="true">
                </DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img4.png)


The appearance of the labels can be customized by using the *Font* and *Offset* options. The Offset option is used to move the labels vertically. Also, labels can be rotated by using the *Rotate* option.

The following code example shows how to rotate data label text and customize the font.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <Marker>
                <%--Rotate data label and customize the font--%>
                <DataLabel Angle="300" Offset="15">
                    <Font Color="black" FontSize="13px"></Font>
                </DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img5.png)


You can position the label to the top, center or bottom position of the segment by using the **TextPosition** option for the chart types such as Column, Bar, Stacked bar, Stacked column, 100% Stacked bar, 100% Stacked column, Candle and OHLC.

The following code example shows how to set textPosition to display data label in the middle of the column rectangle.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series>
            <Marker>
                <%--Place the data label text position in the centre of the rectangle--%>
                <DataLabel TextPosition="Middle">
                </DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img6.png)

The label can be positioned inside or outside the perimeter of the series by using the **LabelPosition** option for the chart types such as Pie and Doughnut, .

The following code example shows how to set the LabelPosition,

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series Type="Doughnut" LabelPosition="Outside">
            <Points>
                <ej:Points X="India" Y="24" Text="India 24%"></ej:Points>
                <ej:Points X="Japan" Y="25" Text="Japan 25%"></ej:Points>
                <ej:Points X="Australia" Y="20" Text="Australia 20%"></ej:Points>
                <ej:Points X="USA" Y="35" Text="USA 35%"></ej:Points>
                <ej:Points X="China" Y="23" Text="China 23%"></ej:Points>
                <ej:Points X="Germany" Y="27" Text="Germany 27%"></ej:Points>
                <ej:Points X="France" Y="22" Text="France 22%"></ej:Points>
            </Points>
            <Marker>
                <%--Place the data label text position in the centre of the rectangle--%>
                <DataLabel Visible="true" Shape="Rectangle">
                    <Font Color="white"></Font>
                </DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %} 

![](Data-Markers_images/Data-Markers_img7.png)


The following screenshot displays the labels when the LabelPosition is set as *Inside* position.

![](/js/Chart/Data-Markers_images/Data-Markers_img8.png)


The following screenshot displays the labels when the LabelPosition is set as *OutsideExtended* position.

![](Data-Markers_images/Data-Markers_img9.png)


The label can be wrapped for pie, doughnut, funnel, and pyramid series by setting the enableWrap property. 

{% highlight javascript %} 

<ej:Chart ID="Chart1" runat="server"> 
         <Series> 
              <ej:Series> 
                //.... . . 
                    <Marker>
                        <DataLabel Visible=’true’ EnableWrap=’true’ MaximumLabelWidth=’32’/>
                    </Marker>
                //.... . . 
               </ej:Series> 
         </Series> 
    //.... . . 
</ej:Chart>


{% endhighlight %} 

![](Data-Markers_images/Data-Markers_img13.png)




## Binding label from the datasource

You can bind the text value to the data label from the datasource and then you need to map the text value field with the **TextMappingName** property respectively.



{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientLoad="onChartLoad"> 
    <Series>
       <ej:Series>       
                //.... . . 
                    <Marker>
                        <DataLabel Visible=’true’ TextMappingName= "text"/>
                    </Marker>
                //.... . .                          
       </ej:Series>
    </Series>
</ej:Chart>
 
{% endhighlight %}


{% highlight js %}

//data source for chart with label 
var chartData = [
          { month: 'Jan', sales: 35 , text: 'January' },
          { month: 'Feb', sales: 28 , text: 'February' }
];
          
function onChartLoad(sender) {
    var data = GetData();
    sender.model.series[0].dataSource = chartData;
    sender.model.series[0].xName = "month";
    sender.model.series[0].yName = "sales";
}
   
{% endhighlight %}


## Binding fill color to the points from the datasource

You can bind the color value to the points from the datasource and then you need to map the color value field to the **PointColorMappingName** property respectively.



{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientLoad="onChartLoad"> 
    <Series>
       <ej:Series PointColorMappingName="color">       
                //.... . .                                                             
       </ej:Series>
    </Series>
</ej:Chart>
 
{% endhighlight %}


{% highlight js %}

//data source for chart with fill color
var chartData = [
          { month: 'Jan', sales: 35 , color: 'red' },
          { month: 'Feb', sales: 28 , color: 'blue' }
];
          
function onChartLoad(sender) {
    var data = GetData();
    sender.model.series[0].dataSource = chartData;
    sender.model.series[0].xName = "month";
    sender.model.series[0].yName = "sales";
}
   
{% endhighlight %}


## Customize specific points

By using the ejChart, you can also customize the individual/specific markers with different colors, shapes and also with different images.

There are two ways to achieve this based on how the data is fed to the series.

When the data is provided by using the Points option, you can add marker for each data point or specific point by using the Marker option as illustrated in the following code example.

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series Type="Line" LabelPosition="Outside">
            <Points>
                <ej:Points X="Jan" Y="35"></ej:Points>
                <ej:Points X="Feb" Y="28"></ej:Points>
                <ej:Points X="Mar" Y="34"></ej:Points>
                <ej:Points X="Apr" Y="32"></ej:Points>
                <ej:Points X="May" Y="40"></ej:Points>
                <ej:Points X="Jun" Y="32"></ej:Points>
                <ej:Points X="Jul" Y="35"></ej:Points>
                <ej:Points X="Aug" Y="55">
                    <Marker>
                        <%--Enable and customize the data label for a point--%>
                        <DataLabel Visible="true" Offset="-10" Shape="UpArrow" Fill="green">
                            <Font Color="white" FontSize="11px"></Font>
                            <Margin Right="15" Left="15" Top="10" Bottom="10" />
                        </DataLabel>
                    </Marker>
                </ej:Points>
                <ej:Points X="Sep" Y="38"></ej:Points>
                <ej:Points X="Oct" Y="30"></ej:Points>
                <ej:Points X="Nov" Y="25">
                     <Marker>
                        <%--Enable and customize the data label for a point--%>
                        <DataLabel Visible="true" Offset="-22" Shape="DownArrow" Fill="red" VerticalTextAlignment="Near">
                            <Font Color="white" FontSize="11px"></Font>
                            <Margin Right="15" Left="15" Top="10" Bottom="10" />
                        </DataLabel>
                    </Marker>
                </ej:Points>
                <ej:Points X="Dec" Y="32"></ej:Points>
            </Points>
            <Marker>
                <%--Place the data label text position in the centre of the rectangle--%>
                <DataLabel Visible="true" Shape="Rectangle">
                    <Font Color="white"></Font>
                </DataLabel>
            </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img10.png)


When the data is bound to the series by using the DataSource option, you can customize the points in the **SeriesRendering** event as illustrated  in the following code example,

{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientSeriesRendering="onSeriesRender"> 
    <Series>
        <%--Add datasource and set xName and yName --%>
        <ej:Series Type="Line" XName="Month" YName="Sales">
           
        </ej:Series>
    </Series>
</ej:Chart>
     
{% endhighlight %}

{% highlight csharp %}

      //Binding DataSource to Chart
      this.Chart1.DataSource = data;
      this.Chart1.DataBind();
            
{% endhighlight %}

{% highlight js %}

    //Define the seriesRendering client side event
  
     function onSeriesRender(sender) {
 
        
        //Enable and customize the dataLabel for a point using event

            sender.data.series.points[7].marker = {
               dataLabel: {
                    visible: true,
                    offset: -10,
                    shape: "upArrow", font: { color: "white", size: '11px' },
                    margin: { left: 15, right: 15, top: 10, bottom: 10 },                    
                    fill: "green"
                }};

            sender.data.series.points[10].marker = {
                 //Enable and customize the dataLabel for a point using event
                dataLabel: {
                        visible: true,
                        offset: -22,
                        verticalTextAlignment: 'near',
                        shape: "downArrow", font: { color: "white", size: '11px' },
                        margin: { left: 15, right: 15, top: 10, bottom: 10 },                    
                        fill: "red"
                }};
        }

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img10.png)


## Connect Line

This feature is used to connect label and data point by using a line. It can be enabled only for Pie, Doughnut, Pyramid and Funnel chart types. **ConnectorLine** types can be set as *Bezier* or *Line* by using the **Type** option.

 The following code example illustrates this,

{% highlight html %}

<ej:Chart ID="Chart1" runat="server" OnClientSeriesRendering="onSeriesRender"> 
    <Series>
        <ej:Series Type="Doughnut" LabelPosition="OutsideExtended">
           <Marker>
               <DataLabel Visible="true">
                   <%--Set connector line type and customize the color--%>
                   <ConnectorLine Color="black" Type="Bezier" />
               </DataLabel>
           </Marker>
        </ej:Series>
    </Series>
</ej:Chart>

{% endhighlight %}

![](Data-Markers_images/Data-Markers_img11.png)


## SmartLabels

Overlapping of the labels can be avoided by enabling the **EnableSmartLabels** property. The default value is *true* for *Accumulation type series* and *false* for *other series types*.

The following code example shows how to enable smart labels,

{% highlight html %}

<ej:Chart ID="Chart1" runat="server"> 
    <Series>
        <ej:Series Type="Pie" EnableSmartLabels="true" StartAngle="145" Name="Expense">
           <Marker>
               <DataLabel Visible="true" Shape="None">
                   <%--Set connector line type and customize the color--%>
                   <ConnectorLine Color="black" Type="Bezier" />
                   <Font FontSize="14px"></Font>
               </DataLabel>
           </Marker>
        </ej:Series>
    </Series>
</ej:Chart>


{% endhighlight %}

![](Data-Markers_images/Data-Markers_img12.png)


[Click](http://asp.syncfusion.com/demos/web/chart/pie.aspx) here to view the SmartLabels online demo sample.