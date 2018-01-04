---
layout: post
title: Embed the resources from assembly 
description: Embed the resources from assembly 
platform: aspnet
control: General
documentation: ug
---

# Embedded Resources

Until Volume 1, 2015 our scripts and themes are registered manually in application level to render our components. Now you can also embed the resources from assembly to reduce the work. Henceforth user can render EJ (Essential JavaScript) components by dragging the control from toolbox in the design time without any manual configuration.

## How it works?
The EJ resources and dependent scripts are encapsulated as embedded in our assembly and registered those resources in ASP Script Manager. Afterwards ASP Script Manager will take appropriate process to access the resources from assembly as usual once components gets loaded on that page.

For themes, necessary stylesheets will be added in the header section of current page dynamically to render the EJ components. To get the embed resources in your application, you should register an App Key in Web.Config file.

## Access Embedded Resources
When drag and drop the control from toolbox to web page at the design time, the following key settings will be configured in web.config file. Refer to the following code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="true" />
            <add key="EJResources" value="jsrender:true;jqueryeasing:true; themes:true;" />
      </appSettings>

{% endhighlight %}

N> The above key setting will be configured automatically when drag and drop the control in design page only, otherwise we should configure it manually in web.config file.

### LoadEJResourcesFromAssembly 
The key denotes that whether the resources are referred from assembly or not. If you do not want to load the resources from assembly, you can disable this key value. Refer to the following code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="false" />
      </appSettings>

{% endhighlight %}

### EJResources 
EJResources key is used to get external scripts and themes that you want to access from assembly. For example, if you do not want to load the themes from assembly then you can give false to themes in that key. Refer to the following code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="true" />
            <add key="EJResources" value="jsrender:true;jqueryeasing:true;themes:false;" />
      </appSettings>

{% endhighlight %}

N> 1. You should enable the ‘LoadEJResourcesFromAssembly’ key before configuring necessary scripts and themes in **EJResources** settings.
N> 2. The jQuery file is excluded from embedded resources list since while creating new project, jQuery script will be referred by default.

## What are the resources will embed from assembly?

By default, the following resources are shipped as embedded resources from assembly.

*     JsRender v1.0.0 Beta
*	jQuery Easing v1.3
*	Default Theme (Azure Flat)

And component related scripts will be embedded dynamically from assembly in your application.

N> The jquery.easing.js library already avails within ej.web.all.min.js file, therefore it is not necessary to externally refer it in your application if you have referred ej.web.all.min.js already. For version lower than 14.3.0.49, refer to the jQuery.easing.min.js along with the ej.web.all.min.js.

## CDN integration with Embedded Resources
You can get these embedded resources from CDN (Content Delivery Networks) also. To achieve this behavior you should enable the **EnableCdn** property in ASP script manager control. Refer to the following code snippet:

{% highlight aspx-cs %}

      <asp:scriptmanager id="ScriptManager1" runat="server" EnableCdn="true">
      </asp:scriptmanager>

{% endhighlight %}

You can embed the resources from assembly when CDN (Content Delivery Network) is unavailable. To achieve this behavior you should enable **EnableCdnFallback** property in script manager. Refer to the following code snippet:

{% highlight aspx-cs %}

      <asp:ScriptManager runat="server" EnableCdn="true" EnableCdnFallback="true">
      </asp:scriptmanager>

{% endhighlight %}

N> 1. EnableCdnFallback property is supported from 4.5 and above frameworks.
N> 2. EnableCdnFallback is not applicable for theme file.
N> 3. Both script and style resources can also be accessed through HTTPS (secure connection) from CDN.
