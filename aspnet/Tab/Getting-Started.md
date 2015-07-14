---
layout: post
title: Getting-Started
description: getting started 
platform: aspnet
control: Tab
documentation: ug
---

# Getting Started 

This section explains briefly how to create a Tab Control in your application with ASP.NET.

## Create your first Tab control in ASP.NET	

The ASP.NET Tab control is an interface that displays the content in multiple sections. Each TabPanel consists of HeaderText or HeaderTemplate as well as a ContentTemplate. Tab is useful for a dashboard that contains limited space. The following section guides you to customize the Tab for displaying Hotel menu items, its rating details, and ingredients.

{ ![](Getting-Started_images/Getting-Started_img1.png) | markdownify }
{:.image }




Create Tab control

You can create an ASP Project and add the necessary Dll and scripts with the help of the given [ASP-Getting Started](http://help.syncfusion.com/ug/js/Documents/gettingstartedwithmv.htm) Documentation.

Add the following code example to the corresponding ASP page for Tabrendering.

{% highlight html %}

    <form id="form1" runat="server">

        <div>

            <ej:Tab ID="DishType" runat="server" Width="600px">

                <Items>

                    <ej:TabItem Id="PizzaType" Text="Pizza Menu">

                        <ContentSection>

                            <%-- Enter your contents here --%>

                        </ContentSection>

                    </ej:TabItem>

                    <ej:TabItem Id="SandwichType" Text="Sandwich Menu">

                        <ContentSection>

                            <%-- Enter your contents here --%>

                        </ContentSection>

                    </ej:TabItem>

                    <ej:TabItem Id="PastaType" Text="Pasta Menu">

                        <ContentSection>

                            <%-- Enter your contents here --%>

                        </ContentSection>

                    </ej:TabItem>

                </Items>

            </ej:Tab>

        </div>

    </form>



{% endhighlight %}

Output of the above steps.



{ ![](Getting-Started_images/Getting-Started_img2.png) | markdownify }
{:.image }


Configure content

In this application, a detailed description is provided to each item. You can specify the contents in the Tab section within the &lt;ContentSection &gt; by using the following format. 

{% highlight html %}

<ej:Tab ID="DishType" runat="server" Width="500px">

                <Items>

                    <ej:TabItem Id="PizzaType" Text="Pizza Menu">

                        <ContentSection>

                            <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

                        </ContentSection>

                    </ej:TabItem>

<!--Reuse remaining Tab contents-->  

                </Items>

            </ej:Tab>



{% endhighlight %}

You can provide more customization to the Tab with rating control as the content to describe the item rating value.

The following screenshot is the output of the above code example:

{ ![](Getting-Started_images/Getting-Started_img3.png) | markdownify }
{:.image }


Create the rating in the Tab

The ASP.NET Rating control provides an intuitive rating experience that allows you to select the number of stars that represents the rating. The following code example explains he rating control creation. Render the rating control by using the &lt;ej:Rating&gt; tag. The code example is placed within the content description( &lt;ContentSection &gt; ) element to declare the rating control and description in the Tab section and it can be appended with the control initialization code section &lt;ej:Tab&gt; element by using the following format.

{% highlight html %}

<ej:Tab ID="DishType" runat="server" Width="500px">

                <Items>

                    <ej:TabItem Id="PizzaType" Text="Pizza Menu">

                        <ContentSection>

                            <div>

                                Rating : 

                                 <div>                                     <ej:Rating ID="GardenPizza" Precision="Exact" Value="4.9" runat="server"></ej:Rating>

                                 </div>                                

                            </div>

                            <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

                        </ContentSection>

                    </ej:TabItem>

 <!--Reuse remaining Tab contents-->  

                </Items>

            </ej:Tab>                 



{% endhighlight %}



The following screenshot is the output of the above code example:

{ ![](Getting-Started_images/Getting-Started_img4.png) | markdownify }
{:.image }


Sub Tab with content 

Each item has a variety of options and these options are also specified in the limited space. So, you can choose the Tab control that is used within the root Tab to specify more details.

The following code example illustrates how to create the Tab control within the root Tab element. This HTML code is appended within the previous HTML code section. To render the child Tab with its header, add this code example within the &lt;ej:Tab &gt; tag by using the following format.

The sub Tab control rendering is represented in the following code example.

&lt;!--Use the following codes with in the  above Html --&gt;

&lt;ej:Tab ID="DishType" runat="server" Width="500px"&gt;

    &lt;Items&gt;

        &lt;ej:TabItem Id="PizzaType" Text="Pizza Menu"&gt;

            &lt;ContentSection&gt;

                &lt;div&gt;

                    Rating : 

                                 &lt;div&gt;

                                     &lt;ej:Rating ID="GardenPizza" Precision="Exact" Value="4.9" runat="server"&gt;&lt;/ej:Rating&gt;

                                 &lt;/div&gt;

                &lt;/div&gt;

                <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.&lt;/p&gt;

                &lt;ej:Tab ID="PizzaTab" runat="server"&gt;

                    &lt;Items&gt;

                        &lt;ej:TabItem Id="PizzaMenu" Text="Corn Spinach"&gt;

                            &lt;ContentSection&gt;

                                &lt;img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach"&gt;

                                &lt;div class="ingredients"&gt;

                                    Rate    : $70<br />

                                    Ingredients : cheese, sweet corn &amp; green capsicums.&lt;br /&gt;

                                    Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.  

                                &lt;/div&gt;

                            &lt;/ContentSection&gt;

                        &lt;/ej:TabItem&gt;

                        &lt;ej:TabItem Id="PizzaMenu1" Text="Chicken-Delite"&gt;

                            &lt;ContentSection&gt;

                                &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="chicken-delite"&gt;

                                &lt;div class="ingredients"&gt;

                                    Rate    : $100<br />

                                    Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.&lt;br /&gt;

                                    Description: This is a tasty, elegant chicken dish that is easy to prepare. 

                                &lt;/div&gt;

                            &lt;/ContentSection&gt;

                        &lt;/ej:TabItem&gt;

                    &lt;/Items&gt;

                &lt;/ej:Tab&gt;



            &lt;/ContentSection&gt;

        &lt;/ej:TabItem&gt;

&lt;!--Reuse remaining Tab contents--&gt;  

                &lt;/Items&gt;

            &lt;/ej:Tab&gt;

The following code example positions the image and content.

{% highlight css %}

            .ingredients {

            height: 180px;

            margin-top: 8px;

        }

        img {           

            float: left;        

            margin: 10px 26px 5px 1px;

        }





{% endhighlight %}

The following screenshot illustrates the first Tab with the sub Tab control.

{ ![](Getting-Started_images/Getting-Started_img5.png) | markdownify }
{:.image }


Orientation Change

The following gives details on how to set the sub Tab orientation to vertical. By default, Tab control is rendered in horizontal orientation. You can change this orientation to vertical by using the HeaderPosition property. The following code section sets the Tab header orientation as left and renders the sub Tab element in the vertical orientation.

{% highlight html %}

<!--Use the following codes with in the  above Html -->

<ej:Tab ID="DishType" runat="server" Width="500px">

    <Items>

        <ej:TabItem Id="PizzaType" Text="Pizza Menu">

            <ContentSection>

                <div>

                    Rating : 

                                 <div>

                                     <ej:Rating ID="gardenPizza" Precision="Exact" Value="4.9" runat="server"></ej:Rating>

                                 </div>

                </div>

                <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

                <ej:Tab ID="PizzaTab" runat="server" HeaderPosition="Left" Height="221px">

                    <Items>

                        <ej:TabItem Id="PizzaMenu" Text="Corn Spinach">

                            <ContentSection>

                                <img src=" http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png" alt="corn-spinach">

                                <div class="ingredients">

                                    Rate    : $70<br />

                                    Ingredients : cheese, sweet corn &amp; green capsicums.<br />

                                    Description: Small pizza bases are topped with spinach and paneer and fresh cream, a nice layer of mozzarella cheese. This is baked until the cheese is all hot and gooey.  

                                </div>

                            </ContentSection>

                        </ej:TabItem>

                        <ej:TabItem Id="PizzaMenu1" Text="Chicken-Delite">

                            <ContentSection>

                                <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png" alt="chicken-delite">

                                <div class="ingredients">

                                    Rate    : $100<br />

                                    Ingredients : cheese, chicken chunks, onions &amp; pineapple chunks.<br />

                                    Description: This is a tasty, elegant chicken dish that is easy to prepare. 

                                </div>

                            </ContentSection>

                        </ej:TabItem>

                    </Items>

                </ej:Tab>

            </ContentSection>

        </ej:TabItem>

<!--Reuse remaining Tab contents-->  

                </Items>

            </ej:Tab>



{% endhighlight %}

The following screenshot is the output of the above steps.

{ ![](Getting-Started_images/Getting-Started_img6.png) | markdownify }
{:.image }


Header Image Customization

In this application, the Tab header image is set for each Tab item to specify image in ImageCssClass property during the Tab header declaration time.

Use the following code example to customize the header image.

{% highlight css %}

.dish {

        display: inline-block;

        vertical-align: middle;

        margin: 0px -9px 0px 9px;

    }

    .pizzaImg {

        background: url("http://js.syncfusion.com/UG/Web/Content/rsz_chicken-delite.png") no-repeat;

        height: 25px;

        width: 25px;

    }

        /*reuse the previous code*/                





{% endhighlight %}

The following code example is used to add the header image for the root tab header element.

{% highlight html %}



<!--Use the following codes with in the  above Html --> 

<ej:TabItem Id="pizzaType" Text="Pizza Menu" ImageCssClass="dish pizzaImg">

                        <ContentSection>

                            <!—- reuse the previously defined first tab html content section-->

                        </ContentSection>

                    </ej:TabItem>

<!—- reuse the remaining tab contents -->

                </Items>

            </ej:Tab>   



{% endhighlight %}



The following screenshot illustrates the Tab with the customized header image.

{ ![](Getting-Started_images/Getting-Started_img7.png) | markdownify }
{:.image }


Configure contents to the remaining Tab items

The second and third Tab contents are declared in the same method the first Tab content declaration. These Tabs also consist of rating and sub Tab controls. Add the second Tab content with header image in the &lt;ej:Tab &gt; element during initialization.

&lt;!--Use the following codes with in the  above Html --&gt;                 

&lt;ej:TabItem Id="SandwichType" Text="Sandwich Menu" ImageCssClass="dish sandwichImg"&gt;

                        &lt;ContentSection&gt;

                            &lt;div&gt;

                                Rating : 

                                 &lt;div&gt;

                                     &lt;ej:Rating ID="RatingSandwich" Value="4.9" Precision="Exact" runat="server"&gt;&lt;/ej:Rating&gt;

                                 &lt;/div&gt;

                            &lt;/div&gt;

                            <p>Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.&lt;/p&gt;

                            &lt;ej:Tab ID="SandwichTab" runat="server" HeaderPosition="Left" Height="221px"&gt;

                                &lt;Items&gt;

                                    &lt;ej:TabItem Id="GardenVeggie" Text="Garden Veggie"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png" alt="garden-veggie "&gt;

                                            &lt;div class="ingredients"&gt;

                                                Rate    : $55<br />

                                                Ingredients : grilled chicken, corn &amp;olives.&lt;br /&gt;

                                                Description: To make an appetizer pizza made with crescent roll dough, baked and topped with flavored cream cheese and crispy fresh vegetables. Broccoli, carrots, and bell peppers make this a wonderfully delicious vegetarian treat 

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                    &lt;ej:TabItem Id="ChickenTikka" Text="Chicken Tikka"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-tikka.png" alt="chicken-tikka"&gt;

                                            &lt;div class="ingredients"&gt;

                                                Rate    : $100<br />

                                                Ingredients : onions, grilled chicken, chicken salami &amp; tomatoes.&lt;br /&gt;

                                                Description: Juicy chunks of boneless chicken roasted on open fire. This takeaway favourite is freezer-friendly and quick to reheat, giving you the chance to get ahead. 

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                    &lt;ej:TabItem Id="paneerTikka" Text="Paneer Tikka"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/paneer-tikka.png" alt="paneer-tikka"&gt;

                                            &lt;div class="ingredients"&gt;

                                                Rate    : $150

                                                &lt;br /&gt;

                                                Ingredients : onions, paneer & tomatoes.

                                                &lt;br /&gt;

                                                Description: Delve into the tasty Paneer Tikka Kebabs made from marinated paneer or cottage cubes. Relish these grilled delicacies with green mint chutney and onion rings. 

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                &lt;/Items&gt;

                            &lt;/ej:Tab&gt;

                        &lt;/ContentSection&gt;

                    &lt;/ej:TabItem&gt;

&lt;!--Reuse remaining Tab contents--&gt;  

                &lt;/Items&gt;

            &lt;/ej:Tab&gt;



Add the third Tab content with the header image in the &lt;ej:Tab &gt; element during initialization.

&lt;ej:TabItem Id="PastaType" Text="Pasta Menu" ImageCssClass="dish pastaImg"&gt;

                        &lt;ContentSection&gt;

                            &lt;div&gt;

                                Rating : 

                                 &lt;div&gt;

                                     &lt;ej:Rating ID="Rating1" Value="4.9" Precision="Exact" runat="server"&gt;&lt;/ej:Rating&gt;

                                 &lt;/div&gt;

                            &lt;/div&gt;

                            <p>Pasta cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.&lt;/p&gt;

                            &lt;ej:Tab ID="Tab2" runat="server" HeaderPosition="Left" Height="221px"&gt;

                                &lt;Items&gt;

                                    &lt;ej:TabItem Id="kheemaPasta" Text="Kheema Pasta"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach.png" alt="kheema-pasta "&gt;

                                            &lt;div class="ingredients"&gt;

                                                &lt;p&gt;

                                                    Rate : $30<br />

                                                    Ingredients : chicken, onions, chilly, garlic &amp; tomatoes.&lt;br /&gt;

                                                    Description: Kheema pasta dish make with veg or non-veg type.It is delicious and can be served for dinner, brunch or evening snack. 

                                                &lt;/p&gt;

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                    &lt;ej:TabItem Id="tunaPasta" Text="Tuna Pasta"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/garden-fresh.png" alt="tuna-pasta"&gt;

                                            &lt;div class="ingredients"&gt;

                                                &lt;p&gt;

                                                    Rate : $55<br />

                                                    Ingredients : tomato ,olive, oninor &amp;garlic.&lt;br /&gt;

                                                    Description: Canned tuna is used to make this yummy tomato sauce.

                                                &lt;/p&gt;

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                    &lt;ej:TabItem Id="channaPasta" Text="Channa Pasta"&gt;

                                        &lt;ContentSection&gt;

                                            &lt;img src="http://js.syncfusion.com/demos/web/images/accordion/zesty-mushroons-and-tomatoes.png" alt="channa-asta"&gt;

                                            &lt;div class="ingredients"&gt;

                                                &lt;p&gt;

                                                    Rate : $30<br />

                                                    Ingredients : sautered spinach mix, sweet corn, parsley &amp;mozarella cheese. .&lt;br /&gt;

                                                    Description: This is a pasta dish make with leftover channa masala (chole). This can be made from scratch too by making the channa masala first and then tossing in the cooked pasta.

                                                &lt;/p&gt;

                                            &lt;/div&gt;

                                        &lt;/ContentSection&gt;

                                    &lt;/ej:TabItem&gt;

                                &lt;/Items&gt;

                            &lt;/ej:Tab&gt;

                        &lt;/ContentSection&gt;

                    &lt;/ej:TabItem&gt;

&lt;!--Reuse remaining contents--&gt;  

                &lt;/Items&gt;

            &lt;/ej:Tab&gt;

Apply the following styles to the Tab.

        /*to reuse the previous style section code and following css*/        

       .sandwichImg, .pastaImg {

            height: 25px;

            width: 25px;

        }

        .sandwichImg {

            background: url("http://js.syncfusion.com/UG/Web/Content/rsz_garden-fresh.png") no-repeat;                       

        }

        .pastaImg {

            background: url("http://js.syncfusion.com/UG/Web/Content/rsz_garden-veggie.png") no-repeat;                 

        }      



The following screenshot illustrates the second Tab contents and the final hotel menu with rating, description, and ingredients of the item in the Tab interface.

{ ![](Getting-Started_images/Getting-Started_img8.png) | markdownify }
{:.image }


