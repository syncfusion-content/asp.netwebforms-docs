---
layout: post
title: DatePicker Customization
description: DatePicker customization options such as dimension, highlighted dates, other months visibility, etc.
platform: aspnet
control: DatePicker
documentation: ug
---
# Customization

EJWEB DatePicker appearance can be customized using below listed properties. 

## Set Dimension 

By default EJWEB DatePicker has standard height and width (Height: "30px" and Width: "143px"). You can change this height and width by using [Height](http://help.syncfusion.com/js/api/ejdatepicker#members:height) and [Width](http://help.syncfusion.com/js/api/ejdatepicker#members:width) property respectively.

{% highlight html %}
   
    <ej:DatePicker ID="datepick" Height="50px" Width="300px" runat="server"></ej:DatePicker>

{% endhighlight %}

Since EJWEB DatePicker is a form control and you can make it as responsive by specifying its Width as "**100%**".

{% highlight html %}

    <ej:DatePicker ID="datepick" Width="100%" runat="server"></ej:DatePicker>

{% endhighlight %}

## Show Footer

You can show or hide the footer of EJWEB DatePicker calendar by using [ShowFooter](http://help.syncfusion.com/js/api/ejdatepicker#members:showfooter) property. 

{% highlight html %}

    <ej:DatePicker ID="datepick" ShowFooter="false" runat="server"></ej:DatePicker>

{% endhighlight %}

N>  Footer contains the today button to quickly navigate to the current date. By turning off it, you have to select current date by manually. 

## Show Popup Button

EJWEB DatePicker control, contains a button to open the DatePicker calendar. You can hide this DatePicker calendar button using [ShowPopupButton](http://help.syncfusion.com/js/api/ejdatepicker#members:showpopupbutton) value as false.

By hiding this button, you can open the DatePicker by focusing the input textbox element of EJWEB Datepicker control itself.

{% highlight html %}

    <ej:DatePicker ID="datepick" ShowPopupButton="false" runat="server"></ej:DatePicker>

{% endhighlight %}

## Show Other Months

You can show or hide the other month days from EJWEB DatePicker calendar by using [ShowOtherMonths](http://help.syncfusion.com/js/api/ejdatepicker#members:showothermonths) property.

{% highlight html %}

    <ej:DatePicker ID="datepick" ShowOtherMonths="false" runat="server"></ej:DatePicker>
       
{% endhighlight %}

## Highlight Special Date

EJWEB DatePicker allows you to highlight the special dates in DatePicker calendar by using [SpecialDates](http://help.syncfusion.com/js/api/ejdatepicker#members:specialdates) property. It receives the array of JSON data, in which the data should contain the date value, icon CSS class and tooltip as field values with any names.

{% highlight html %}

    <ej:DatePicker ID="datepick" runat="server">
             <ej:SpecialDate Date="specialdate" IconClass="customCss" Tooltip="toolTip" />
    </ej:DatePicker>


{% endhighlight %}

And you can map those above field names to EJWEB DatePicker by using [Fields](http://help.syncfusion.com/js/api/ejdatepicker#members:fields) property, which holds following members.

<table>
<tr>
<th>
Members</th><th>
Description</th></tr>
<tr>
<td>
Date<br/><br/></td><td>
It specifies the mapping field of special date<br/><br/></td></tr>
<tr>
<td>
IconClass<br/><br/></td><td>
It specifies the mapping field of icon CSS class.<br/><br/></td></tr>
<tr>
<td>
Tooltip<br/><br/></td><td>
It specifies the mapping field of tool tip text.<br/><br/></td></tr>
</table>

