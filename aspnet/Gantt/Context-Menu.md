---
layout: post
title: Context Menu in ASP.NET Webforms Gantt | Syncfusion
description: Learn here about context menu support in Syncfusion Essential ASP.NET Webforms Gantt Control, its elements, and more.
platform: aspnet
control: Gantt
documentation: ug
---

# Context Menu in ASP.NET Webforms Gantt

## Default Context Menu

The default context menu contains the following options.

* Task Details
* Add New Task
* Indent
* Outdent
* Delete

The following code example shows you how to enable the default context menu in Gantt control.







{% highlight html %}



<ej:Gantt ID="GanttContainer" runat="server" EnableContextMenu="true">



{% endhighlight %}



The following screenshot shows the Default Context Menu in Gantt control.



![Default Context Menu in ASP.NET Webforms Gantt](Context-Menu_images/Context-Menu_img1.png)

Default Context Menu
{:.caption}

## Custom Context Menu

You can add custom context menu option in Gantt control. The following code example shows you how to add the custom context menu option in Gantt control.


{% tabs %}

{% highlight js %}



<script type="text/javascript">

            function contextMenuOpen(args) {

                args.contextMenuItems.push(

                    {

                        headerText: "ExpandAll",

                        iconPath: "url(../images/Expand All.png)",

                        evenHandler: function () {

                            //event handler for custom menu items

                        }

                    });

            }

          </script>

{% endhighlight %}
{% highlight html %}

<ej:Gantt ID="GanttContainer" runat="server" EnableContextMenu="true" ContextMenuOpen="contextMenuOpen">



{% endhighlight %}

{% endtabs %}

The screenshot of the Custom Context Menu items in Gantt control is as follows.



![Custom Context Menu in ASP.NET Webforms Gantt](Context-Menu_images/Context-Menu_img2.png)


Custom Context Menu
{:.caption}
