---
layout: post
title: TargetId | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: targetid
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# TargetId

This property is used to define the target Id for Navigation Drawer. The drawer opens while you click on the specified target element.

{% highlight html %}

       <div class="cols-sample-area" style="padding: 0px; position:relative;  margin: 0px; min-height: 451px; width: 100%;">
              <button id="drawerTarget" style="top:200px;left:50%;position:absolute">Target Button</button>

        <ej:NavigationDrawer runat="server"  ID="navpane"  EnableListView="true" TargetId="drawerTarget" >
                        <ListViewSettings Width="300" SelectedItemIndex="0" />
                        <Items>
                            <ej:NavigationDrawerItems  Text="Home"  />
                            <ej:NavigationDrawerItems  Text="Profile" />
                            <ej:NavigationDrawerItems  Text="Photos" />
                            <ej:NavigationDrawerItems  Text="Location" />
                        </Items>
                    </ej:NavigationDrawer>
                </div>

{% endhighlight %}

Add following code in style section,

{% highlight css %}

    <style type="text/css">
       
       .e-header {
            padding-top: 8px;
        }

        #container p {
            padding: 10px;
            text-align: justify;
        }

        #container {
           -moz-user-select: none;
           -webkit-user-select: none;
           -ms-user-select: none;
           user-select: none;
           position: relative;
           overflow: hidden;
           min-height: 451px;
        }     
    
    </style>

{% endhighlight %}






The following screenshot illustrates the output.

![](TargetId_images/img1.png) 




