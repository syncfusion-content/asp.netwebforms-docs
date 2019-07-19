---
layout: post
title: Context-Menu | Diagram | ASP.NET Webform | Syncfusion
description: This section explains how to use the Diagram's Context Menu items and their important key features in ASP.NET Webform.
platform: aspnet
control: Diagram
documentation: ug
---

# Context Menu

In graphical user interface (GUI), a context menu is a type of menu that appears when you perform right-click operation. Nested level of context menu items can be created.
Diagram provides some built-in context menu items and allows to define custom menu items.

## Default Context Menu

The `EnableContextMenu` property helps you to enable/disable the context menu. Diagram provides some default context menu items to ease the execution of some frequently used commands.
The following code illustrates how to enable the default context menu items.

{% highlight aspx-cs %}
<%--Disables the context menu--%>
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%" EnableContextMenu="true" >
</ej:Diagram>
{% endhighlight %}


![enable the default context menu items](ContextMenu_images/contextmenu.png)

## Customize Context Menu

Apart from the default context menu items, you can define some additional context menu items. Those additional items have to be defined and added to `ContextMenu.Items`. Sub menu items for context menu can set using `ContextMenu.Items.SubItems`
The following code example illustrate how to add custom context menu items.

 
{% highlight aspx-cs %}
       <%--   Initializes Diagram--%>
        <ej:Diagram ID="Diagram" runat="server" Height="600px" Width="900px" EnableContextMenu="true">
            <ContextMenu ShowCustomMenuItemsOnly="true">
                <items>
                   <ej:ContextMenuItem Name="zoom" Text="Zoom">
                      <SubItems>
                           <ej:ContextMenuItem Name="zoomIn Text="ZoomIn"></ej:ContextMenuItem>
                           <ej:ContextMenuItem Name="zoomOut Text="ZoomOut"></ej:ContextMenuItem>
                      </SubItems>
                   </ej:ContextMenuItem>
                </items>
            </ContextMenu>
        </ej:Diagram>
{% endhighlight %}
 

When you want to display only your custom context menu items, you can set true to the `showCustomMenuItemsOnly` property.

Icons of context menu items can be customized by overriding the default context menu item style.
The following code example illustrates how to customize the icon of context menu items.

{% highlight css %}
#Zoom_image {
	background-image: url("zoom.png");
}

#ZoomIn_image {
	background-image: url("zoom-in.png");
}

#ZoomOut_image {
	background-image: url("zoom-out.png");
}
{% endhighlight %}

![customize the icon of context menu items](ContextMenu_images/Contextmenu_img2.png)

## Context Menu Events

You would be notified with events when you try to open the context menu items(`contextMenuBeforeOpen`) and when you click the menu items(`contextMenuClick`). The following code example illustrates how to define those events.

{% tabs %}
{% highlight aspx-cs %}
<%--Enables the context menu--%>
<ej:Diagram ClientIDMode="Static" ID="Diagram" runat="server" Height="600px" Width="100%"  
	EnableContextMenu="true" OnClientContextMenuBeforeOpen="contextMenuBeforeOpen"
	OnClientContextMenuClick="contextMenuClick">
</ej:Diagram>
{% endhighlight %}

{% highlight js %}
function contextMenuBeforeOpen(args) {
	//do your custom action here.
}

function contextMenuClick(args) {
	switch (args.text) {
		case "zoom":
			//do your custom action here.
		break;
	}
}
{% endhighlight %}
{% endtabs %}
