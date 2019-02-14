---
layout: post
title: Layout Customization | PivotClient | ASP.NET | Syncfusion
description: layout customization
platform: aspnet
control: PivotClient
documentation: ug
---

# Layout customization

# Size

Allows you to render the pivot client in different sizes. You can set the height and width under the `size` property.

## Set size in pixels

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

The pivot client with decreased size from default size.

![ASP NET pivot client control with reduced size](Layout-Customization_images/small-size.png)

## Set size in percentage

You can set the pivot client size in percentage also.

N> The size of the parent container should be set in pixels.

{% highlight html %}
//...
<size Height="80%" Width="50%"></size>

{% endhighlight  %}

## Control placement

### Tab view

In tab view representation, both the grid and chart will be displayed in separate tabs. This can be set by using the `ControlPlacement` property under the `DisplaySettings` option. By default, the **Tab** value is set.

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

![ASP NET pivot client control with tab view](Layout-Customization_images/tabview.png)

### Tile view

In tile view representation, both the grid and chart will be displayed one above the other in the same layout. The tile view can be set by using the `ControlPlacement` property under the `DisplaySettings` option.

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

![ASP NET pivot client control with tile view](Layout-Customization_images/tileview.png)

## Default view

### Grid view

To display grid control by default, set the `DefaultView` property under the `DisplaySettings` option to **Grid**, which is the default value of the property.

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

![ASP NET pivot client control with grid view as default](Layout-Customization_images/gridview.png)

### Chart view

To display the chart control by default, set the `DefaultView` property to the **Chart**.

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

![ASP NET pivot client control with chart view as default](Layout-Customization_images/chartview.png)

## Display mode

### Grid only

In the `Mode` property, the `DisplaySettings` option is set to **GridOnly**, such that the pivot grid component alone will get rendered and the pivot chart will not be rendered.

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

![ASP NET pivot client control with grid only view](Layout-Customization_images/gridonlyview.png)


### Chart only

In the `Mode` property, the `DisplaySettings` option is set to **ChartOnly**, such that the pivot chart component alone will get rendered and the pivot grid will not be rendered.

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

![ASP NET pivot client control with chart only view](Layout-Customization_images/chartonlyview.png)

### Both chart and grid

In the `Mode` property, set the `DisplaySettings` option to **ChartAndGrid**, the data is displayed in both the grid and the chart. This is the default value of the property.

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

![ASP NET pivot client control with grid and chart view](Layout-Customization_images/tileview.png)

## Toggle panel

Toggle panel option allows you to toggle the visibility of axis element builder and cube dimension browser panels in the pivot client by using a button. The button can be added to the control by enabling the `EnableTogglePanel` property under the `DisplaySettings` option. This property is disabled by default.

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

![ASP NET pivot client control with toggle panel](Layout-Customization_images/toggleview.png)

## Collapse Toggle Panel By Default

Allows the user to hide “Cube Browser” and “Axis Element Builder” panels while initiating the widget. You can enable this option in PivotClient by setting the `CollapseCubeBrowserByDefault` property to true.

{% highlight html %}

    <ej:PivotClient  ID="PivotClient1"  runat="server" CollapseCubeBrowserByDefault="true">
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

![ASP NET pivot client control with toggle panel by default](Layout-Customization_images/collapse-cube-browser-by-default.png)

## Maximized/Full Screen View

The full screen view helps to visualize the pivot grid and pivot chart controls in the pivot client precisely according to the browser window size. By selecting the full screen icon in the toolbar, the control which is in the view gets maximized. The drilldown action can also be performed in both pivot grid and pivot chart in maximized view. This option is enabled by setting the `EnableFullScreen` property under `DisplaySettings` option to true. The value is false by default.


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

![Full screen icon in ASP NET pivot client control](Layout-Customization_images/maximizedview.png)

The following screenshot shows the maximized view of the pivot grid:

![Full screen view of ASP NET pivot client control](Layout-Customization_images/maximizedview1.png)


## Chart types

While loading the pivot client initially, the pivot chart widget can be rendered in anyone of the available chart types by using the `ChartType` property.

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

The `ChartType` property takes column chart by default. The available types are column, stacking column, bar, stacking bar, line, spline, step line, area, spline area, step area, stacking area, pie, funnel, and pyramid.

The chart type can also be changed dynamically through the toolbar icon.

![Chart types icon in ASP NET pivot client control](Layout-Customization_images/charttypes.png)

![ASP NET pivot client control with line chart type](Layout-Customization_images/linechart.png)

### Pivot tree map

I> This feature is applicable only for the OLAP data source bound from the server-side.

You can include the pivot tree map component as one of the chart types by setting the `EnablePivotTreeMap` property to true.

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

![Treemap icon in chart types panel of ASP NET pivot client control](Layout-Customization_images/TreeMap1.png)

![Treemap in ASP NET pivot client control](Layout-Customization_images/TreeMap2.png)


## Report toolbar

You can customize the display of toolbar by enabling/disabling the visibility of each icon. This can be achieved by setting the properties under `ToolbarIconSettings` option to false. The values are true by default.​​​

{% highlight html %}

<ej:PivotClient  ID="PivotClient1"  runat="server">
        //...
        <ToolbarIconSettings EnableAddReport="false" EnableNewReport="false" EnableRemoveReport="false" />
    </ej:PivotClient>

{% endhighlight %}

![Report toolbar in ASP NET pivot client control](Layout-Customization_images/toolbarIconSettings1.png)

The following screenshot shows after disabling the toolbar icons:

![Hiding report icons from toolbar of ASP NET pivot client control](Layout-Customization_images/toolbarIconSettings2.png)
