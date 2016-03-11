---
layout: post
title: Miscellaneous
description: Configure start day of week, step month, and enable/disable
platform: aspnet
control: DatePicker
documentation: ug
---
# Miscellaneous 

## Start Day

By default EJWEB DatePicker calendar starts with "Sunday" and ends with "Monday". You can redefine this start day by using [StartDay](http://help.syncfusion.com/js/api/ejdatepicker#members:startday) property.

Refer below code to start Wednesday as start day. 

{% highlight html %}

    <ej:DatePicker ID="datepick" StartDay="2" runat="server"></ej:DatePicker>

{% endhighlight %}

## Step Months

EJWEB DatePicker calendar allows you to quick navigate back and forth from one month to previous or next month by clicking the arrow button. By default its navigate one by one month. You can also navigate by skipping months in odd or even or any count by using [StepMonths](http://help.syncfusion.com/js/api/ejdatepicker#members:stepmonths) property. 

{% highlight html %}

    <ej:DatePicker ID="datepick" StepMonths="2" runat="server"></ej:DatePicker>

{% endhighlight %}

## Read Only

You can make EJWEB DatePicker as read only by setting [ReadOnly](http://help.syncfusion.com/js/api/ejdatepicker#members:readonly) property as true. It allows only to read the value and it can't be changed by interaction.

{% highlight html %}

    <ej:DatePicker ID="datepick" ReadOnly="true" runat="server"></ej:DatePicker>
   
{% endhighlight %}

## Enable or Disable

You can enable or disable the EJWEB DatePicker textbox by using [Enabled](http://help.syncfusion.com/js/api/ejdatepicker#members:enabled) property. In inline mode EJWEB DatePicker calendar also gets enabled or disabled. 

{% highlight html %}

    <ej:DatePicker ID="datepick" Enabled="false" runat="server"></ej:DatePicker>

{% endhighlight %}
