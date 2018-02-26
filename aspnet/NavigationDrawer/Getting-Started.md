---
layout: post
title: Getting Started | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Getting Started

## Create your first Navigation Drawer control in ASP.NET Webforms

NavigationDrawer is a sliding panel that displays the list of navigation options on demand. That is, by default, it is not visible but you can display it on the left/right side of the screen by swiping or by clicking with desired target icon.                       

![](Getting-Started_images/img1.png) 



### Create Navigation Drawer Widget

The following steps guide you in adding a Navigation Drawer control for a web application that displays a list of items such as home, profile, photos and location where you can navigate to desired page by clicking on the option available in the drawer. 

     1. Create a Syncfusion ASP.NET Web Forms application.
     2. Add the following code in .aspx file you have

{% highlight html %}

     <div id="butDrawer" class="drawericon e-icon"></div>
    <ej:NavigationDrawer runat="server" ID="navpane" Direction="Left" Type="Overlay" EnableListView="true" TargetId="butDrawer" >
                        <ListViewSettings Width="300" SelectedItemIndex="0" PersistSelection="true" />
                        <Items>
                            <ej:NavigationDrawerItems  Text="Home"  ID="navhome" />
                            <ej:NavigationDrawerItems  Text="Profile"  ID="navprofile" />
                            <ej:NavigationDrawerItems  Text="Photos"  ID="navphotos" />
                            <ej:NavigationDrawerItems  Text="Location"  ID="navlocation" />
                        </Items>
                    </ej:NavigationDrawer>

{% endhighlight %}



Create a div element that acts as a container for Navigation Drawer's Content. Refer to the following code example.

{% highlight html %}

    <div id="container">
                        <div class="e-lv">
                            <div class="e-header">
                                <div id="butDrawer" class="drawericon e-icon"></div>
                                <h2>Home</h2>
                            </div>
                        </div>
                        <div id="content_container"></div>
                        <div id="home" class="subpage">
                            <p>
                               The Home screen allows you to choose the specific content type displayed.
                            </p>
                        </div>
                         <div id="profile" class="subpage">
                               The Profile page content is displayed.
                             </div>
                        <div id="photos" class="subpage">
                            The Photos page content is displayed.
                        </div>
                        <div id="location" class="subpage">
                            The Location page content is displayed.
                        </div>
                    </div>

{% endhighlight %}



From the above code you can create the target element as follows to display the drawer by clicking target icon.


To set the target icon image from sprite and to positioning the target icon and contents properly use the following styles.

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

         .subpage {
            padding: 10px;
            text-align: justify;
            overflow-x: auto;
            overflow-y: auto;
        }

        #<%=navpane.ClientID%> .subpage {
            padding: 0px;
        }
         .e-drawericon:before{
			content: "\e76b";
            font-size: 28px;
            height:26px;
		}
    </style>


{% endhighlight %}



Create the navigation drawer control as follows. You can display the navigation items as a list (or it can be any template) by using listview control. This is achieved by setting enableListView property as true. Also you can open the drawer by clicking on target element by setting the targetId property. 

## Navigation Drawer

You can display the drawer either by clicking on the target icon or by swiping from left on the page. Refer to the following screenshot.



![](Getting-Started_images/img2.png) 



You can set contents and navigate to the contents from the navigationDrawers listview, by using the following code.


{% highlight html %}

    <ej:NavigationDrawer runat="server" ID="navpane" Direction="Left" Type="Overlay" EnableListView="true" TargetId="butDrawer" ContentId="content_container">
                        <ListViewSettings Width="300" SelectedItemIndex="0" PersistSelection="true" MouseUp="headChange" />
                        <Items>
                            <ej:NavigationDrawerItems ImageURL="../Content/images/navigationdrawer/home.png" Text="Home" Href="#home" ID="navhome" />
                            <ej:NavigationDrawerItems ImageURL="../Content/images/navigationdrawer/profile.png" Text="Profile" Href="#profile" ID="navprofile" />
                            <ej:NavigationDrawerItems ImageURL="../Content/images/navigationdrawer/photo.png" Text="Photos" Href="#photos" ID="navphotos" />
                            <ej:NavigationDrawerItems ImageURL="../Content/images/navigationdrawer/locations.png" Text="Location" Href="#location" ID="navlocation" />
                        </Items>
                    </ej:NavigationDrawer>


{% endhighlight %}

In the above code we have added targetId and contentId to find and navigate to sub pages.


Run the above code to render the following output.

![](Getting-Started_images/img3.png) 


You can load the appropriate content for the navigation items by updating the content through mouseDown handler of listview. You can define the handler and pass the method name with mouseDown attribute through listViewSettings. Also to view which item’s content is being loaded in the page, make the list selection to persist in the drawer by setting persistSelection as true. Refer to the following code example.



{% highlight js %}

    <script type="text/javascript">
        $(function () {
            $(".e-lv").addClass("e-navigation");
        });
        function headChange(e) {
            $("#butDrawer").parent().children("h2").text(e.text);
        }
    </script>



{% endhighlight %}


In the mouse down handler, you can hide the other content and display the respective selected item’s content.

Run the above code to render the following output. 

![](Getting-Started_images/img3.png) 



