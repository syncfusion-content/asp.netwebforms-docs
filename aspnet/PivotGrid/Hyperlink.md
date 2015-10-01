---
layout: post
title: Hyperlink | PivotGrid | ASP.NET | Syncfusion
description: hyperlink
platform: aspnet
control: PivotGrid
documentation: ug
---

# Hyperlink

The PivotGrid control supports Hyperlink option to link data for any individual cell. Hyperlinks are enabled individually for value, row, column, and summary cells by setting the corresponding property to ‘True’. After enabling the property, the specified cells display Hyperlink on hovering. The name of the event to be triggered is passed to the correspondingevent property. On clicking the cells, the passed event is triggered and the information of the cell is carried through a parameter.

The following code example demonstrates how to create the PivotGrid control using Hyperlink support.

{% highlight html %}
<ej:PivotGrid ID="PivotGrid1" runat="server" Url="../wcf/PivotGridService.svc">

    <HyperlinkSettings EnableColumnHeaderHyperlink="true" EnableRowHeaderHyperlink="true"      EnableSummaryCellHyperlink ="true" EnableValueCellHyperlink="true" />

    <ClientSideEvents ValueCellHyperlinkClick="CellClickEvent" RowHeaderHyperlinkClick="CellClickEvent" ColumnHeaderHyperlinkClick="CellClickEvent" SummaryCellHyperlinkClick="CellClickEvent" />

</ej:PivotGrid>

<script type="text/javascript">

        CellClickEvent = function (evt) {

            alert("Cell Click event is fired");

        }

</script>
{% endhighlight %}

The output of the above code creates a PivotGrid with the Hyperlink option as shown in the following screenshot:

![](Hyperlink_images/Hyperlink_img1.png) 

Hyperlink Cell
{:.caption}
