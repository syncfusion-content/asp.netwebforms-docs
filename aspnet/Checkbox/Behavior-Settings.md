---
layout: post
title: Behavior Settings | Chart | ASP.NET Webforms | Syncfusion
description: behavior settings
platform: aspnet
control: Checkbox
documentation: ug
---

# Behavior Settings

## Checkbox ID

Checkbox ID is not displayed in user interface. Here, ID mentions the id attribute of the root element of the Checkbox control. When you assign a value for ID property, then this older ID is replaced by new ID. This ID value should be unique. 

Set ID for Checkbox control as follows.

{% highlight html %}

<%--sets ID for Checkbox--%>

<ej:CheckBox ID="Checkbox" runat="server" Text="Fresher"></ej:CheckBox>



{% endhighlight %}

## Checkbox Id Prefix

Id prefix value is the one that is appended to id value. It is used to mention the prefix for the wrapper’s id attribute. When you assign a value for IdPrefix property, the older prefix id is replaced by new prefix id. 

Set prefix id for Checkbox control as follows.

{% highlight html %}

<%--Sets prefix id for Checkbox--%>

<ej:CheckBox ID="Checkbox" IdPrefix="Sync_" runat="server" Text="Fresher"> </ej:CheckBox>



{% endhighlight %}

## Checkbox Name

The name attribute is used to identify form data after it has been submitted to the server, or to reference form data by using JavaScript on the client side. Checkbox also contains name attribute. This name should be unique.

## Checkbox Value

For Checkboxes, the contents of the value property do not appear in the user interface. The value property contains only a meaning when submitting a form. When a Checkbox is in checked state and when the form is submitted, the name of the Checkbox is sent along with the value of the value property (When the checkbox is not checked, no information is sent).

You can set name and value for the Checkbox control as follows.

{% highlight html %}

<%--Sets name and value for Checkbox--%>

<ej:CheckBox ID="Checkbox" runat="server" Text="Milk" Name="food" Value="milk"></ej:CheckBox>



{% endhighlight %}



