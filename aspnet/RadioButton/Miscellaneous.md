---
layout: post
title: Miscellaneous | RadioButton | ASP.NET | Syncfusion
description: miscellaneous
platform: aspnet
control: RadioButton
documentation: ug
---

# Miscellaneous

## Radio Button ID

Radio Button ID is not shown in the user interface. Here ID denotes the ID attribute of the root element of RadioButton control. This ID value is unique. You can give ID through element and through the **ID property**. When you use two IDs for a single radio button at initialization, the element ID is considered.

Set ID for RadioButton control as follows.

{% highlight html %}
<%--set new id value as follows--%>

<ej:RadioButton Name="Gender" ID="RadBtn_Male" runat="server" Size="Small" Text="Male">

</ej:RadioButton>

<br />

<ej:RadioButton Name="Gender" ID="RadBtm_female" runat="server" Size="Small" Text="Female">

</ej:RadioButton>
{% endhighlight %}

### Radio Button Prefix id

Id prefix value is appended to id value. It is used to mention the prefix for the wrapper’s id attribute. When you assign a value for **IdPrefix property**, the older prefix id gets replaced by the new prefix id. 

Setting a new prefix id for RadioButton control is as follows.

{% highlight html %}
<%--set new idPrefix   value as follows--%>

<ej:RadioButton Name="Gender" ID="RadBtn_Male" IdPrefix="sync_" runat="server" Size="Small"

Text="Male">

</ej:RadioButton>

<br />

<ej:RadioButton Name="Gender" ID="RadBtm_female" IdPrefix="sync_" runat="server"

Size="Small" Text="Female">

</ej:RadioButton>
{% endhighlight %}

## Radio Button Name

The Name setting tells you where a RadioButton belongs. When you select one button, all other buttons in the same group are unselected. You can have only one group of RadioButtons on each page.

The Name attribute is also used to identify form data after it has been submitted to the server, or for reference of form data using JavaScript on the client’s side. Only form elements with a Name attribute have their values passed, when submitting a form.

### Radio Button Value

The Value setting defines what can be submitted when checked.

For Radio Buttons, the contents of the **value property** do not appear in the user interface. The Value property only has meaning when submitting a form. If a radio button is in the checked state when the form is submitted, the name of the Radio button is sent along with the value of the value property, if the radio button is not checked, no information is sent.

To identify, on the server side, which one was checked, give different values for radio buttons in the same group, 

Set name and value for each radio button control as follows.

{% highlight html %}
<%--set name and value for each radio button as follows--%>

<ej:RadioButton ID="RadBtn_Male" runat="server" Size="Small" Text="Male" Name="Gender"

Value="male">

</ej:RadioButton>

<br />

<ej:RadioButton ID="RadBtm_female" runat="server" Size="Small" Text="Female" Name="Gender"

Value="female">

</ej:RadioButton>
{% endhighlight %}

## Server Side Events

The following server side event is available in Radio Button control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Argument Details</th></tr>
<tr>
<td>
OnChange</td><td>
It is raise when RadioButton status has been changed whether checked to uncheck / unchecked to check.</td><td>
Event Argument contains parameters are .IsChecked – Status of RadioButton.e.EventType – Event Name.Arguments – Contain keys and values for IsChecked.</td></tr>
</table>
In the ASPX page, add the Checkbox control to configure RadioButton events.

{% highlight html %}
<%--Add serverside event for Radio Button control as follows--%>

<ej:RadioButton ID="RadBtn_Male" runat="server" Text="Male" Name="Gender" Value="male"

OnChange="RadBtn_Male_Change">

</ej:RadioButton>

<br />

<ej:RadioButton ID="RadBtm_female" runat="server" Text="Female" Name="Gender" Value="female">

</ej:RadioButton>
{% endhighlight %}

The code **RadBtn_Male_Change** defines the server side "onChange" event in code behind.

{% highlight c# %}

protected void RadBtn_Male_Change(object Sender, Syncfusion.JavaScript.Web.RadioButtonEventArgs e){

//e.IsChecked – Status of Radiobutton

//e.EventType – Event Name

//e.Arguments – Contain keys and values for IsChecked

}
{% endhighlight %}
