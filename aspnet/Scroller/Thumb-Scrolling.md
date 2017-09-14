---
layout: post
title: Thumb Scrolling | Scroller | ASP.NET | Syncfusion
description: thumb scrolling
platform: aspnet
control: Scroller
documentation: ug
---

# Thumb Scrolling

Normally, the scrollbar position is changed by dragging the scrollbar handle or click the arrows. The Scroller control allows you to pan or drag the scroll content area. To achieve this in your Scroller control, set the EnableTouchScroll set as true. In Scroller control, the default value for **EnableTouchScroll** is true. When you want to prevent panning or dragging the scroll content area, set EnableTouchScroll to false.

The following steps explains the configuration of EnableTouchScroll property in Scroller. 

In an ASPX page, add the following code to render Scroller.

{% highlight html %}

<ej:Scroller ID="scrollcontent" runat="server" Height="170" Width="350" EnableTouchScroll="false">
      <ScrollerContent>
                <div>
                    <div class="sampleContent">
                        <h3 style="font-size: 20px;">MVC</h3>
                        <div>
                            <p>
                                Model–view–controller (MVC) is a software architecture pattern which separates the
                                    representation of information from the user's interaction with it.
                                    The model consists of application data, business rules, logic, and functions. A view can be any
                                    output representation of data, such as a chart or a diagram. Multiple views of the same data 
                                    are possible, such as a bar chart for management and a tabular view for accountants. 
                                    The controller mediates input, converting it to commands for the model or view.The central 
                                    ideas behind MVC are code reusable and n addition to dividing the application into three 
                                    kinds of components, the MVC design defines the interactions between them.
                            </p>
                            <ul>
                                <li>
                                    <b>A controller </b>can send commands to its associated view to change the view's presentation of the model (e.g., by scrolling through a document). 
                                                 It can also send commands to the model to update the model's state (e.g., editing a document).

                               </li>
                                <li>
                                    <b>A model</b> notifies its associated views and controllers when there has been a change in its state. This notification allows the views to produce updated output, and the controllers to change the available set of commands. 
                                                A passive implementation of MVC omits these notifications, because the application does not require them or the software platform does not support them.
                                </li>
                                <li>
                                    <b>A view</b> requests from the model the information that it needs to generate an output representation to the user.
                                </li>
                            </ul>
                        </div>
                    </div>
                </div>
      </ScrollerContent>
</ej:Scroller>

{% endhighlight %}

Define the style for Scroller control

{% highlight css %}

.sampleContent {
	width: 700px;
	padding: 15px;
}

{% endhighlight %}


The following screenshot displays the output of the above code example.

![](Thumb-Scrolling_images/Thumb-Scrolling_img1.png)