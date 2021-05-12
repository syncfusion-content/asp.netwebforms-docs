---
layout: post
title: About Essential Studio ASP.NET Licensing | Syncfusion
description: Learn here about Syncfusion Essential Studio ASP.NET license key, how to generate the license key, how to register the license key, and more details.
platform: aspnet
control: Essential Studio
documentation: ug
---

# License Key Registration

The generated license key is just a string that needs to be registered before any Syncfusion control is initiated. The following code is used to register the license.

{% tabs %}
{% highlight c# %}
Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
{% endhighlight %}
{% endtabs %}

N> Place the license key between double quotes.  Also, ensure that Syncfusion.Licensing.dll is referenced in your project where the license key is being registered.

### ASP.NET Web Forms

You can register the license key in Application_Start method of **Global.asax.cs/Global.asax**

{% tabs %}
{% highlight c# %}
void Application_Start(object sender, EventArgs e)
{
	//Register Syncfusion license
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY");
	
	// Code that runs on application startup
	RouteConfig.RegisterRoutes(RouteTable.Routes);
	BundleConfig.RegisterBundles(BundleTable.Bundles);
}
{% endhighlight %}

{% highlight vb %}
Sub Application_Start(ByVal sender As Object, ByVal e As EventArgs)
	'Syncfusion Licensing Register
	Syncfusion.Licensing.SyncfusionLicenseProvider.RegisterLicense("YOUR LICENSE KEY")
	'Code that runs on application startup
	AuthConfig.RegisterOpenAuth()
	RouteConfig.RegisterRoutes(RouteTable.Routes)
	System.Web.Http.GlobalConfiguration.Configuration.Routes.MapHttpRoute(name:="DefaultApi", routeTemplate:="api/{controller}/{action}/{id}", defaults:=New With {.id = System.Web.Http.RouteParameter.[Optional]
	   })
End Sub
{% endhighlight %}

{% endtabs %}