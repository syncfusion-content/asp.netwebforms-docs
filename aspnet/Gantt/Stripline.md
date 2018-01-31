---
layout: post
title: Stripline | Gantt | ASP.NET Webforms | Syncfusion
description: stripline
platform: aspnet
control: Gantt
documentation: ug
---

# Stripline

Stripline in Gantt control is used to highlight the important event in Gantt chart part. By using this feature, you can add the Striplines to highlight important days in your project. The following code example shows you how to add the Stripline in Gantt control.

{% highlight html %}

<div style="width:100%;height:100%;overflow:visible;">                  

        <ej:Gantt ID="GanttControlDefault" runat="server">
            <StripLines>
                <ej:GanttStripLine Day="01/02/2014" Label="Project Release"  LineColor="blue" LineStyle="dotted" LineWidth="2" />
            </StripLines>
        </ej:Gantt>        
    </div>   

{% endhighlight %}

The following screenshot shows Stripline in Gantt control.

![](Stripline_images/Stripline_img1.png) 

Figure : Stripline
{:.caption}


