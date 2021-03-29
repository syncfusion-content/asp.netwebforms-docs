---
layout: post
title: Drill Down Support | TreeMap | ASP.NET | Syncfusion
description: drill down support
platform: aspnet
control: TreeMap
documentation: ug
---

# Drill Down Support

Treemap enables drill down to expose the hierarchy achieved by clicking on a node and this results in enabling the Treemap to move to the next level or sub level and can return back to the normal Treemap view by clicking on the node header. Only a single level of the Treemap is visible at once.

### Enabling Drill Down

Treemap elements can be drilled down by setting the `EnableDrillDown` property to true. You can view the hierarchy of the Treemap by clicking on the treemap items and can move to the previous level by clicking on the drill down header. The header color can be customized by changing the values in the property `DrillDownHeaderColor` and the selection color can be done by changing the `DrillDownSelectionColor` property.


<table>
<tr>
<th>
Property</th><th>
Type</th><th>
Description</th></tr>
<tr>
<td>
enableDrillDown</td><td>
bool</td><td>
Gets or sets a value that indicates whether the drill down feature is enabled or not</td></tr>
<tr>
<td>
drillDownHeaderColor</td><td>
string</td><td>
Gets or sets a color for header during drill down</td></tr>
<tr>
<td>
drillDownSelectionColor</td><td>
string</td><td>
Gets or sets a color for highlighting tree map item during drill down.</td></tr>
</table>

{% tabs %}
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

    this.treemap.DataSource = TreeMapPopulationData.GetData();

}

{% endhighlight  %}

{% highlight html %}

    <div style="min-height:404px">

    <ej:TreeMap ID="treemap" runat="server"  EnableDrillDown = "true" DrillDownHeaderColor= "#199DAF" drillDownSelectionColor = "#199DAF" WeightValuePath="Population" >

        <TreeMapUniColorMapping Color = "#CCDFE3"></TreeMapUniColorMapping>

        <Levels>

            <ej:TreeMapLevel GroupPath = "Continent" ShowLabels = "true" GroupGap = "5" HeaderHeight = "25"></ej:TreeMapLevel>

            <ej:TreeMapLevel GroupPath = "Country" ShowLabels = "true" GroupGap = "0" HeaderHeight = "25"></ej:TreeMapLevel>

            <ej:TreeMapLevel GroupPath = "Name" ShowLabels = "true" GroupGap = "0" HeaderHeight = "25"></ej:TreeMapLevel>

        </Levels>

    </ej:TreeMap>

    </div>

{% endhighlight  %}
{% endtabs %}

![ASPNET TreeMap Drill-Down-Support Image1](Drill-Down-Support_images/Drill-Down-Support_img1.png) 

![ASPNET TreeMap Drill-Down-Support Image2](Drill-Down-Support_images/Drill-Down-Support_img2.png) 