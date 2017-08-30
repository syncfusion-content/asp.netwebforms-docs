---
layout: post
title: Highlight
description: What are the different modes of highlight present in the Sunburst Chart
platform: aspnet
control: Sunburst Chart
documentation: ug
---

# Highlight 
SunburstChart provides highlighting support for the points on mouse hover. To enable the highlighting , set the *Enable* property to true in the **HighlightSettings**. 

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Highlight_images/Highlight_img1.png)

 
## Highlight Display mode

 You can customize the highlighted segment appearance by using color or opacity. You can choose between color or opacity using the **Type** property in the highlight Settings.

*	HighlightByColor – To display the highlighted segment appearance using color.
*	HighlightByOpacity – To display the highlighted segment appearance using opacity.

{% highlight html %}


<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" Type="Color" Color="Red" />                            
</ej:SunburstChart> 

 {% endhighlight %}

![](Highlight_images/Highlight_img2.png)

## Highlight Mode

Sunburst chart provides multiple option to represent the highlighted categories. You can highlight the segment categories by using the **Mode** property in highlightSettings
*	Child – To highlight the child of selected parent.
*	All – To highlight the entire categories in group.
*	Parent – To highlight the parent of selected child.
*	Single - To highlight single item in the category.

### Child
The following code shows how to set the highlight type as child 

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" Mode="Child" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Highlight_images/Highlight_img3.png)
 
### Parent

The parent mode can be enabled by using the below code 

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" Mode="Parent" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Highlight_images/Highlight_img4.png)
 
### Point

To highlight the particular segment, the point mode of the highlight settings is used.

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" Mode="Point" />                            
</ej:SunburstChart> 

 {% endhighlight %}

![](Highlight_images/Highlight_img5.png)
 
### All

The following code snippet is used for the all mode of highlight settings

{% highlight html %}

<ej:SunburstChart  ID="container" runat="server"> 
<HighlightSettings Enable="true" Mode="All" />                            
</ej:SunburstChart> 

{% endhighlight %}

![](Highlight_images/Highlight_img6.png)


[Click](http://asp.syncfusion.com/demos/web/sunburstchart/selection.aspx) here to view the Highlighting sample of the  Sunburst Chart.
