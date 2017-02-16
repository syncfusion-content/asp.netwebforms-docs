---
layout: post
title: Layout Customization | PivotClient | ASP.NET | Syncfusion
description: layout customization
platform: aspnet
control: PivotClient
documentation: ug
---

# Layout Customization

# Size

Allows you to render PivotClient in different sizes. You can set height and width under `size` property.

## Set size in Pixels

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1"  runat="server">
         <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <size Height="685px" Width="1000px"></size>
        <ClientSideEvents Load="onLoad" />
    </ej:PivotClient>

{% endhighlight  %}

PivotClient with decreased size from default size

![](Layout-Customization_images/small-size.png)

## Set size in Percentage

You can set the PivotClient size in percentage also.

N> Size of the parent container Should be set in Pixels.

{% highlight html %}
//...
<size Height="80%" Width="50%"></size>

{% endhighlight  %}

## Control Placement

### Tab View

In Tab View representation, both Grid and Chart will be displayed in separate tabs.  This could be set by using the `ControlPlacement` property under the `DisplaySettings` option.  By default, **Tab** value is set.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1"  runat="server">
         <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <DisplaySettings ControlPlacement="Tab" />
        <ClientSideEvents Load="onLoad" />
    </ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/tabview.png) 

### Tile View

In Tile View representation, both Grid and Chart will be displayed one above the other, in the same layout.  Tile view can be set by using the `ControlPlacement` property under the `DisplaySettings` option.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" runat="server">
         <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <ClientSideEvents Load="onLoad"/>
        <DisplaySettings ControlPlacement="Tile" />
    </ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/tileview.png) 

## Default View

### Grid View

To display Grid control by default, set `DefaultView` property under `DisplaySettings` option to **Grid**, which is the default value of the property.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" runat="server">
        <DataSource>
                <Rows>
                    <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
                </Rows>
                <Columns>
                    <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
                </Columns>
                <Values>
                    <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
                </Values>
            </DataSource>
            <ClientSideEvents Load="onLoad"/>
            <DisplaySettings DefaultView="Grid" />
    </ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/gridview.png) 

### Chart View

To display Chart control by default, set the property `DefaultView` property to **Chart**.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" runat="server">
     <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
    <ClientSideEvents Load="onLoad"/>
    <DisplaySettings DefaultView="Chart" />
</ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/chartview.png) 

## Display Mode

### Grid Only

By the `Mode` property under `DisplaySettings` option to **GridOnly**, PivotGrid component alone will get rendered and PivotChart will not be rendered.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" runat="server">
        <DataSource>
                <Rows>
                    <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
                </Rows>
                <Columns>
                    <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
                </Columns>
                <Values>
                    <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
                </Values>
            </DataSource>
            <ClientSideEvents Load="onLoad"/>
        <DisplaySettings Mode="GridOnly" />
    </ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/gridonlyview.png) 


### Chart Only

By the `Mode` property under `DisplaySettings` option to **ChartOnly**, PivotChart component alone will get rendered and PivotChart will not be rendered .

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1" runat="server">
            <DataSource>
                <Rows>
                    <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
                </Rows>
                <Columns>
                    <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
                </Columns>
                <Values>
                    <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
                </Values>
            </DataSource>
            <ClientSideEvents Load="onLoad"/>
        <DisplaySettings Mode="ChartOnly" />
    </ej:PivotClient>

{% endhighlight  %}

![](Layout-Customization_images/chartonlyview.png) 

### Both Chart and Grid

By the `Mode` property under `DisplaySettings` option to **ChartAndGrid**, data is displayed in both Grid and Chart.  This is the default value of the property.

{% highlight html %}

    <ej:PivotClient   ID="PivotClient1" runat="server">
        <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <ClientSideEvents Load="onLoad"/>
        <DisplaySettings Mode="ChartAndGrid" />
    </ej:PivotClient>

{% endhighlight  %}	

