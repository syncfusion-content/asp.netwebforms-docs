---
layout: post
title: getting started
description: getting started
platform: aspnet
control: DateRangePicker
documentation: ug
keywords: getting-started
---

# Getting Started

## New HTML Document and required codes:

To get start with The EJWEB DateRangePicker, create a new web application and add the required assemblies in references and then refer the below specified dependent CSS file as well as scripts

To create a web application and to add necessary assemblies you can use the help of the given [ASP-Getting Started](https://help.syncfusion.com/aspnet/getting-started) documentation.

CSS file

* [ej.web.all.min.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css) - includes all widgets styles (To know more about theme refer [Theming in Essential JavaScript Component](http://help.syncfusion.com/js/theming-in-essential-javascript-components#))

External script files

* [jQuery](http://jquery.com/#) (from the version 1.7.1 to 3.1.0)

N> From V13.4.0.53 onwards, jQuery.globalize.min.js file has been replaced with our script file ej.globalize.min.js to support the globalization for our widgets. For version lower than 13.4.0.53, refer jQuery.globalize.min.js. jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

Internal script files

<table>
<tr>
<td>
File </td><td>
Description / Usage</td></tr>
<tr>
<td>
ej.core.min.js<br></td><td>
Includes only the widget basic functions and Framework features. Must be referred always before using all the JS controls<br></td></tr>
<tr>
<td>
ej.scroller.min.js</td><td>
To enable the scroll bar with preset ranges if count exceeded</td></tr>
<tr>
<td>
ej.globalize.min.js<br></td><td>
To support the globalization.<br></td></tr>
<tr>
<td>
ej.datepicker.min.js<br></td><td>
DatePicker plugin.</td></tr>
<tr>
<td>
ej.timepicker.min.js</td><td>
TimePicker plugin</td></tr>
<tr>
<td>
ej.daterangepicker.min.js</td><td>
DateRangePicker Plugin</td></tr>
</table>

You can make use of **ej.web.all.min.js** file which encapsulates all EJWEB components and frameworks in single file.

* [ej.web.all.min.js](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js) - includes all web widgets.

N>  In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets#) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en#text-compression-with-gzip) in your server. 


## DateRangePicker Initialization

You can add the following code example to the corresponding ASPX page to render the DateRangePicker.

{% highlight html %}

 <ej:DateRangePicker ID="dateRange" runat="server"></ej:DateRangePicker>

{% endhighlight %}


## Get/Set Value

DateRangePicker provides an options to configure all its properties and to get its value. DateRangePicker value can be assigned during initialization or at run time. Below code shows how to assign the values at initialization.

{% highlight html %}
    // initialize DateRangePicker component with Value API

     <ej:DateRangePicker ID="dateRange" runat="server" Width="100%" Value="11/1/2013 - 12/3/2019"></ej:DateRangePicker>

{% endhighlight %}


You can assign values after initialization in DateRangePicker (‘it helps to get or set value at run time). Let’s consider that going to set date range at button click.


{% highlight html %}


//bind below onClick action to button

        function onClick() {

            //create instance for dateRangePicker.

            // create instance only after control creation, to get dateRangeObj otherwise it throws exception.

            var dateRangeObj = $('#<%=dateRange.ClientID%>').ejDateRangePicker('instance');

                //set value using date range picker object

                dateRangeObj.option('value', "11/1/2013 - 12/3/2019");

                //get value using date range object and displays in alert box

                alert(dateRangeObj.option('value'));

            }

{% endhighlight %}



