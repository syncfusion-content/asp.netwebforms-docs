---
layout: post
title: customization
description: customization
platform: aspnet
control: DateRangePicker
documentation: ug
keywords: dimension, corners
---

## Customization

With available flexible options customization of DateRangePicker will be easier.

### Setting Dimension

**Height** and **width** of the DateRangePicker can be changed using corresponding API (**Height,Width**) like below code examples.

{% highlight html %}

  <ej:DateRangePicker ID="dateRange" runat="server" Height="50" Width="300"></ej:DateRangePicker>
        
{% endhighlight %}

        
### Rounded Corners

You can make use of **ShowRoundedCorner** property in order to add rounded borders to the input and popup elements. By default, in DateRangePicker this will be disabled state we can enable this by setting true to this API.

// creates DateRangePicker and setting rounded corner dynamically


{% highlight html %}

<ej:DateRangePicker ID="dateRange" runat="server" ShowRoundedCorner="true"></ej:DateRangePicker>

{% endhighlight %}



