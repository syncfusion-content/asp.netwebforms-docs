---
layout: post
title: State Maintenance | ProgressBar | ASP.NET | Syncfusion
description: state maintenance
platform: aspnet
control: ProgressBar
documentation: ug
---

# State Maintenance

Save the current model value to cookies for state maintenance. While refreshing the ProgressBar control, the page retains the 
model value applied from the browser cookies. By default, EnablePersistence property is set to false in the ProgressBar.

Add the following code example to the corresponding ASPX page to render ProgressBar control.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Value="70" Text="70 %"   Height="20" Width="500" EnablePersistence="true">

</ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the output for the above code.

![](State-Maintenance_images/State-Maintenance_img1.png)

