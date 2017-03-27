---
layout: post
title: Selection
description: What are the different modes of selection present in the Sunburst Chart
platform: aspnet
control: SunburstChart
documentation: ug
---

# Selection 
SunburstChart provides selection support for the points on mouse click. To enable the selection , set the *Enable* property to true in the **SelectionSettings**. 

{% highlight js %}


<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Selection_images/Selection_img1.png)

 
## Selection Display mode

 You can customize the selected  segment appearance by using color or opacity. You can choose between color or opacity using the **Type** selection Settings.

*	selectionByColor – To display the selected segment appearance using color.
*	selectionByOpacity – To display the selected segment appearance using opacity.

{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" Type="Color" Color="Red" />                            
</ej:SunburstChart> 

 {% endhighlight %}

![](Selection_images/Selection_img2.png)

## Selection Mode

Sunburst chart provides multiple option to represent the selected categories. You can select the segment categories by using the **Mode** property in selectionSettings
*	Child – To selection the child of selected parent.
*	All – To selection the entire categories in group.
*	Parent – To selection the parent of selected child.
*	Single - To selection single item in the category.

### Child
The following code shows how to set the selection type as child 

{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" Mode="Child" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Selection_images/Selection_img3.png)
 
### Parent

The parent mode can be enabled by using the below code 

{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" Mode="Parent" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Selection_images/Selection_img4.png)
 
### Point

To selection the particular segment, the point mode of the selection settings is used.

{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" Mode="Point" />                            
</ej:SunburstChart> 

 {% endhighlight %}

![](Selection_images/Selection_img5.png)
 
### All

The following code snippet is used for the all mode of selection settings

{% highlight js %}

<ej:SunburstChart  ID="container" runat="server"> 
<SelectionSettings Enable="true" Mode="All" />                            
</ej:SunburstChart> 


{% endhighlight %}

![](Selection_images/Selection_img6.png)

[Click](http://asp.syncfusion.com/demos/web/sunburstchart/selection.aspx) here to view the Selection sample of the  Sunburst Chart.

