---
layout: post
title: Embed the resources from assembly 
description: Embed the resources from assembly 
platform: aspnet
control: General
documentation: ug
---


#Embedded Resources

Until Volume 1, 2015 we registered our scripts and themes manually in application level to render our components. Now you can also embed the resources from assembly to reduce the work. Hence forth user can render EJ (Essential JavaScript) components by dragging the control from toolbox in design time without any manual configuration. 

##How it works?
The EJ resources and dependent scripts are encapsulated as embedded in our assembly and registered those resources in ASP Script Manager. Afterwards ASP Script Manager will take appropriate process to access the resources from assembly as usual once components loaded on that page. 

For themes, necessary stylesheets will be added in header section of current page dynamically to render the EJ components.  To get the embed resources in your application, you should register an App Key in Web.Config file. 

##Access Embedded Resources
When drag and drop the control from toolbox to web page at design time, the following key settings will configure in web.config file. Please refer below code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="true" />
            <add key="EJResources" value="jsrender:true;jqueryeasing:true; themes:true;" />
      </appSettings>

{% endhighlight %}

N> The above key setting will configure automatically when drag and drop the control in design page only otherwise we should configure it manually in web.config file.

###LoadEJResourcesFromAssembly 
The key denotes that whether resources are referred from assembly or not. If you don’t want to load resources from assembly, you can disable this key value. Please refer below code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="false" />
      </appSettings>

{% endhighlight %}

###EJResources 
EJResources key used to get external scripts and themes that you want to access from assembly. For e.g. if you don’t want to load the themes from assembly then you can give false to themes in that key. Please refer below code snippet:

{% highlight xml %}

      <appSettings>
            <add key="LoadEJResourcesFromAssembly" value="true" />
            <add key="EJResources" value="jsrender:true;jqueryeasing:true;themes:false;" />
      </appSettings>

{% endhighlight %}

N> 1. You should enable the ‘LoadEJResourcesFromAssembly’ key before configure necessary scripts and themes in **EJResources** settings.
N> 2. The jQuery file is excluded from embedded resources list since while creating new project, jQuery script will be referred by default. 

##What are the resources will embed from assembly?

By default, the following resources shipped as embedded resources from assembly. 

*     JsRender v1.0.0 Beta
*	jQuery Easing v1.3
*	Default Theme (Azure Flat)

And component related scripts will embed dynamically from assembly in your application. 

##CDN integration with Embedded Resources
You can get these embedded resources from CDN (Content Delivery Networks) also. To achieve this behavior you should enable the **EnableCdn** property in ASP script manager control.  Please refer below code snippet:

{% highlight aspx-cs %}

      <asp:scriptmanager id="ScriptManager1" runat="server" EnableCdn="true">
      </asp:scriptmanager>

{% endhighlight %}

You can embed the resources from assembly when CDN (Content Delivery Network) is unavailable. To achieve this behavior you should enable **EnableCdnFallback** property in script manager. Please refer the below code snippet:

{% highlight aspx-cs %}

      <asp:ScriptManager runat="server" EnableCdn="true" EnableCdnFallback="true">
      </asp:scriptmanager>

{% endhighlight %}

N> 1. EnableCdnFallback property is supported from 4.5 and above frameworks.
N> 2. EnableCdnFallback is not applicable for theme file. 
N> 3. Both script and style resources can also be accessed through HTTPS (secure connection ) from CDN 
