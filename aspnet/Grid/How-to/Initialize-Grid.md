---
layout: post
title: Initialize Grid | Grid | ASP.NET Webforms | Syncfusion
description: initialize grid
platform: aspnet
control: Grid
documentation: ug
---

## Initialize Grid

In this section, you can learn about Grid’s mandatory property to render a simple Grid. To initialize Grid, it needs two important properties. They are columns and its inner property field. Columns are used to define schema of Grid and field is mapping a name to the data source.

{% highlight html %}

  <ej:Grid ID="FlatGrid" runat="server">

            <Columns>

                <ej:Column Field="OrderID" />

                <ej:Column Field="CustomerID" />

                <ej:Column Field="EmployeeID" />

            </Columns>

        </ej:Grid>
		
		 {% endhighlight %}

The following output is displayed as a result of the above code example.

![](Initialize-Grid_images/Initialize-Grid_img1.png)



