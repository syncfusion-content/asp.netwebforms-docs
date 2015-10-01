---
layout: post
title: Template Support | Tab | ASP.NET | Syncfusion
description: template support
platform: aspnet
control: Tab
documentation: ug
---

# Template Support

In the ASP.NET, you can use the <contentsection> tag to load the contents to the Tab control.

{% highlight html %}

<ej:Tab ID="pizzaMenu" runat="server" Width="650px">

    <Items>

        <ej:TabItem ID="Tabitem1" Text="GARDEN FRESH (Veg)">

            <ContentSection>

                <img src=" http://js.syncfusion.com/demos/web/images/

                 accordion/garden-veggie.png" alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $50

                    <br />

                    Ingredients : cheese, onions, green capsicums & tomatoes.

                </div>

            </ContentSection>

        </ej:TabItem>

        <ej:TabItem ID="Tabitem2" Text="CORN & SPINACH (Veg)">

           <ContentSection>

                <img src=" http://js.syncfusion.com/demos/web/images

                /accordion/corn-and-spinach-05.png" alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $70

                    <br />

                    Ingredients : cheese, sweet corn & green capsicums.

                </div>

           </ContentSection>

        </ej:TabItem>

        <ej:TabItem ID="Tabitem3" Text="CHICKEN DELITE (Non-veg)">

          <ContentSection>

                <img src=" http://js.syncfusion.com/demos/web/images/

                 accordion/chicken-delite.png" alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $100

                    <br />

                    Ingredients : cheese, chicken chunks, onions & pineapple chunks.

                </div>

            </ContentSection>

        </ej:TabItem>

    </Items>

</ej:Tab>

{% endhighlight %}
![](Template-Support_images/Template-Support_img1.png) 





