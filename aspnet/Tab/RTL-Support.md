---
layout: post
title: RTL Support | Tab | ASP.NET | Syncfusion
description: rtl support
platform: aspnet
control: Tab
documentation: ug
---

# RTL Support

Tab control provides support to load contents in the right to left format. This is achieved by setting the EnableRTL property to true.

The following code example is used to render the Tab element in the RTL format. 

Add the following ASPX to render the Tab with the RTL format.

{% highlight html %}

<ej:Tab ID="dishtype" runat="server" Width="600px" EnableRTL="true">

    <Items>

        <ej:TabItem ID="pizzatype" Text="Pizza Menu">

            <ContentSection>

                <p>

                    Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

            </ContentSection>

        </ej:TabItem>

        <ej:TabItem ID="sandwichtype" Text="Sandwich Menu">

            <ContentSection>

                <p>

                    Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

            </ContentSection>

        </ej:TabItem>

    </Items>

</ej:Tab>

{% endhighlight %}

The following screenshot illustrates the Tab with the RTL format.

![](RTL-Support_images/RTL-Support_img1.png) 



