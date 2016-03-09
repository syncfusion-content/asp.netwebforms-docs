---
layout: post
title: Define value | ProgressBar | ASP.NET | Syncfusion
description: define value
platform: aspnet
control: ProgressBar
documentation: ug
---

# Define value

## Value

Sets the ProgressBar value. By default, value is set to 0 (number). You can set the value for ProgressBar by using Value property. The value should be in between min and max values (number) of the ProgressBar. By default, MinValue is 0 and MaxValue is 100.

The following steps explain how to set the value for the ProgressBar control.

Add the following code in the ASPX page in order to render the ProgressBar control.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Text="60" Value="60" MinValue="40" MaxValue="80" Height="20" Width="500" ></ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the Assigning value to ProgressBar.            
![](Define-value_images/Define-value_img1.png)

## Percentage

Sets the ProgressBar value in percentage. By default, percentage is set to 0 (number). You can set the ProgressBar value in percentage by using the Percentage property. The value should be in between min and max values (number) of the ProgressBar. By default, MinValue is 0 and MaxValue is 100.

The following steps explain how to set the value in percentage.

Add the following code example to the ASPX page to render the Progress bar control with Percentage.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Percentage="64" MinValue="40" MaxValue="80" Text="64 %" Height="20" Width="500"> </ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the Progress bar with Percentage.

![](Define-value_images/Define-value_img2.png) 



## Setting Range

It allows you to set the range to the ProgressBar control. The range of the ProgressBar can be set by using the minimum and maximum values. The Minimum value specifies the value where the progress bar shows the start of the process. The Maximum value specifies the value where the progress bar shows the completion of the process. You can set the range by using MinValue and MaxValues properties.

The following steps explain the configuration of the range for the ProgressBar control.

Add the following code example in the ASPX page to render Minimum and Maximum values.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Value="100" Text="100 %" MinValue="40" MaxValue="100" Height="20" Width="500" ></ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the Minimum and Maximum values. 

![](Define-value_images/Define-value_img3.png)

### Appearance and Styling

#### Adjusting ProgressBar size

ProgressBar control provides ability to change/adjust the bar size. The Height and Width property allows you to set the maximum height and maximum width for the ProgressBar. The value set to this property should be string type.

Add the following code example to the ASPX page.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Value="40" Text="40 %" Height="40" Width="400" ></ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the maximum height and maximum width.                         

![](Define-value_images/Define-value_img4.png)

## Custom text

Allows custom text like percentage or any other message in the ProgressBar. You can set the custom text that is displayed when the progress bar shows different levels of progress.

The following steps explain the configuration of the custom text in the ProgressBar control.

Add the following code example in the ASPX page.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server"  Text="loading" Value="40"  Height="20" Width="500" ></ej:ProgressBar>
{% endhighlight %}

The following screenshot displays the custom text.

![](Define-value_images/Define-value_img5.png) 

## Theme

ProgressBar control’s style and appearance can be controlled based on the CSS classes. In order to apply Theme to the ProgressBar control, refer to the files, ej.widgets.core.min.css and ej.theme.min.css. When the file ej.widgets.all.min.css is referred, it is not necessary to include the ej.widgets.core.min.css and ej.theme.min.css files in your project, as ej.widgets.all.min.css is the combination of these two files. 

By default, there are 13 themes supported by the ProgressBar control, 

* default-theme
* bootstrap
* flat-azure-dark
* fat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark

### CSS class


To apply custom styles to the ProgressBar control, specify the CssClass property. The specified CSS name is added to the root of the ProgressBar control.

Add the following code example to the corresponding ASPX page to render ProgressBar control with customized style.

{% highlight html %}
<ej:ProgressBar ID="progressbar" runat="server" Value="70" Text="70 %"   Height="20" Width="500" CssClass="custom" ></ej:ProgressBar>
{% endhighlight %}

{% highlight css %}
.custom .e-progress{

    background: gray;

}
{% endhighlight %}

The following screenshot displays the customized style.

![](Define-value_images/Define-value_img6.png) 
