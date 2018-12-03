---
layout: post
title: Syncfusion DatePicker How-to
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

{% highlight html %}

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

## How to add clear button with DatePicker?

Clear button can be included in the DatePicker control. In the `create` event of DatePicker, clear button element should be appended in the input element and event for clearing the value should bind with the clear button element. Refer the sample from the link [Clear button](http://jsplayground.syncfusion.com/mmdn4d0q) to know how to add the clear button with the DatePicker component.

{% highlight html %}

    <ej:DatePicker ClientSideOnCreate="onCreate" runat="server"></ej:DatePicker>

    <script>
        function onCreate() {
            if (this.innerWrapper.find('.e-clear-date').length == 0) {
                this.innerWrapper.append("<span class='e-clear-date e-icon'></span>"); // create and append the 'div' element to the calendar
                this._on($('.e-clear-date', this.innerWrapper), "click", function () { this.option('value', null); if (!this.model.displayInline) this.hide(); }); // bind the 'Click' event to that 'div' element
            }
        }
    </script>

    <style>
        .e-clear-date {
            text-align: center;
            position: absolute;
            right: 24px;
            top: 0;
            background: #ececec;
            width: 21px !important;
            height: 100% !important;
            margin-top: -14px !important;
        }

        .e-clear-date:hover {
            background: #86cbea;
            cursor: pointer;
        }

        .e-clear-date:before {
            content: "\e605";
            font-size: 16px;
            line-height: 1.8;
        }
    </style>

{% endhighlight %}

## How to integrate with bootstrap grid system? 

EJWEB DatePicker is responsive control, you have to just set the Width as 100% to DatePicker. In Bootstrap grid layout use the below code example to get responsive DatePicker Control. 

{% highlight html %}

    <ej:DatePicker ID="datepick" Height="100%" Width="100%" runat="server"></ej:DatePicker>

{% endhighlight %}

