---
layout: post
title: Getting Started | Tab | ASP.NET | Syncfusion
description: getting started 
platform: aspnet
control: Tab
documentation: ug
---

# Getting Started 

This section explains briefly how to create a Tab Control in your application with ASP.NET.

## Create your first Tab control in ASP.NET	

The ASP.NET Tab control is an interface that displays the content in multiple sections. Each TabPanel consists of HeaderText or HeaderTemplate as well as a ContentTemplate. Tab is useful for a dashboard that contains limited space. The following section guides you to customize the Tab for displaying Hotel menu items, its rating details, and ingredients.

![](Getting-Started_images/Getting-Started_img1.png) 


### Create Tab control

You can create an ASP Project and add the necessary assembly and scripts with the help of the given [ASP-Getting Started](http://help.syncfusion.com/aspnetmvc/captcha/getting-started#create-your-first-captcha-in-aspnet-mvc) Documentation.

Add the following code example to the corresponding ASP page for Tab rendering.

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



![](Getting-Started_images/Getting-Started_img2.png)



### Configure content

In this application, a detailed description is provided to each item. You can specify the contents in the Tab section within the <ContentSection > by using the following format. 

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

![](Getting-Started_images/Getting-Started_img3.png) 



### Create the rating in the Tab

The ASP.NET Rating control provides an intuitive rating experience that allows you to select the number of stars that represents the rating. The following code example explains he rating control creation. Render the rating control by using the <ej:Rating> tag. The code example is placed within the content description( <ContentSection > ) element to declare the rating control and description in the Tab section and it can be appended with the control initialization code section <ej:Tab> element by using the following format.

{% highlight html %}

<ej:Tab ID="DishType" runat="server" Width="500px">

    <Items>

        <ej:TabItem Id="PizzaType" Text="Pizza Menu">

            <ContentSection>

                <div>

                    Rating : 

                     <div>                                     
                     
                         <ej:Rating ID="GardenPizza" Precision="Exact" Value="4.9" runat="server"></ej:Rating>

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

 ![](Getting-Started_images/Getting-Started_img4.png) 



### Sub Tab with content 

Each item has a variety of options and these options are also specified in the limited space. So, you can choose the Tab control that is used within the root Tab to specify more details.

The following code example illustrates how to create the Tab control within the root Tab element. This HTML code is appended within the previous HTML code section. To render the child Tab with its header, add this code example within the <ej:Tab > tag by using the following format.

The sub Tab control rendering is represented in the following code example.

<!--Use the following codes with in the  above Html -->

{% highlight html %}

<ej:Tab ID="DishType" runat="server" Width="500px">

    <Items>

        <ej:TabItem Id="PizzaType" Text="Pizza Menu">

            <ContentSection>

                <div>

                    Rating : 

                    <div>

                         <ej:Rating ID="GardenPizza" Precision="Exact" Value="4.9" runat="server"></ej:Rating>

                    </div>

                </div>

                <p>Pizza cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

                <ej:Tab ID="PizzaTab" runat="server">

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

![](Getting-Started_images/Getting-Started_img5.png) 



#### Orientation Change

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

![](Getting-Started_images/Getting-Started_img6.png) 



### Header Image Customization

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

![](Getting-Started_images/Getting-Started_img7.png) 



Configure contents to the remaining Tab items

The second and third Tab contents are declared in the same method the first Tab content declaration. These Tabs also consist of rating and sub Tab controls. Add the second Tab content with header image in the <ej:Tab > element during initialization.

<!--Use the following codes with in the  above Html -->                 

{% highlight html %}

<ej:TabItem Id="SandwichType" Text="Sandwich Menu" ImageCssClass="dish sandwichImg">

    <ContentSection>

        <div>

             Rating : 

             <div>

                 <ej:Rating ID="RatingSandwich" Value="4.9" Precision="Exact" runat="server"></ej:Rating>

             </div>

        </div>

        <p>Sandwich cooked to perfection tossed with bread, milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

        <ej:Tab ID="SandwichTab" runat="server" HeaderPosition="Left" Height="221px">

            <Items>

                <ej:TabItem Id="GardenVeggie" Text="Garden Veggie">

                    <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png" alt="garden-veggie ">

                        <div class="ingredients">

                            Rate    : $55<br />

                            Ingredients : grilled chicken, corn &amp;olives.<br />

                            Description: To make an appetizer pizza made with crescent roll dough, baked and topped with flavored cream cheese and crispy fresh vegetables. Broccoli, carrots, and bell peppers make this a wonderfully delicious vegetarian treat 

                        </div>

                    </ContentSection>

                </ej:TabItem>

                <ej:TabItem Id="ChickenTikka" Text="Chicken Tikka">

                    <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/chicken-tikka.png" alt="chicken-tikka">

                        <div class="ingredients">

                            Rate    : $100<br />

                            Ingredients : onions, grilled chicken, chicken salami &amp; tomatoes.<br />

                            Description: Juicy chunks of boneless chicken roasted on open fire. This takeaway favorite is freezer-friendly and quick to reheat, giving you the chance to get ahead. 

                        </div>

                    </ContentSection>

                </ej:TabItem>

                <ej:TabItem Id="paneerTikka" Text="Paneer Tikka">

                   <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/paneer-tikka.png" alt="Paneer-tikka">

                        <div class="ingredients">

                            Rate    : $150

                            <br />

                            Ingredients : onions, paneer & tomatoes.

                            <br />

                            Description: Delve into the tasty Paneer Tikka Kebabs made from marinated Paneer or cottage cubes. Relish these grilled delicacies with green mint chutney and onion rings. 

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


Add the third Tab content with the header image in the <ej:Tab > element during initialization.

{% highlight html%}

<ej:TabItem Id="PastaType" Text="Pasta Menu" ImageCssClass="dish pastaImg">

    <ContentSection>

        <div>

            Rating : 

             <div>

                 <ej:Rating ID="Rating1" Value="4.9" Precision="Exact" runat="server"></ej:Rating>

             </div>

        </div>

        <p>Pasta cooked to perfection tossed with milk, vegetables, potatoes, poultry, 100% pure mutton, and cheese - and in creating nutritious and tasty meals to maintain good health.</p>

        <ej:Tab ID="Tab2" runat="server" HeaderPosition="Left" Height="221px">

            <Items>

                <ej:TabItem Id="kheemaPasta" Text="Kheema Pasta">

                    <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach.png" alt="kheema-pasta ">

                        <div class="ingredients">

                            <p>

                                Rate : $30<br />

                                Ingredients : chicken, onions, chilly, garlic &amp; tomatoes.<br />

                                Description: Kheema pasta dish make with veg or non-veg type.It is delicious and can be served for dinner, brunch or evening snack. 

                            </p>

                        </div>

                    </ContentSection>

                </ej:TabItem>

                <ej:TabItem Id="tunaPasta" Text="Tuna Pasta">

                    <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/garden-fresh.png" alt="tuna-pasta">

                        <div class="ingredients">

                            <p>

                                Rate : $55<br />

                                Ingredients : tomato ,olive, onion &amp;garlic.<br />

                                Description: Canned tuna is used to make this yummy tomato sauce.

                            </p>

                        </div>

                    </ContentSection>

                </ej:TabItem>

                <ej:TabItem Id="channaPasta" Text="Channa Pasta">

                    <ContentSection>

                        <img src="http://js.syncfusion.com/demos/web/images/accordion/zesty-mushroons-and-tomatoes.png" alt="channa-asta">

                        <div class="ingredients">

                            <p>

                                Rate : $30<br />

                                Ingredients : sauntered spinach mix, sweet corn, parsley &amp;mozzarella cheese. .<br />

                                Description: This is a pasta dish make with leftover Channa masala (choler). This can be made from scratch too by making the Channa masala first and then tossing in the cooked pasta.

                            </p>

                        </div>

                    </ContentSection>

                </ej:TabItem>

            </Items>

        </ej:Tab>

    </ContentSection>

</ej:TabItem>

<!--Reuse remaining contents-->  

	</Items>

</ej:Tab>

{% endhighlight %}

Apply the following styles to the Tab.

{% highlight css %}

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

{% endhighlight %}

The following screenshot illustrates the second Tab contents and the final hotel menu with rating, description, and ingredients of the item in the Tab interface.

 ![](Getting-Started_images/Getting-Started_img8.png) 



