---
layout: post
title: Getting Started | GroupButton | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: GroupButton
documentation: ug
---

# Getting Started

This section provides details on how to create and customize **Groupbutton** control in an ASP.NET WebForms application.

## Create a simple GroupButton control

Create ASP.NET WebForms project and add necessary assemblies and script dependencies with the help of given [Getting started document](https://help.syncfusion.com/aspnet/getting-started).

Add the below code the aspx page to render a simple groupbutton control.

{% highlight html %}

<ej:GroupButton ID="grp_btn" runat="server"  Size="Large">

<Items>

<ej:GroupButtonItem Text="Save"></ej:GroupButtonItem>

<ej:GroupButtonItem Text="Open"></ej:GroupButtonItem>

<ej:GroupButtonItem Text="Delete"></ej:GroupButtonItem>

</Items>

</ej:GroupButton>

{% endhighlight %}

Run the project to get the following output

![](Getting-Started_images/grpbtn.png)

