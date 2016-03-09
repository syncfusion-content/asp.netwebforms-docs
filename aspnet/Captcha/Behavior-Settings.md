---
layout: post
title: Behavior Settings | Captcha | ASP.NET Webforms | Syncfusion
description: behavior settings 
platform: aspnet
control: Captcha
documentation: ug
---

# Behavior Settings 

## Regenerate Captcha

Captcha control supports regeneration of captcha image without full page refresh. You can achieve this by clicking the refresh button. By default, Captcha renders without refresh button. You can add the refresh button by setting the ShowRefreshButton property to true. 

The following code example is used to render the Captcha with Refresh support.

{% highlight html %}

 <ej:Captcha ID="captcha" ShowRefreshButton="true" Mapper="Refresh"  runat="server"></ej:Captcha>

{% endhighlight %}

Add the following Refresh mapper code example to the corresponding CS page.


{% highlight c# %}
	public static string Refresh(Dictionary<object, object> captchaModel)    {	        
		return Syncfusion.JavaScript.Web.Captcha.GetModel(captchaModel).ExecuteResult();    
	}
{% endhighlight %}


The following screenshot illustrates the Captcha with Refresh button. 

![C:/Users/ApoorvahR/Desktop/3.png](Behavior-Settings_images/Behavior-Settings_img1.png)



## Audio Accessibility

Sometimes, Captcha characters are too hard to identify. In this case, Captcha with audio helps understand the Captcha character.  Captcha supports captcha with audio. You can achieve this by enabling the ShowAudioButton property to true. When this property is set to true, captcha renders with audio button and when you click the audio button, it readouts the captcha characters. By default, Captcha renders without audio button.

In the ASPX page, include the following Captcha control code example to render Audio.

{% highlight html %}

  <ej:Captcha ID="captcha" ShowAudioButton="true"  runat="server"></ej:Captcha>

{% endhighlight %}



The following screenshot illustrates the Captcha with audio button. 

![C:/Users/ApoorvahR/Desktop/3.png](Behavior-Settings_images/Behavior-Settings_img2.png)



