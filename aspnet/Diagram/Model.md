---
layout: post
title: Model | Diagram | ASP.NET Webforms | Syncfusion
description: model
platform: aspnet
control: Diagram
documentation: ug
---

# Model

The Diagram model represents data for rendering the Diagram and manipulating the Diagram elements.

The following code illustrates how to create a Diagram with some model properties.

{% tabs %}

{% highlight html %}

<%--Creates Diagram--%>

<asp:ScriptManager ID="ScriptManager1" runat="server"></asp:ScriptManager>



<ej:Diagram ID="Diagram1" runat="server" Height="600px" Width="100%">        

</ej:Diagram>





{% endhighlight %}



{% highlight c# %}

    public partial class Diagram : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            if (!IsPostBack)

            {

                // Sets diagram model properties

                Diagram1.Model.Width = "100%";

                Diagram1.Model.Height = "100%";

                Diagram1.Model.PageSettings.PageWidth = 2000;

                Diagram1.Model.PageSettings.PageHeight = 2000;

            }

        }

    }



{% endhighlight %}

{% endtabs %}

![](Model_images/Model_img1.png) 

Model
{:.caption} 

