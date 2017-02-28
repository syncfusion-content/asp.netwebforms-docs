---
layout: post
title: Miscellaneous | Toggle Button | ASP.NET | Syncfusion
description: miscellaneous
platform: aspnet
control: ToggleButton
documentation: ug
---

# Miscellaneous

## Show Rounded Corner 

It sets the corner of the Toggle Button in rounded shape. The Toggle Button, by default, does not have rounded corners. To set rounded corners, you can enable the **ShowRoundedCorner property**.

In the ASPX page, add the following button elements to configure the Toggle Button.

{% highlight html %}

<ej:ToggleButton ID="ToggleButton_RoundedCorner" runat="server" Size="Small" ShowRoundedCorner="true" DefaultText="Play" ActiveText="Pause" ContentType="TextAndImage" DefaultPrefixIcon="e-icon e-mediaplay" ActivePrefixIcon="e-icon e-mediapause">

</ej:ToggleButton>

{% endhighlight %}



Run the above code to render the following output.

![](Miscellaneous_images/Miscellaneous_img1.png) 



## Prevent Toggle

This property is used to prevent the state change of the Toggle Button when it is clicked. When you set the **PreventToggle property** to true, the state of the Toggle Button is not changed even though it is clicked.

In the ASPX page, add the following button elements to configure the Toggle Button.

{% highlight html %}

<ej:ToggleButton ID="ToggleButton_Prevent" runat="server" Size="Small" DefaultText="Play" ActiveText="Pause" ContentType="TextAndImage" DefaultPrefixIcon="e-icon e-mediaplay" ActivePrefixIcon="e-icon e-mediapause" PreventToggle="true">

</ej:ToggleButton>

{% endhighlight %}



Run the above code to render the following output.

![](Miscellaneous_images/Miscellaneous_img2.png) 



