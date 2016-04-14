---
layout: post
title: Getting Started | NavigationDrawer | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Navigation Drawer
documentation: ug
---

# Getting Started

## Create your first Navigation Drawer control in JavaScript

EssentialJavaScriptNavigation Drawer is a sliding panel that displays the list of navigation options on demand. That is, by default, it is not visible but you can display it on the left/right side of the screen by swiping or by clicking with desired target icon.                       

![](Getting-Started_images/Getting-Started_img1.png) 



### Create Navigation Drawer Widget

The following steps guide you in adding a Navigation Drawer control for a web application that displays a list of items such as home, profile, photos and location where you can navigate to desired page by clicking on the option available in the drawer. 

Create an HTML file and paste the following template for web layout.       

{% highlight html %}

<head>

    <title>Navigation Drawer</title>

    <link href="[http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css](http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css)" rel="stylesheet" />

     <script src="[http://code.jquery.com/jquery-1.10.2.min.js](http://code.jquery.com/jquery-1.10.2.min.js)"></script>

    <script src="[http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js](http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js)"></script>

</head>

<body>

        <!-- Add Navigation Drawer control Here -->

        <!-- Add Page Content content Here -->

</body>

</html>



{% endhighlight %}



Create a div element that acts as a container for Navigation Drawer. Refer to the following code example.

{% highlight html %}

<div id="navpane">

     <ul>

          <li data-ej-text="Home"></li>

          <li data-ej-text="Profile"></li>

          <li data-ej-text="Photos"></li>

          <li data-ej-text="Location"></li>

     </ul>

</div>



{% endhighlight %}



Create the target element as follows to display the drawer by clicking target icon.

{% highlight html %}

<div class="navi">

     <div id="target" class="icon-target"> Drawer</div>

</div>





{% endhighlight %}



To set the target icon image from sprite and to position the target icon properly use the following styles.

{% highlight css %}

<style>

        [class*="icon-"]

        {

            background-image: url("http://js.syncfusion.com/ug/web/content/drawer/sprite.png");

        }

     .icon-target 

        {

             background-position: 0 -338px;

             font-size: 34px;

             height: 48px;

             position: absolute;

             text-indent: 50px;

             top: -3px;

             width: 48px;

             z-index: 3;

         }

     .navi 

        {

            background: none repeat scroll 0 0 #C4C4B4;

            color: #fff;

            height: 45px;

            padding-left: 5px;

            width: 100%;

        }

       body

         {

            background: none repeat scroll 0 0 #ece9d8;

         }

</style>



{% endhighlight %}



Create the navigation drawer control as follows. You can display the navigation items as a list (or it can be any template) by using listview control. This is achieved by setting enableListView property as true. Also you can open the drawer by clicking on target element by setting the targetId property. 

{% highlight js %}

<script type="text/javascript">

  $(function () {

       $("#navpane").ejNavigationDrawer({ enableListView: true, targetId: "target"});

  });

 </script>



{% endhighlight %}

## Navigation Drawer

You can display the drawer either by clicking on the target icon or by swiping from left on the page. Refer to the following screenshot.



![](Getting-Started_images/Getting-Started_img2.png) 



You can set the images for Navigation Drawer by using data-ej-imageclass attribute in the inner list elements.

{% highlight html %}

<div id="navpane">

   <ul>

     <li data-ej-imageclass="icon-home" data-ej-text="Home"></li>

     <li data-ej-imageclass="icon-profile" data-ej-text="Profile"></li>

     <li data-ej-imageclass="icon-photo" data-ej-text="Photos"></li>

     <li data-ej-imageclass="icon-locations" data-ej-text="Location"></li>

  </ul>

</div>



{% endhighlight %}



You can define the image classes specified for the list items as follows.

{% highlight css %}

<style>

        #navpane [class*="icon-"]

        {

            width: 35px;

            height: 35px;

        }

        .icon-home

        {

            background-position: 0 0;

        }

        .icon-profile

        {

            background-position: 0 -253px;

        }

        .icon-photo

        {

            background-position: 0 -168px;

        }

        .icon-locations

        {

            background-position: 0 -85px;

        }    
</style>



{% endhighlight %}



Run the above code to render the following output.

![C:/Users/ApoorvahR/Desktop/1.png](Getting-Started_images/Getting-Started_img3.png) 



You can add desired page content while selecting the options in navigation drawer as follows.



{% highlight html %}

<!-- Home Page Content-->

<div id="Home">

  The Home screen allows you to choose the specific content type displayed.

</div>

<!-- Profile Page Content-->

<div id="Profile" style="display: none">

   The Profile page content is displayed.

</div>

<!-- Photos Page Content-->

<div id="Photos" style="display: none">

    The Photos page content is displayed.

</div>

<!-- Location Page Content-->

<div id="Location" style="display: none">

     The Location page content is displayed.

</div>



{% endhighlight %}



You can load the appropriate content for the navigation items by updating the content through mouseDown handler of listview. You can define the handler and pass the method name with mouseDown attribute through listViewSettings. Also to view which item’s content is being loaded in the page, make the list selection to persist in the drawer by setting persistSelection as true. Refer to the following code example.



{% highlight js %}

<script type="text/javascript">

  $(function () {

       $("#navpane").ejNavigationDrawer({ enableListView: true, targetId: "target", listViewSettings: { mouseDown: 'slideMenuClick', persistSelection: true } });

  });

</script>



{% endhighlight %}



In the mouse down handler, you can hide the other content and display the respective selected item’s content.



{% highlight js %}

<script type="text/javascript">

function slideMenuClick(e) {

        $('#Home, #Profile, #Photos, #Location').hide(); //Hiding all other contents

        $('#' + e.text).show(); //Displaying the content based on the text of item selected

        $("#navpane").ejNavigationDrawer("close");

    }

    </script>



{% endhighlight %}



Run the above code to render the following output. 

![](Getting-Started_images/Getting-Started_img4.png) 



