---
layout: post
title: State Maintenance | ProgressBar | ASP.NET | Syncfusion
description: Learn here about state maintenance in Syncfusion Essential ASP.NET WebForms ProgressBar Control, its elements, and more.
platform: aspnet
control: ProgressBar
documentation: ug
---

# State Maintenance in ASP.NET WebForms ProgressBar

Save the current model value to cookies for state maintenance. While refreshing the ProgressBar control, the page retains the 
model value applied from the browser cookies. By default, EnablePersistence property is set to false in the ProgressBar.

Add the following code example to the corresponding ASPX page to render ProgressBar control.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Value="70" Text="70 %"   Height="20" Width="500" EnablePersistence="true">

</ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the output for the above code.

![ASP.NET WebForms ProgressBar state maintenance](State-Maintenance_images/State-Maintenance_img1.png)

