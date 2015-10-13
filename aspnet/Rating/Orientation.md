---
layout: post
title: Orientation | Rating | ASP.NET | Syncfusion
description: orientation
platform: aspnet
control: Rating
documentation: ug
---

# Orientation

Rating provides support for the vertical orientation. By default, Rating renders with horizontal orientation. You can the change the orientation by the orientation property.

Add the following code example to the corresponding ASPX page to render the Rating with the customized orientation.

{% highlight html %}
<div id="container" style="border: 1px solid black; width: 300px; padding: 2px">

            <table>

                <tr>

                    <td valign="top">Rating:

                    </td>

                    <td>

                        <ej:Rating ID="Rating1" Orientation="Vertical"runat="server"> </ej:Rating>

                    </td>

                </tr>

            </table>

</div>
{% endhighlight %}

The following screenshot displays the output of the above code example.

![](Orientation_images/Orientation_img1.png)