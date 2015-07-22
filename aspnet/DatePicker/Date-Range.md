---
layout: post
title: Date-Range
description: date range
platform: aspnet
control: DatePicker
documentation: ug
---

# Date Range

Date Range from minimum to maximum values are set for the DatePicker control by using MinDate and MaxDate properties respectively. This allows you to restrict the date selection between the MinDate and MaxDate. This disables the dates beneath the MinDate and dates above the MaxDate.

In the ASPX page, include the following DatePicker control code example to specify the range.

{% highlight html %}



 <ej:DatePicker ID="datepicker" runat="server"  MinDate="2014/06/03" MaxDate="2014/06/19"></ej:DatePicker>   





{% endhighlight %}



The following screenshot displays the output for the above code.

![](Date-Range_images/Date-Range_img1.png) 
{:.image }


