---
layout: post
title: Animations | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: animations
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Animations

You can set the transition type of the Navigation Drawer by using type property. The possible transition types are slide and overlay.

* Slide - both navigation panel and content page slides towards left/right direction to view the navigation panel items.
* Overlay - Only the navigation panel slides over the content page to view the navigation panel items. That is, part of the content page is hidden under navigation panel.

N> Transition slide type works only with fixed position.

The default value is Overlay.

{% highlight html %}

       <div class="cols-sample-area" style="padding: 0px; position:relative;  margin: 0px; min-height: 451px; width: 100%;">
              <button id="drawerTarget" style="top:200px;left:50%;position:absolute">Target Button</button>

        <ej:NavigationDrawer runat="server"  ID="navpane" Position="Fixed" Type="Slide"  EnableListView="true" TargetId="drawerTarget" >
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

![](Animations_images/img2.png) 



![](Animations_images/img1.png) 



