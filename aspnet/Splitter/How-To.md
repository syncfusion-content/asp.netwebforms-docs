---
layout: post
title: How to section in Splitter? 
description: How to achieve specific requirements in Splitter
platform: aspnet
control: Splitter
documentation: ug
---
# How To?

### Change Expand/Collapse icons

By default, you are provided with collpase/expand icons in **Split bar** to collapse or expand the splitter panes. We have provided template support to replace existing expand/collapse icons.

* **expanderTemplate** Specifies HTML element string to replace template with existing expand/collapse icons. 

* **clickOnExpander** event is triggered when we click on the template icon.`

{% highlight html %}

<ej:Splitter ID="innersplitter" Height="250" Width="80%" ExpanderTemplate="<img class='eimg' src='../Content/basketball.png' ClientSideOnClickOnExpander="template" alt='employee'/>" runat="server" >
    <ej:SplitPane>
        <div>
            <div class="cont">Pane 1</div>
        </div>
    </ej:SplitPane>
    <ej:SplitPane>
        <div>
            <div class="cont">Pane 2</div>
        </div>
    </ej:SplitPane>
</ej:Splitter>

{% endhighlight %}

{% highlight js %}

       function template(args) {
            if (flag) { this.collapse(0); flag = false; }
            else { this.expand(0); flag = true; }
        }

{% endhighlight %}

{% highlight css %}

        .cont {
            padding: 10px 0 0 10px;
            text-align: center;
        }   
         .eimg {
            height:40px;
            width:35px;
			margin-left: -13px;
        }  

		.ediv {
           height: 30px;
			width: 45px;
			background-color: darkblue;
			margin-top: -130px;
			margin-left: -20px;
        }  
       .e-splitter .e-splitbar .e-splitter-h-template {
            top: 15%;
       }

{% endhighlight %}

The output for Splitter with **Tempalet support**.

![](How-To_images/Template_Support_img.png) 