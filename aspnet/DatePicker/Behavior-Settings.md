---
layout: post
title: Behavior Settings
description: Configure DatePicker Behavior settings
platform: aspnet
control: DatePicker
documentation: ug
---
# Behavior Settings

EJWEB DatePicker has some default behavior settings which helps you to perform more operation by built-in.

## Selected Date

EJWEB DatePicker value can be selected through picking date from DatePicker calendar or you can set it by using [Value](http://help.syncfusion.com/js/api/ejdatepicker#members:value) property.

Refer below code example to set selected date at initialization

{% highlight html %}
      
      <ej:DatePicker ID="datepicker1" Value="<%# DateTime.Now %>" runat="server"></ej:DatePicker>

{% endhighlight %}

In ASP.NET to bind all the data sources to their server controls, we can use Page.DataBind() in the code behind page. Please refer the below code example.

{% highlight javascript %}

    protected void Page_Load(object sender, EventArgs e)
       {
           Page.DataBind();
       }

{% endhighlight %}

EJWEB DatePicker allows only the valid date to be entered and it should be within the specified range. By default, strict mode is enabled in DatePicker, so it will restrict invalid date and resets to previous date if it is not valid. To know more about strict mode refer [Strict Mode](#strict-mode).

## Date Range

EJWEB DatePicker provides an option to restrict the user to pick the date from specified range of value. You can utilize this option by make use of [MinDate](http://help.syncfusion.com/js/api/ejdatepicker#members:mindate) and [MaxDate](http://help.syncfusion.com/js/api/ejdatepicker#members:maxdate) property.

**MinDate** - specifies the minimum date to be picked in DatePicker calendar by disabling below date of minDate.

**MaxDate** -  specifies the maximum date to be picked in DatePicker calendar by disabling above date of maxDate. 


{% highlight html %}
     
    <ej:DatePicker ID="daterange1" runat="server" MaxDate="06/11/2015" MinDate="06/03/2015"></ej:DatePicker>  

{% endhighlight %}


N> You can change the **MinDate** and **MaxDate** value dynamically like **Value** property

## Start and Depth Level

Start and depth represents the view of EJWEB DatePicker calendar. EJWEB DatePicker calendar has four different level of views, which are month, year, decade and century. It allows you to quick pick date from different months and years by navigating through different views. 

By default DatePicker starts with month view and can be navigate into year, decade and century. You can also change the start and depth level view by using [StartLevel](http://help.syncfusion.com/js/api/ejdatepicker#members:startlevel) and [DepthLevel](http://help.syncfusion.com/js/api/ejdatepicker#members:depthlevel) property. So that you can initiate DatePicker calendar to view at any level and control the navigation.

* "Month"   -  shows the days in month to pick.
* "Year"    -  shows the months in year to pick.
* "Decade"  -  shows the years in decade to pick.
* "Century" -  shows the decades in century to pick.

{% highlight html %}

    <ej:DatePicker ID="daterange1" runat="server" MaxDate="06/11/2015" MinDate="06/03/2015"></ej:DatePicker>

{% endhighlight %}

## Display Inline Mode

EJWEB DatePicker provides an option to act as calendar by setting the [DisplayInline](http://help.syncfusion.com/js/api/ejdatepicker#members:displayinline) property as true. In this mode the DatePicker calendar has been placed open state constantly to pick the date. 

Refer below code example to represent DatePicker as calendar. 

{% highlight html %}

    <ej:DatePicker ID="daterange1" runat="server" DisplayInline="true"></ej:DatePicker>

{% endhighlight %}


## Strict Mode

Strict mode in  EJWEB DatePicker allows you to enter valid or invalid date in input textbox of this component, but an error class will get added to exhibit if it is an invalid date. When you set [EnableStrictMode](http://help.syncfusion.com/js/api/ejdatepicker#members:enablestrictmode) to false, EJWEB DatePicker allows you to enter only the valid date or else it will resets with previous value. 

Also the valid date should be defined in specified range or else it resets to min or maximum date when the entered date is out of range

By default **EnableStrictMode** is true, so you can enter any value other than date too, but an **error** class (**.** **e** **-** **error**) will get added to wrapper to highlight the invalid date.

{% highlight html %}

    <ej:DatePicker ID="daterange1" runat="server" EnableStrictMode="true"></ej:DatePicker>

{% endhighlight %}


You can also override the **e-error** class to highlight when invalid date is entered.


{% highlight html %}

    <ej:DatePicker ID="daterange1" runat="server" EnableStrictMode="true"></ej:DatePicker>
		
{% endhighlight %}


{% highlight css %}

    <style>
        /* error class to highlight invalid date */

        .e-error .e-input {
            color: Red; /* highlights invalid date font color in input */
        }
    </style>

{% endhighlight %}
