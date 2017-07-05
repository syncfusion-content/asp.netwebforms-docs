---
layout: post
title: state persistence
description: state persistence
platform: aspnet
control: DateRangePicker
documentation: ug 
keywords: state-persistence
---

## State Persistence

The value of DateRangePicker can be sustained even after form post back and page refreshing by enabling the **EnablePersistence** API like below code example.

{% highlight html %}

  <ej:DateRangePicker ID="dateRange" runat="server" EnablePersistence="true"></ej:DateRangePicker>
  
{% endhighlight %}

The DateRangePicker Model value will be stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.

