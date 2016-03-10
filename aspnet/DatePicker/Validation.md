---
layout: post
title: Validation
description: Validate the date using JQuery
platform: aspnet
control: DatePicker
documentation: ug
---
# Validation

EJWEB DatePicker provides very cool way to validate the value by custom rules and messages before its get processing. Enhanced APIs and built-in validation support in EJWEB DatePicker provides the quick validation in client side itself which provides the easy customization and better user experience than the validating the values in  server side. Most common client side validation plugin is [JQuery Validation](http://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js). 

Since, EJWEB DatePicker supports this validation by built-in, you can do client validation with simple steps to validate and respond validation message. The jQuery validate plugin rules and custom methods can be used in the DatePicker control with the help of two properties,[ValidationRules](http://help.syncfusion.com/js/api/ejdatepicker#members:validationrules) and [ValidationMessage](http://help.syncfusion.com/js/api/ejdatepicker#members:validationmessage). 

Before using those properties, you need to add the jQuery validate plugin to your html page.

Refer the below jQuery validation plugin script after jQuery script reference.

{% highlight aspx %}

     <script src="http://ajax.aspnetcdn.com/ajax/jquery.validate/1.14.0/jquery.validate.min.js"></script>

{% endhighlight %}


{% highlight aspx %}

    <ej:DatePicker ID="datepick" Locale="de-DE" runat="server">
                <ValidationRule> 
                    <ej:KeyValue Key="required" Value="true" />
                </ValidationRule>
                <ValidationMessage>
                    <ej:KeyValue Key="required" Value="Please enter the date value" />
                </ValidationMessage>
    </ej:DatePicker>


{% endhighlight %}


N>  jQuery validation works only within the form element.
