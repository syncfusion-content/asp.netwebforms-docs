---
layout: post
title: miscellaneous 
description: miscellaneous 
platform: aspnet
control: DateRangePicker
documentation: ug
keywords: enable, disable, editing
---

## Miscellaneous 

### Enable / Disable

The control can be enabled / disabled using public methods, **enable** or **disable**. 

{% highlight html %}

     <ej:DateRangePicker ID="dateRange" runat="server"></ej:DateRangePicker>
       

{% endhighlight %}


{% highlight js %}

   // Disable the dateRangePicker.

        $('#<%=dateRange.ClientID%>').ejDateRangePicker('disable');


   // Enable the dateRangePicker.

       $('#<%=dateRange.ClientID%>').ejDateRangePicker('enable');


{% endhighlight %}


### Allow Editing

Editing in input box can be disabled by setting the false value to **AllowEdit** API. By default this will be false and we can edit the value in input box

{% highlight html %}

    <ej:DateRangePicker ID="dateRange" runat="server" AllowEdit="false"></ej:DateRangePicker>
        
{% endhighlight %}


### Clear ranges

To clear the all selection and ranges in a popup we can make use of **clearRanges** method.

{% highlight html %}

    <ej:DateRangePicker ID="dateRange" runat="server"></ej:DateRangePicker>

  {% endhighlight %}


{% highlight js %}

   $('#<%=dateRange.ClientID%>').ejDateRangePicker('clearRanges');

{% endhighlight %}