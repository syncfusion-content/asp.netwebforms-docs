---
layout: post
title: State Persistence
description: DatePicker - State persistence properties 
platform: aspnet
control: DatePicker
documentation: ug
---
# State Persistence

You can sustain the entire widget model of EJWEB DatePicker even after form post or browser refresh by using [EnablePersistence](http://help.syncfusion.com/js/api/ejdatepicker#members:enablepersistence) property. So the entire model values such as 

* Selected date
* Highlighted date
* Start and depth level 

are stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.


{% highlight html %}

    <ej:DatePicker ID="datepick" EnablePersistence="true" runat="server"></ej:DatePicker>

{% endhighlight %}
