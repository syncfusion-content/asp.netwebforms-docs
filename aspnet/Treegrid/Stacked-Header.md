---
layout: post
title: Stacked Header | TreeGrid | ASP.NET | Syncfusion
description: stacked header
platform: aspnet
control: TreeGrid
documentation: ug
---

# Stacked Headers

The stacked headers helps you to group the logical columns in treegrid. It can be shown by setting `ShowStackedHeader` as `true` and by defining `StackedHeaderRows`.

## Adding Stacked header columns

To stack columns in stacked header, you need to define `Column` property in `StackedHeaderColumns` with field names of visible columns.

{% highlight html %}

<ej:TreeGrid runat="server" ID="TreeGridControl" ShowStackedHeader="true" >
            <Columns>
                <ej:TreeGridColumn HeaderText="S.No" Field="ID" Width="45" />
                <ej:TreeGridColumn HeaderText="Shipment Name" Field="Name" />
                <ej:TreeGridColumn HeaderText="Category" Field="Category" />
                <ej:TreeGridColumn HeaderText="Units" Field="Units" />
                <ej:TreeGridColumn HeaderText="Unit Price($)" Field="UnitPrice" />
                <ej:TreeGridColumn HeaderText="Price($)" Field="Price" />
            </Columns>            
            <StackedHeaderRows>
                <ej:TreeGridStackedHeaderRow>
                    <StackedHeaderColumns>
                        <ej:TreeGridStackedHeaderColumn Column="ID,Name,Category,Units" HeaderText="Shipment Details" TextAlign="center" />
                        <ej:TreeGridStackedHeaderColumn Column="UnitPrice,Price" HeaderText="Price Details" TextAlign="center"  />
                    </StackedHeaderColumns>
                </ej:TreeGridStackedHeaderRow>
            </StackedHeaderRows>
        </ej:TreeGrid>

{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img1.png)

## Stacked header column customization

we can customize the stacked header cells with more options as described below.

### CSS Class

You can provide external CSS styles to the stacked header with the help of `CssClass` property.

{% highlight html %}

<style>
  .stack {
            background-color: #ffb3b3; 
        }
</style>

 <ej:TreeGrid runat="server" ID="TreeGridControl" ShowStackedHeader="true">
            <StackedHeaderRows>
                <ej:TreeGridStackedHeaderRow>
                    <StackedHeaderColumns>
                        <ej:TreeGridStackedHeaderColumn Column="ID,Name,Category,Units" HeaderText="Shipment Details" CssClass="stack" />
                        <ej:TreeGridStackedHeaderColumn Column="UnitPrice,Price" HeaderText="Price Details"  />
                    </StackedHeaderColumns>
                </ej:TreeGridStackedHeaderRow>
            </StackedHeaderRows>
        </ej:TreeGrid>
{% endhighlight %}
![](Stacked-header_images/Stacked-Header-img2.png)

### Text Align

There is an option to align the stacked header text inside the header cell using `TextAlign` property as follows.

{% highlight html %}
 <ej:TreeGrid runat="server" ID="TreeGridControl" ShowStackedHeader="true">
            <StackedHeaderRows>
                <ej:TreeGridStackedHeaderRow>
                    <StackedHeaderColumns>
                        <ej:TreeGridStackedHeaderColumn Column="ID,Name,Category,Units" HeaderText="Shipment Details" TextAlign="left"  />
                        <ej:TreeGridStackedHeaderColumn Column="UnitPrice,Price" HeaderText="Price Details" TextAlign="right"  />
                    </StackedHeaderColumns>
                </ej:TreeGridStackedHeaderRow>
            </StackedHeaderRows>
        </ej:TreeGrid>
{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img4.png)

### Tooltip

We can have the customized tooltip for the stacked header text with the help of `ToolTip` property. JsRender template script id can be assigned to this property to get tooltip.

{% highlight html %}
<ej:TreeGrid runat="server" ID="TreeGridControl" ShowStackedHeader="true" ShowGridCellTooltip="true">
            <StackedHeaderRows>
                <ej:TreeGridStackedHeaderRow>
                    <StackedHeaderColumns>
                        <ej:TreeGridStackedHeaderColumn Column="ID,Name,Category,Units" HeaderText="Shipment Details"  />
                        <ej:TreeGridStackedHeaderColumn Column="UnitPrice,Price" HeaderText="Price Details" ToolTip="#tooltip"  />
                    </StackedHeaderColumns>
                </ej:TreeGridStackedHeaderRow>
            </StackedHeaderRows>
        </ej:TreeGrid>
<script id="tooltip" type="text/x-jsrender">
        <div>Custom Tooltip</div>
</script> 

{% endhighlight %}

![](Stacked-header_images/Stacked-Header-img3.png)

N>
To enable stacked header tooltip we need to set `ShowGridCellTooltip` as `true`.

[Click](http://asp.syncfusion.com/demos/web/treegrid/treegridstackedheader.aspx) here to view the demo sample for stacked header.