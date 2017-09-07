---
layout: post
title: Getting started with DatePicker
description: Get start with DatePicker by adding references,required script and files.
platform: aspnet
control: DatePicker
documentation: ug
---
# Getting Started

## A new web application with required files and assemblies

To get start with The EJWEB DatePicker, create a new web application and add the required assemblies in references and then refer the below specified dependent CSS file as well as scripts

To create a web application and to add necessary assemblies you can use the help of the given [ASP-Getting Started](https://help.syncfusion.com/aspnet/getting-started) documentation.

CSS file

* [ej.web.all.min.css](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/flat-azure/ej.web.all.min.css) - includes all widgets styles (To know more about theme refer [Theming in Essential JavaScript Component](http://help.syncfusion.com/js/theming-in-essential-javascript-components#))

External script files

* [jQuery](http://jquery.com/#) (from the version 1.7.1 to 3.1.0)

N> From V13.4.0.53 onwards, jQuery.globalize.min.js file has been replaced with our script file ej.globalize.min.js to support the globalization for our widgets. For version lower than 13.4.0.53, refer jQuery.globalize.min.js. jQuery.easing external dependency has been removed from version 14.3.0.49 onwards. Kindly include this jQuery.easing dependency for versions lesser than 14.3.0.49 in order to support animation effects.

Internal script files

<table>
<tr>
<th>
File </th><th>
Description / Usage </th></tr>
<tr>
<td>
ej.core.min.js<br/><br/></td><td>
Includes only the widget basic functions and Framework features. Must be referred always before using all the JS controls<br/><br/></td></tr>
<tr>
<td>
ej.globalize.min.js<br/><br/></td><td>
To support the globalization.<br/><br/></td></tr>
<tr>
<td>
ej.datepicker.min.js<br/><br/></td><td>
DatePicker plugin.<br/><br/></td></tr>
</table>

N> From V13.4.0.53 onwards, jQuery.globalize.min.js file has been replaced with our script file ej.globalize.min.js to support the globalization for our widgets. For version lower than 13.4.0.53, refer jQuery.globalize.min.js.

You can make use of **ej.web.all.min.js** file which encapsulates all EJWEB components and frameworks in single file.

* [ej.web.all.min.js](http://cdn.syncfusion.com/{{ site.releaseversion }}/js/web/ej.web.all.min.js) - includes all web widgets.

N>  In production, we highly recommend you to use our [custom script generator](http://helpjs.syncfusion.com/js/include-only-the-needed-widgets#) to create custom script file with required controls and its dependencies only. Also to reduce the file size further please use [GZip compression](https://developers.google.com/web/fundamentals/performance/optimizing-content-efficiency/optimize-encoding-and-transfer?hl=en#text-compression-with-gzip) in your server. 

Below is a simple site master page with required CSS and script references added to create EJWEB DatePicker in ASP.NET WEB application

{% highlight html %}

    <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>@ViewBag.Title - My ASP.NET Application</title>
       
    <link rel="stylesheet" href="http://cdn.syncfusion.com/13.4.0.63/js/web/flat-azure/ej.web.all.min.css" />
    <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
    <script src="http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js"> </script>
    <script src="http://cdn.syncfusion.com/13.4.0.63/js/web/ej.web.all.min.js"> </script>
    <script src="http://cdn.syncfusion.com/13.4.0.63/js/common/ej.unobtrusive.min.js"></script>

    </head>
     
{% endhighlight %}

## DatePicker Initialization

EJWEB DatePicker can be created using aspx code like as below code

{% highlight html %}

    <%--initialize DatePicker component--%>

    <ej:DatePicker runat="server" ID="datePicker"></ej:DatePicker>

{% endhighlight %}


N>  DatePicker is a form control, so on form submitting its value can be retrieved by its **name**. By default **id** has been treated as name, if "name" attribute is not specified.

## Get / Set value

EJWEB DatePicker provides an options to configure all its properties and get its value. This DatePicker value can be assigned during initialization or at some action.
Below code shows how to assign values at initialization

{% highlight html %}

    <%--initialize DatePicker component with current date--%>

    <ej:DatePicker runat="server" ID="datePicker" Value="<%# DateTime.Now %>">
    </ej:DatePicker>

{% endhighlight %}

You can assign values after initialization of EJWEB DatePicker (it helps to get or set value at run time). Let's consider that going to set date value at button click.

{% highlight js %}

        <script>

        //bind below onClick action to button
        function onClick() {

            //create instance for datePicker.
            // only after control creation we can get dateObj otherwise it throws exception.
            var dateObj = $("#datePicker").ejDatePicker('instance');

            //set value using date object
            dateObj.option('value', new Date());

            //get value using date object and displays in alert box
            alert(dateObj.option('value'));
        }
  
    </script>


{% endhighlight %}

In ASP.NET to bind all the data sources to their server controls, we can use Page.DataBind() in the code behind page. Please refer the below code example.

{% highlight javascript %}

    protected void Page_Load(object sender, EventArgs e)
        {
            Page.DataBind();
        }

{% endhighlight %}

N>  Existing EJWEB DatePicker instance can be created by [jQuery.data()](http://api.jquery.com/jQuery.data/#) and you can control the API's of DatePicker behavior.

## DatePicker events

You can handle the all available [Client side events](http://help.syncfusion.com/js/api/ejdatepicker#events) in Essential JavaScript DatePicker. Refer the below code example to use the client side event in EJWEB DatePicker


{% highlight html %}
 
    <ej:DatePicker ID="datepicker1" ClientSideOnChange="onChange" Value="<%# DateTime.Now %>" runat="server"></ej:DatePicker>

    <script type="text/javascript">
    function onChange(args) {
        //args contains entire model of DatePicker to get the value of all properties.

        //alert popup shows the previous date and selected date.
        alert(" previous date is : " + args.prevDate + " \n selected date is : " + args.value);
    }     

{% endhighlight %}

In Code Behind page,

{% highlight javascript %}

    protected void Page_Load(object sender, EventArgs e)
        {
            Page.DataBind();
        }

{% endhighlight %}

Also, EJWEB DatePicker components have support with server side events please refer the [Server Side Events](http://help.syncfusion.com/aspnet/datepicker/server-side-events) section to know about available server side events in this component.