---
layout: post
title: Toolbar Customization | ReportViewer | ASP.NET | Syncfusion
description: toolbar customization
platform: aspnet
control: ReportViewer
documentation: ug
---

# Toolbar Customization

The ReportViewer has an option to show or hide items in the toolbar. To customize the toolbar items, use the ReportViewer’s  ToolbarSettings property. The toolbar template can also be customized by specifying custom template to ReportViewer toolbar.

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
    this.viewer.ToolbarSettings.Items = Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.All & ~Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.Parameters;
}

{% endhighlight %}