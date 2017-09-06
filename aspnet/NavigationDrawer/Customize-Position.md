---
layout: post
title: Customize Position | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: customize position
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Customize Position

Position property is used to specify the position whether it is in fixed or relative to the page. When you set a normal value to position property, it appears within the container. Otherwise, it appears in the whole body .The possible position values are fixed and normal. The Default value is normal.

{% highlight html %}
        
    <div class="cols-sample-area" style="padding: 0px; position:relative;  margin: 0px; min-height: 451px; width: 100%;">
         <div id="butdrawer" class="drawericon e-icon"></div>
              <ej:NavigationDrawer runat="server"  ID="navpane" Position="Fixed" Type="Slide" EnableListView="true" TargetId="butdrawer" >
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
            .e-drawericon {
            background-position: center center;
            background-repeat: no-repeat;
            height: 32px;
            width: 32px;
            background-size: 100% 100%;
            padding-right: 10px;
                  }
         .e-drawericon:before{
			content: "\e76b";
            font-size: 28px;
            height:26px;
		}
    </style>

{% endhighlight %}


The following screenshot illustrates the output by swiping from left to right at the left end of the screen.

![](Customize-Position_images/img2.png) 



