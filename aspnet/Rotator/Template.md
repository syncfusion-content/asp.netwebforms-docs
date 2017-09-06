---
layout: post
title: Template | Rotator | ASP.NET Webforms | Syncfusion
description: template
platform: aspnet
control: Rotator
documentation: ug
---

# Template

This Template feature implements in Rotator control. Rotator template will allow you to customize the rendering structure for its li elements. Using template API with data binding can render image, audio or video inside the Rotator control. 

The property template specifies the structure for slide li elements. The default value is null. The value set to this property is string. 


You can refer the following code example of Template in the Rotator.

In an ASPX page, add the following code example to render the Rotator control.



{% highlight html %}

<div class="control">
<ej:Rotator ID="sliderContent" runat="server" SlideWidth="600px" FrameSpace="0px" DisplayItemCount="1" SlideHeight="350px" ShowCaption="true" Template="<div class='image'><img src = ${url} title = ${text} class='image'/> </div>">
    </ej:Rotator>  
</div>   

{% endhighlight %}


{% highlight c# %}

       public partial class Template : System.Web.UI.Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                List<LocalData> LocalValues = new List<LocalData>();
                LocalValues.Add(new LocalData{ text= "Beautiful Bird", url= "../Images/rotator/bird.jpg" });
                LocalValues.Add(new LocalData { text = "Colorful Night", url = "../Images/rotator/night.jpg" });
                LocalValues.Add(new LocalData { text = "Technology", url = "../Images/rotator/tablet.jpg" });
                LocalValues.Add(new LocalData { text = "Nature", url = "../Images/rotator/nature.jpg" });
                LocalValues.Add(new LocalData { text = "Snow Fall", url = "../Images/rotator/snowfall.jpg" });
                LocalValues.Add(new LocalData { text = "Credit Card", url = "../Images/rotator/card.jpg" });
                LocalValues.Add(new LocalData { text = "Amazing Sculptures", url = "../Images/rotator/sculpture.jpg" });
                ViewBag.datasource=LocalValues;
            }
        }
        public class LocalData
        {
            public string Text { get; set; }
            public string url { get; set; }
        }

{% endhighlight %}

Define the style for the Rotator control.


{% highlight css %}

       .frame {
            width: 100%;
            box-sizing : border-box;
        }
        #<%=sliderContent.ClientID%> > li img {
            width: 100%;
            height: 350px;
        }

{% endhighlight %}
