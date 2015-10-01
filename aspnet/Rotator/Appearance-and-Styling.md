---
layout: post
title: Appearance and Styling | Rotator | ASP.NET Webforms | Syncfusion
description: appearance and styling
platform: aspnet
control: Rotator
documentation: ug
---

# Appearance and Styling

## Adjusting rotator item size

### Slide width

This property sets the width of a Rotator Item. The value set to this property is string or number.

In an ASPX page, add the following code example and set the SlideWidth property as required.

{% highlight html %}

//Refers to the Local Data section for style and data bound for rotator items.

<ej:Rotator ID="slidercontent" runat="server" SlideWidth="600px" DataCaptionField="Caption" DataUrlField="Url"></ej:Rotator>

{% endhighlight %}

### Slide height

This property sets the height of a Rotator Item. The value set to this property is string or number.

In an ASPX page, add the following code example and set the SlideHeight property as required.

{% highlight html %}

//Refer Local Data section for style and data bound for rotator items

<ej:Rotator ID="slidercontent" runat="server" SlideHeight="350px" DataCaptionField="Caption" DataUrlField="Url"></ej:Rotator>

{% endhighlight %}