![](Layout-Customization_images/tileview.png) 

## Toggle Panel

Toggle panel option lets the user to toggle the visibility of Axis Element Builder and Cube Dimension Browser panels in PivotClient with a use of a button. The button could be added to the control by enabling the `EnableTogglePanel` property under `DisplaySettings` option.  This property is disabled by default.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1"  runat="server">
        <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <ClientSideEvents Load="onLoad"/>
        <DisplaySettings EnableTogglePanel="true" />
    </ej:PivotClient>

{% endhighlight  %}	

![](Layout-Customization_images/toggleview.png) 

## Maximized/Full Screen View

Full screen view helps to visualize the PivotGrid and PivotChart controls inside PivotClient precisely according to the browser window size.  By selecting full screen icon in the toolbar, the control which is in the view gets maximized.  Drilldown action can also be performed in both PivotGrid and PivotChart in the maximized view.  This option is enabled by setting the `EnableFullScreen` property under `DisplaySettings` option to true.  The value is false by default.


{% highlight html %}

    <ej:PivotClient  ID="PivotClient1"  runat="server">
        <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <ClientSideEvents Load="onLoad" />
        <DisplaySettings EnableFullScreen="true" />
    </ej:PivotClient>

{% endhighlight  %}	

![](Layout-Customization_images/maximizedview.png) 

The following screenshot shows the maximized view of PivotGrid.

![](Layout-Customization_images/maximizedview1.png) 


## Chart Types

While loading the PivotClient initially, the PivotChart widget can be rendered in any one of the available chart types using the `ChartType` property.

{% highlight html %}

    <ej:PivotClient   ID="PivotClient1" runat="server" ChartType="Column">
        <DataSource>
            <Rows>
                <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            </Rows>
            <Columns>
                <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
            </Columns>
            <Values>
                <ej:Field FieldName="Amount" FieldCaption="Amount"></ej:Field>
            </Values>
        </DataSource>
        <ClientSideEvents Load="onLoad"/>
    </ej:PivotClient>

{% endhighlight  %}	

The `ChartType` property takes Column Chart by default. The types available are Column, Stacking Column, Bar, Stacking Bar, Line, Spline, Step Line, Area, Spline Area, Step Area, Stacking Area, Pie, Funnel and Pyramid.

The Chart Type can also be changed dynamically through the toolbar icon.

![](Layout-Customization_images/charttypes.png) 

![](Layout-Customization_images/linechart.png)  

### PivotTreeMap

I> This feature is applicable only for OLAP data source bound from server-side.

You can include the PivotTreeMap component as one of the chart types by setting `EnablePivotTreeMap` property to true.

{% highlight html %}

    <ej:PivotClient ID="PivotClient1" runat="server" EnablePivotTreeMap="true">
            <DataSource>
                <Rows>
                    <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
                </Rows>
                <Columns>
                    <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
                </Columns>
                <Values>
                    <ej:Field FieldName="Amount" FieldCaption="Amount" Format="currency"></ej:Field>
                </Values>
            </DataSource>
            <ClientSideEvents Load="onLoad" />
    </ej:PivotClient>

{% endhighlight %}

![](Layout-Customization_images/TreeMap1.png)

![](Layout-Customization_images/TreeMap2.png)


## Report Toolbar

You can customize the display of toolbar by enabling/disabling the visibility of each of the icons. This can be achieved by setting the properties under `ToolbarIconSettings` option to false. The values are true by default.​​​

{% highlight html %}

<ej:PivotClient  ID="PivotClient1"  runat="server">
        //...
        <ToolbarIconSettings EnableAddReport="false" EnableNewReport="false" EnableRemoveReport="false" />
    </ej:PivotClient>

{% endhighlight %}

![](Layout-Customization_images/toolbarIconSettings1.png)

The following screenshot shows after disabling the toolbar icons.

![](Layout-Customization_images/toolbarIconSettings2.png)
