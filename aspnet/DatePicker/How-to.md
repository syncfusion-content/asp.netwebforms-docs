---
layout: post
title: How-to
description: How-to section
platform: js
control: DatePicker
documentation: ug
---
# How to?

## Customizing template with range selection between two DatePicker. 

You can customize the date field to emphasize the particular dates in EJWEB DatePicker calendar with help of [SpecialDates](http://help.syncfusion.com/js/api/ejdatepicker#members:specialdates) and set the date range using [MinDate](http://help.syncfusion.com/js/api/ejdatepicker#members:mindate) and [MaxDate](http://help.syncfusion.com/js/api/ejdatepicker#members:maxdate) property. Refer the sample from the link [DateRange](http://asp.syncfusion.com/demos/web/datepicker/date-range.aspx) to know how to customize date with date range.

## Disable specific dates to restrict user

EJWEB DatePicker allows you to restrict date selection in specific range by using date range option. But you can also restrict selective date in DatePicker calendar by utilizing [BeforeDateCreate](http://help.syncfusion.com/js/api/ejdatepicker#events:beforedatecreate) event. This event will get triggered at each date creation. So you can disable the selective date in this event to restrict the user.

{% highlight aspx %}

       <ej:DatePicker ID="datepick" ClientSideOnBeforeDateCreate="beforeCreate" runat="server"></ej:DatePicker>

    <script>   

        //event get triggered for each date create.
        function beforeCreate(args) {
            //date to disable in calendar to restrict selection.
            var disableDate = new Date("09/22/2015"); 
            //compares two and adds the disable class.
            if (+args.date === +disableDate)                
                args.element.addClass('e-disable');  
                // args contains current date and its element.          
        }
         
    </script>



{% endhighlight %}

## How to integrate with bootstrap grid system? 

EJWEB DatePicker is responsive control, you have to just set the Width as 100% to DatePicker. In Bootstrap grid layout use the below code example to get responsive DatePicker Control. 

{% highlight aspx %}

    <ej:DatePicker ID="datepick" Height="100%" Width="100%" runat="server"></ej:DatePicker>

{% endhighlight %}

