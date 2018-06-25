---
layout: post
title: Appearance and Styling | TreeGrid | ASP.NET | Syncfusion
description: appearance and styling
platform: aspnet
control: TreeGrid
documentation: ug
---

# Appearance and Styling

You can customize the look and feel of the TreeGrid control by applying themes.

You are provided the following twelve different themes in TreeGrid control.

1. Flat Azure 
2. Flat Azure Dark
3. Flat Lime    
4. Flat Lime Dark 
5. Flat Saffron 
6. Flat Saffron Dark
7. Gradient Azure
8. Gradient Azure Dark
9. Gradient Lime
10. Gradient Lime Dark
11. Gradient Saffron
12. Gradient Saffron Dark
13. Bootstrap
14. High Contrast 01
15. High Contrast 02
16. Material
17. Office-365

You can apply the theme (Gradient lime) to the TreeGrid control by using the style sheet from the online link as follows.

{% highlight html %}

<!DOCTYPE html>
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<title>Getting Started with TreeGrid Control for JavaScript</title>
<!-- style sheet for default theme(gradient lime) -->
<link href=" http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet">
</html>

{% endhighlight %}

The following screenshot shows the TreeGrid control with Gradient-lime theme.

![]
(Appearance-and-Styling_images/Appearance-and-Styling_img1.png)

## Configuring CSS class

In TreeGrid `CssClass` property is used to apply different custom styles to multiple TreeGrid controls available in the webpage.

The following code example shows how to apply different background color for each TreeGrid control's toolbar element.

{% highlight html %}
<style>
    .c-class1.e-treegrid .e-toolbar {
        background-color: rgba(169, 45, 45, 0.31);
    }
    .c-class2.e-treegrid .e-toolbar {
        background-color: rgba(0, 128, 0, 0.2);
    }
</style>

<ej:TreeGrid ID="TreeGridContainer" CssClass = "c-class1">
</ej:TreeGrid>

<ej:TreeGrid ID="TreeGridContainer1" CssClass = "c-class2">
</ej:TreeGrid>
@(Html.EJ().ScriptManager())

{% endhighlight %}

The below screenshot shows the output of above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png)

![](Appearance-and-Styling_images/Appearance-and-Styling_img3.png)

## Customize rows and cells

In TreeGrid, while rendering rows  `RowDataBound` event will be triggered for rows. Similarly `QueryCellInfo` event will be triggered for every cells. Using these events we can customize the TreeGrid rows and cells at initial load.

The below code example shows how to customize the rows and cells in TreeGrid.

{% highlight html %}

<ej:TreeGrid ID="TreeGridContainer"   QueryCellInfo="queryCellInfo" RowDataBound="rowDataBound">
</ej:TreeGrid>

<asp:ScriptManager ID="ScriptManager" runat="server"/>
<script type="text/javascript">
function queryCellInfo(args) {
    if (args.column.mappingName == "progress") {
        if (args.data.item["progress"] < 75)
            $(args.cellElement).css("background-color", "rgba(255, 0, 0, 0.12)");
        else
            $(args.cellElement).css("background-color", "rgba(86, 226, 86, 0.25)");
    }
}
function rowDataBound(args) {
    if (args.data.item["taskID"] == 5)
        $(args.rowElement).css("background-color", "rgba(251, 255, 0, 0.24)");
}

</script>

{% endhighlight %}

The below screenshot shows the output of above code example.

![](Appearance-and-Styling_images/Appearance-and-Styling_img4.png)