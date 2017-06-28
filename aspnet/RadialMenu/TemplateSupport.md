---
layout: post
title:  Template Support | Radial Menu | ASP.NET Webforms | Syncfusion
description: Template Support.
platform: aspnet
control: Radial Menu
documentation: ug
---
## Template Support

 Template support for RadialMenu items will allow you to use any type of [\<svg\>](https://developer.mozilla.org/en-US/docs/Web/SVG/Element#SVG_elements) permittable tags inside our template. Here for example, using this template support you can use the SVG icons in Radial Menu instead of image tags. To use SVG icons in RadialMenu, you need to use **PrependTo** property.

 ### Add SVG to item Icon

Using SVG icon will optimize the icons quality and to reduce space occupation by normal images and svg images are scalable and zoomable. Define the text element for SVG with x and y position and code for rendering the font icons. Assign the SVG element ID to PrependTo property.

Please add the following code in your ASP Content section,

{% highlight html %}

        <div id="contentDiv">
        <div id="radialtargetone" class="content-container-fluid">
            <div class="row">
                    <ej:RTE ID="rteSampleone" runat="server" Width="100%" MinWidth="10px" ShowContextMenu="false"  ClientSideOnChange="rteChange" ClientSideOnCreate="rteCreate" ClientSideOnSelect="radialShow" ShowToolBar="false">
                    <RTEContent>
                    <p>Model–view–controller (MVC) is a software architecture pattern which separates the representation of information from the user's interaction with it.
                    The model consists of application data, business rules, logic, and functions. A view can be any output representation of data, such as a chart or a diagram.
                    Multiple views of the same data are possible, such as a bar chart for management and a tabular view for accountants.
                    The controller mediates input, converting it to commands for the model or view.The central ideas behind MVC are code reusability and in addition to dividing the application into three kinds of components, the MVC design defines the interactions between them.</p>

                    <p>A controller can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). It can also send commands to the model to update the model's state (e.g., editing a document).</p>

                    <p>A model notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.</p>
                        
                    <p>A view requests from the model the information that it needs to generate an output representation to the user.</p>
                    </RTEContent></ej:RTE>
            </div>
        </div>

    <ej:RadialMenu ID="defaultradialmenu" runat="server" TargetElementId="radialtargetone" >         
            <Items>
                <ej:RadialMenuItems PrependTo="#template1"  Click="bold" Text="Bold"></ej:RadialMenuItems>
                <ej:RadialMenuItems PrependTo="#template2"  Text="Italic" Click="italic"></ej:RadialMenuItems>
                <ej:RadialMenuItems PrependTo="#template3" Text="Redo" Click="redo" Enabled="false"></ej:RadialMenuItems>
                <ej:RadialMenuItems PrependTo="#template4"  Text="Undo" Click="undo" Enabled="false"></ej:RadialMenuItems>
            
            </Items>
    </ej:RadialMenu>
         <svg id="template1" style="display: none" xmlns="http://www.w3.org/2000/svg">
            <text x="210" y="100">&#xe636;</text>
         </svg>
        <svg id="template2" style="display: none" xmlns="http://www.w3.org/2000/svg">
            <text x="210" y="218">&#xe635;</text>
        </svg>
         <svg id="template3" style="display: none" xmlns="http://www.w3.org/2000/svg">
          <text x="90" y="215">&#xe606;</text>
        </svg>
        <svg id="template4" style="display: none" xmlns="http://www.w3.org/2000/svg">
         <text x="93" y="100">&#xe607;</text>
        </svg>
        </div>
{% end highlight %}

Add the folling code in your Script Section,

{% highlight javascript %}

        $(function () {
            if (!(ej.browserInfo().name == "msie" && ej.browserInfo().version < 9)) {
                $("#radialtargetone").parent().css("position", "relative");
                }
                else {
                    $("#contentDiv").html("Radial Menu is only supported from Internet Explorer Versioned 9 and above.").css({ "font-size": "20px", "color": "red" });
                }
				$(window).resize(function(){
					if(ej.isMobile() && ej.isPortrait())
						$('#defaultradialmenu').css({"left":25})
				});
            });
            var rteObj, rteEle = $('#<%=rteSampleone.ClientID%>'), radialEle = $('#<%=defaultradialmenu.ClientID%>'), action = 0, forRedo = 0;
            function rteCreate(e) {
                rteObj = this;
            }
            function radialShow(e) {
                var target = $("#radialtargetone"), radialRadius = 150, radialDiameter = 2 * radialRadius,
                // To get Iframe positions
                iframeY = e.event.clientY, iframeX = e.event.clientX,
                // To set Radial Menu position within target
                x = iframeX > target.width() - radialRadius ? target.width() - radialDiameter : (iframeX > radialRadius ? iframeX - radialRadius : 0),
                y = iframeY > target.height() - radialRadius ? target.height() - radialDiameter : (iframeY > radialRadius ? iframeY - radialRadius : 0);
                $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("setPosition", x, y);
				$('iframe').contents().find('body').blur();
            }
            function click(e) {
                $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("hideMenu");
            }
            function rteChange(e) {
                   $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("enableItem", "Undo");
            }
            function bold(e) {
                rteObj.executeCommand("bold");
                data = rteObj._getSelectedHtmlString() ? true : false;
                if (data) action += 1;
                forRedo = action;
            }
            function italic(e) {
                rteObj.executeCommand("italic");
                data = rteObj._getSelectedHtmlString() ? true : false;
                if (data) action += 1;
                forRedo = action;
            }
            function undo(e) {
                rteObj.executeCommand("undo");
                action -= 1;
                if (action == 0)  $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("disableItem", "Undo");
                $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("enableItem", "Redo");
            }
            function redo(e) {
                rteObj.executeCommand("redo");
                action += 1;
                if (forRedo == action)  $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("disableItem", "Redo");
                $('#<%=defaultradialmenu.ClientID%>').ejRadialMenu("enableItem", "Undo");
        }

{% end highlight %}

Use following in style section to render svg icon,

{% highlight javascript %}

  
        #rteSampleone {
            width: 100%;
        }
        @font-face {
            font-family: 'ej-webfont';
            font-weight: normal;
            font-style: normal;
            font-size: 20px;
        }

        .e-radialmenu .e-abs.e-radialshow, .e-radialmenu .e-abs.e-scaleshow {
            /* use !important to prevent issues with browser extensions that change fonts */
            font-family: 'ej-webfont' !important;
            speak: none;
            font-size: 20px;
            font-style: normal;
            font-weight: normal;
            font-variant: normal;
            text-transform: none;
            line-height: 1;
            -webkit-font-smoothing: antialiased;
            /* Better Font Rendering =========== */
            -webkit-font-smoothing: antialiased;
            -moz-osx-font-smoothing: grayscale;
        }
       
{% end highlight %}


The following screenshot illustrates the output,

![](template-support\img1.png)

     N> This is the example sample for SVG icon support for Radial Menu.Like wise you can add any SVG element to it, but you need to customize and position the element individually.
