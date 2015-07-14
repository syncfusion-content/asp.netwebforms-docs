---
layout: post
title: Customize-Drag-and-Drop-element-while-grouping
description: customize drag and drop element while grouping
platform: aspnet
control: Grid
documentation: ug
---

### Customize Drag and Drop element while grouping

In this section, you can learn how to customize drag and drop element. This drag and drop element is framed by using CSS classes with default values. When you want to change or customize drag and drop element, then just override default values of CSS class values. e-cloneproperties is the name of drag and drop element in CSS class.

[ASP]



[aspx]

&lt;style type="text/css"&gt;

.e-grid .e-cloneproperties {

            background-color: black;

        }

&lt;/style&gt;



&lt;ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True"&gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;

 &lt;/ej:Grid&gt;









The following output is displayed as a result of the above code example.

{ ![](Customize-Drag-and-Drop-element-while-grouping_images/Customize-Drag-and-Drop-element-while-grouping_img1.png) | markdownify }
{:.image }


