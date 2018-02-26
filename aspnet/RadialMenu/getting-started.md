---
layout: post
title: Getting Started | RadialMenu | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Radial Menu
documentation: ug
---

# Getting Started

## Creating your first RadialMenu in ASP Web Forms

1. Create an ASP.NET Web Forms application and add RadialMenu control to the Default.aspx page.

    ![](getting-started_images\getting-started_img3.png)

2. Once the control is dragged and dropped into the page the embedded resource will add dependent script and CSS files from Syncfusion.EJ.Web assembly and the assembly will be referred from GAC. This will add the following appSetting key in web.config file to load resource files.

    {% highlight xml %}
        
        <appSettings>
                <add key="LoadEJResourcesFromAssembly" value="true"/>
                <add key="EJResources" value="jsrender:true;jqueryeasing:true;globalize:true;themes:true;"/>
        </appSettings>
            
    {% endhighlight %}
    
N> Refer the [ASP.NET-Getting Started](http://help.syncfusion.com/aspnet/getting-started#manual-integration-of-syncfusion-aspnet-controls-into-the-newexisting-application) Documentation to know further details about necessary assemblies, Script and CSS files.

3. Configure the RadialMenu control using smart tag, to add RadialMenu items

    ![](getting-started_images\getting-started_img4.png)

    Switching from Design view to Source the RadialMenu code looks like the below. Syncfusion namespace will be registered and control will be initialized from the Syncfusion.EJ.Web namespace tag prefix "ej". The items to RadialMenu are added using the RadialMenuItem child element under Items.

    {% highlight html %}
            <ej:RadialMenu ID="RadialMenu1" runat="server" AutoOpen="true">
                <Items>
                    <ej:RadialMenuItems ID="RadialMenuItems1" runat="server" Enabled="True" Text="Copy" ImageURL="Content/images/copy.png">
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ID="RadialMenuItems2" runat="server" Enabled="True" Text="Paste" ImageURL="Content/images/paste.png">
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ID="RadialMenuItems3" runat="server" Enabled="True" Text="Redo" ImageURL="Content/images/redo.png">
                    </ej:RadialMenuItems>
                    <ej:RadialMenuItems ID="RadialMenuItems4" runat="server" Enabled="True" Text="Undo" ImageURL="Content/images/undo.png">
                    </ej:RadialMenuItems>
                </Items>            
            </ej:RadialMenu>
    {% endhighlight %}

4. Execute the code to get the below output

    ![](getting-started_images\getting-started_img5.png)

## Create a Simple RadialMenu with RTE content

**RadialMenu** can be rendered using ul li element or div element.   

![](getting-started_images\getting-started_img1.png)

**Create a simple Radial Menu**

The following steps guide you to add a **Radial Menu** control.

Create an ASP Project and add the necessary assemblies and scripts with the help of the given [ASP Getting Started](http://help.syncfusion.com/aspnet/getting-started) documentation.

Add the following code snippet in corresponding ASPX page to render the RadialMenu.

You can set the images for each item by giving the image URL to the **ImageURL** attribute in the RadialMenuItems and text to **Text** attribute. Refer the following code example.Initialize **Radial Menu** control and set its target content as follows.

{% highlight html %}

      <ej:RadialMenu ID="defaultRadialMenu" runat="server" TargetElementId="radialTargetOne" >         
            <Items>
           
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/copy.png" Text="Copy" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/paste.png" Text="Paste"></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/redo.png" Text="Redo" ></ej:RadialMenuItems>
                <ej:RadialMenuItems ImageURL="asp.syncfusion.com/demos/web/Content/images/RadialMenu/undo.png" Text="Undo" ></ej:RadialMenuItems>
            
            </Items>

        </ej:RadialMenu>

{% endhighlight %}

Refer to the following code example to add target content to the **Radial Menu**.

{% highlight html %}

     <div id="contentDiv">

            <div id="radialTargetOne" class="content-container-fluid">
                <div class="row">
                        <ej:RTE ID="rteSampleone" runat="server" Width="100%" ShowToolBar="false"  ClientSideOnSelect="radialShow">
                        <RTEContent>
                        <p>Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                        The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                        Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                        The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusable and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.</p>
                        <p>A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).</p>

                        <p>A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.</p>

                        <p>A view requests from the model the information that it needs to generate an output representation to the user.</p>
    </RTEContent></ej:RTE>
                </div>
            </div>

        </div>

{% endhighlight %}

Add the following styles in your code.
    
{% highlight css %}

    <style type="text/css" class="cssStyles">
         #rteSampleone {
            width: 100%;
        }
    </style>


{% endhighlight %}


You can display the **Radial Menu** by performing desired action on the target content while selecting the text inside the target. Therefore, call the **radialShow** method in the select action of the content. Refer  the following code example and add it to the script.

{% highlight javascript %}

           
            function radialShow(e) {
            var target = $("#radialTargetOne"), radialRadius = 150, radialDiameter = 2 * radialRadius,
            // To get Iframe positions
            iframeY = target.offset().top + e.event.clientY, iframeX = target.offset().left + e.event.clientX,
            // To set Radial Menu position within target
            x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
            y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
            $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("setPosition", x, y);
        }               
 
{% endhighlight %}

Run the above code and select any text inside the target. The settings icon is displayed. Click that icon to render the following output.


![](getting-started_images\getting-started_img2.png)

