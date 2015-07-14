---
layout: post
title: Context-Menu
description: context menu
platform: aspnet
control: Gantt
documentation: ug
---

## Context Menu

Default Context Menu

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



{ ![http://help.syncfusion.com/ug/js/ImagesExt/image72_8.png](Context-Menu_images/Context-Menu_img1.png) | markdownify }
{:.image }


Custom Context Menu

You can add custom context menu option in Gantt control. The following code example shows you how to add the custom context menu option in Gantt control.







{% highlight html %}



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



<ej:Gantt ID="GanttContainer" runat="server" EnableContextMenu="true" ContextMenuOpen="contextMenuOpen">



{% endhighlight %}



The screenshot of the Custom Context Menu items in Gantt control is as follows.



{ ![C:/Users/Rajasekar/Desktop/IMG_17062014_121224.png](Context-Menu_images/Context-Menu_img2.png) | markdownify }
{:.image }


