---
layout: post
title: Toolbar-Customization
description: toolbar customization
platform: aspnet
control: ReportViewer
documentation: ug
---

## Toolbar Customization

The ReportViewer has an option to show or hide items in the toolbar. To customize the toolbar items, use the ReportViewer’sToolbarSettings property. The toolbar template can also be customized by specifying custom template to ReportViewertoolbar.





[EJWEB]

[C#]

protected void Page_Load(object sender, EventArgs e)

        {

            this.viewer.ToolbarSettings.Items = Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.All & ~Syncfusion.JavaScript.ReportViewerEnums.ToolbarItems.Parameters;

        }



