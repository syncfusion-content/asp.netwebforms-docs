---
layout: post
title: Customize Drag and Drop element while grouping | Grid | ASP.NET Webforms | Syncfusion
description: Learn about Easy Customization support in Syncfusion ASP.NET Webforms Grid control, its elements, and more.
platform: aspnet
control: Grid
documentation: ug
---

# Customize Drag and Drop element while grouping in ASP.NET Webforms Grid

In this section, you can learn how to customize drag and drop element. This drag and drop element is framed by using CSS classes with default values. When you want to change or customize drag and drop element, then just override default values of CSS class values. e-cloneproperties is the name of drag and drop element in CSS class.

{% highlight css %}

<style type="text/css">

.e-grid .e-cloneproperties {

            background-color: black;

        }

</style>

<ej:Grid ID="OrdersGrid" runat="server" AllowGrouping="True">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>

 </ej:Grid>



{% endhighlight %}





The following output is displayed as a result of the above code example.

![ASP.NET Webforms Grid Customize Drag and Drop element while grouping](Customize-Drag-and-Drop-element-while-grouping_images/Customize-Drag-and-Drop-element-while-grouping_img1.png) 



