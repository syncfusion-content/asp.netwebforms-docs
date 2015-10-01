---
layout: post
title: Splitter Orientation | Splitter | ASP.NET | Syncfusion
description: splitter orientation
platform: aspnet
control: Splitter
documentation: ug
---

# Splitter Orientation

The Splitter supports both vertical and horizontal orientation of the pane. You can declare the orientation by using enum, Vertical or Horizontal, that has corresponding value of vertical and horizontal as a string.

## Configure Splitter Orientation

The following steps explain the implementation of Splitter orientation option.

In an ASPX page, define the Splitter control and add the contents correspondingly. Set the Orientation property as Vertical.

{% highlight html %}

<ej:Splitter ID="splitter" Height="280" Width="400" Orientation="Vertical" runat="server">

           <ej:SplitPane>

             <div>

                <div style="padding: 10px 0 0 10px; text-align: center;">Pane 1</div>

             </div>

           </ej:SplitPane>

           <ej:SplitPane>

             <div>

                <div style="padding: 10px 0 0 10px; text-align: center;">Pane 2</div>

            </div>

          </ej:SplitPane>

</ej:Splitter>

{% endhighlight %}



The following screenshots display the Splitter with horizontal and vertical orientation. 

 ![](Splitter-Orientation_images/Splitter-Orientation_img1.png)



 ![](Splitter-Orientation_images/Splitter-Orientation_img2.png)



