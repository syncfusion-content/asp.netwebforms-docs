---
layout: post
title: Miscellaneous | ColorPicker | ASP.NET Webforms | Syncfusion
description: miscellaneous
platform: aspnet
control: ColorPicker
documentation: ug
---

# Miscellaneous

## getValue

The **getValue()** method in the ColorPicker returns the hexadecimal value.

Add the following code example to the corresponding ASPX page to render the ColorPicker control.



{% highlight html %}



<ej:ColorPicker runat="server" ID="colorpicker" Value="#278787"> </ej:ColorPicker>





{% endhighlight %}



Add the following code in the script section.



{% highlight js %}

    var ColorObj;

    jQuery(function ($)

    {

        ColorObj = $("#<%=colorpicker.ClientID%>").ejColorPicker({ value: "#278787" }).data('ejColorPicker');

        ColorObj.getValue();

    });



{% endhighlight %}



## setValue

The **setValue()** method in ColorPicker is used to set the color value. The given value is hexadecimal form.

Add the following code example to the corresponding ASPX page to render the ColorPicker control



{% highlight html %}



<ej:ColorPicker runat="server" ID="colorpicker" ></ej:ColorPicker>





{% endhighlight %}



Add the following code in the script section.



{% highlight js %}

     var ColorObj;

     jQuery(function ($)

     {

        ColorObj = $("#<%=colorpicker.ClientID%>").ejColorPicker().data('ejColorPicker');

        ColorObj.setValue("#278787");

     });



{% endhighlight %}



## getColor

The **getColor()** method in ColorPicker control returns the color value in r,g,b form.

Add the following code example to the corresponding ASPX page to render the ColorPicker control



{% highlight html %}



<ej:ColorPicker runat="server" ID="colorpicker" Value="#278787"> </ej:ColorPicker>





{% endhighlight %}



Add the following code in the script section.



{% highlight js %}

     var ColorObj;

     jQuery(function ($)

     {

         ColorObj = $("#<%=colorpicker.ClientID%>").ejColorPicker({ value: "#278787" }).data('ejColorPicker');

         ColorObj.getColor();

     });



{% endhighlight %}



