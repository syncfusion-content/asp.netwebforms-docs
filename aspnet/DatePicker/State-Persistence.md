---
layout: post
title: State-Persistence
description: state persistence 
platform: aspnet
control: DatePicker
documentation: ug
---

## State Persistence 

It Enables or Disables the state maintenance of the DatePicker. DatePicker control can store the model value in the browser cookies and every time after initial rendering, the control gets the model from the cookie only. By using enablePersistence property, you can store the model value in cookies. So, when any changes are made dynamically then those values are updated in cookie. On refreshing the page, the past state of the DatePicker control is rendered from cookies. By default, EnablePersistence property is set to false in the DatePicker.

In the ASPX page, include the following DatePicker control code example to enable the state persistence. 

{% highlight html %}

     <ej:DatePicker ID="datepicker" runat="server" EnablePersistence="true"> </ej:DatePicker>



{% endhighlight %}



