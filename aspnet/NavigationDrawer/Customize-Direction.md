---
layout: post
title: Customize Direction | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: customize direction
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Customize Direction

Using this property you can set the drawer to be open from right to left direction or left to right direction. The possible direction values are Right, Left and the default value is Left. Refer to the following code example.

{% highlight html %}
 
    <div class="cols-sample-area" style="padding: 0px; position:relative;  margin: 0px; min-height: 451px; width: 100%;">
    <div id="butdrawer" class="drawericon e-icon"></div>
    <ej:NavigationDrawer runat="server" Direction="Right" ID="navpane" Position="Normal"  EnableListView="true" TargetId="butdrawer" >
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

Add the following code in style section

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
            float:right;
        }
         .e-drawericon:before{
			content: "\e76b";
            font-size: 28px;
            height:26px;
		}
    </style>
{% endhighlight %}


The following screenshot displays the output by swiping from right to left at the right side end of the screen.

![](Customize-Direction_images/img1.png) 



