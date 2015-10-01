---
layout: post
title: Miscellaneous | DatePicker | ASP.NET Webforms | Syncfusion
description: miscellaneous
platform: aspnet
control: DatePicker
documentation: ug
---

# Miscellaneous

## Define height

It specifies the Height of the DatePicker input text. The Height property allows you to set the maximum Height of the DatePicker. The value set to this property should be string or Numer type.

In the ASPX page, include the following DatePicker control code example to configure the height.



{% highlight html %}

  <ej:DatePicker ID="datepicker" runat="server" Height="22"></ej:DatePicker>



{% endhighlight %}

## Define width

It specifies the Width of the DatePicker input text. The Width property allows you to set the maximum Width of the DatePicker. The value set to this property should be string or Numer type

In the ASPX page, include the following DatePicker control code example to configure the width.



{% highlight html %}



<ej:DatePicker ID="datepicker" runat="server"  Width="200"></ej:DatePicker>





{% endhighlight %}

## Highlight Section

Highlight section highlights the current month, current week, current workdays. You can highlight a week, month, and work days by using HighlightSection property.

<table>
<tr>
<th>
Name</th><th>
Description</th></tr>
<tr>
<td>
Month</td><td>
Highlights the Current Month.</td></tr>
<tr>
<td>
Week</td><td>
Highlights the Current Week.</td></tr>
<tr>
<td>
WorkDays</td><td>
Highlights the Current Workdays.</td></tr>
<tr>
<td>
None</td><td>
Does not Highlight anything.</td></tr>
</table>


In the ASPX page, include the following DatePicker control code example to highlight the current week.



<ej:DatePicker ID="datepicker" runat="server" HighlightSection="Week"></ej:DatePicker>





The following screenshot displays the output for the above code.   

![](Miscellaneous_images/Miscellaneous_img1.png) 





## ReadOnly

Readonly property indicates that the DatePicker value can only be read. You cannot edit the value in DatePicker and also the DatePicker calendar popup is not shown. By default, ReadOnly Boolean value is set to false.

In the ASPX page, include the following DatePicker control code example to enable the read only mode.



{% highlight html %}



<ej:DatePicker ID="datepicker" runat="server" ReadOnly="true"></ej:DatePicker>



{% endhighlight %}

## Show Footer

It allows to Show Footer in the DatePicker calendar to select today date. By default, ShowFooter property is set to true in the DatePicker control. You can hide footer in the DatePicker when this property is set to false.

In the ASPX page, include the following DatePicker control code example to hide the footer



{% highlight html %}



   <ej:DatePicker ID="datepicker" runat="server" ShowFooter="false"></ej:DatePicker>





{% endhighlight %}



![](Miscellaneous_images/Miscellaneous_img2.png) 



## Show popup button

It shows the date icon button at right side of the textbox and the DatePicker popup by clicking on it. This can be achieved by using the ShowPopupButton property. By default, ShowPopupButton property is set to true in the DatePicker control. 

In the ASPX page, include the following DatePicker control code example to hide the popup button.



{% highlight html %}

   <ej:DatePicker ID="datepicker" runat="server" ShowPopupButton="false"> </ej:DatePicker>



{% endhighlight %}



The following screenshot displays the output for the above code.



![](Miscellaneous_images/Miscellaneous_img3.png)



## Show rounded corner

DatePicker input is displayed in a rounded corner style, when this property is set to true. By default, ShowRoundedCorner property is set to false in the DatePicker control.

In the ASPX page, include the following DatePicker control code example to enable the rounded corner effect.



{% highlight html %}

<ej:DatePicker ID="datepicker" runat="server" ShowRoundedCorner="true"> </ej:DatePicker>

{% endhighlight %}



The following screenshot displays the output for the above code.

 ![](Miscellaneous_images/Miscellaneous_img4.png)



## Show ToolTip

DatePicker Tooltip is displayed while you hover the date. By default, ShowTooltip property is set to true in the DatePicker control.

In the ASPX page, include the following DatePicker control code example to show/hide the tooltip.

{% highlight html %}



<ej:DatePicker ID="datepicker" runat="server" ShowTooltip="true"></ej:DatePicker>





{% endhighlight %}

The following screenshot displays the output for the above code.



![](Miscellaneous_images/Miscellaneous_img5.png)



