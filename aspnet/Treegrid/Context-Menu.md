---
layout: post
title: Context Menu | TreeGrid | ASP.NET | Syncfusion
description: context menu
platform: aspnet
control: TreeGrid
documentation: ug
---

# Context Menu

Context menu in TreeGrid control is used to manipulate (add, edit and delete) the tree grid rows. In TreeGrid, context menu can be enabled with ContextMenuSettings API. The ContextMenuSettings property contains two inner properties ShowContextMenu and ContextMenuItems.

The ShowContextMenu property is used to enable or disable the context menu, default value for this property is false.

The ContextMenuItems property is used to add the menu items to context menu, this property renders ‘Add’ and ‘Delete’ by default when the menu items are not provided.

{% highlight html %}

<ej:TreeGrid ID="treegrid1" runat="server">

       // ...

       <EditSettings AllowEditing="true" EditMode="rowEditing" />

       <ContextMenuSettings ShowContextMenu="true" 

                            ContextMenuItems="add,edit,delete"/>

        // ...

</ej:TreeGrid>

{% endhighlight %}



The following screenshot displays the Context menu in TreeGrid control.

 ![](Context-Menu_images/Context-Menu_img1.png) 



## ContextMenu Customization

Context menu can be customized by adding a new custom menu item to it. In TreeGrid, context menu can be customized using ContextMenuOpen client side event. This event is triggered when the context menu is rendered with mouse right click action. The following properties are available in the event,

* headerText: Display text for menu item.
* iconPath: Image location for menu item.
* eventHandler: Client side event for menu item click.







{% highlight html %}

<ej:TreeGrid ID="treegrid1" runat="server" ContextMenuOpen="customMenu">

        // ...

       <ContextMenuSettings ShowContextMenu="true" />

        // ...

   </ej:TreeGrid>



<script type=”text/javascript”>

  function customMenu( args )

  {

    args.contextMenuItems.push(

    {

      headerText: "customMenu",

      iconPath: “url(…/images/customMenu.png)”,

      eventHandler: customMenuClick,

    }

    );

  }

  function customMenuClick( args )

  {

      // ...     

      // ...     

  }

</script>

{% endhighlight %}



The following screenshot displays the customization of Context menu in TreeGrid control.

![](Context-Menu_images/Context-Menu_img2.png) 









