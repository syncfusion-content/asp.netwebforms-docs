---
layout: post
title: Appearance-and-Styling
description: appearance and styling
platform: aspnet
control: Menu
documentation: ug
---

## Appearance and Styling

### Theme

Essential Studio ASP.NET controls feature 13 built-in themes, six flat and gradient effects, and also supports custom skin options for user-defined themes.

13 themes support available for menu control namely,

* default-theme
* flat-azure-dark
* flat-lime
* flat-lime-dark
* flat-saffron
* flat-saffron-dark
* gradient-azure
* gradient-azure-dark
* gradient-lime
* gradient-lime-dark
* gradient-saffron
* gradient-saffron-dark
* bootstrap-theme
### CssClass


Menu control also customizes its appearance by using user-defined CSS and custom skin options (colors and backgrounds). To apply custom themes, “CssClass” property is used. “CssClass” property sets the root class for Menu control theme.

By using CssClass you can override the existing styles under the theme style sheet. The theme stylesheet applies theme-specific styles like colors and backgrounds. In the following code example, the value of “CssClass” property is set as “Purple-dark”. Purple-dark is added as root class to Menu control at the runtime. From this root class you can customize the Menu control theme.

Add the following code in your ASPX page.

{% highlight html %}



        <ej:Menu ID="MenuControl" Width="500" CssClass="Purple-dark" runat="server">

            <Items>

                <ej:MenuItem Id="Home" Text="Home">

                    <Items>

                        <ej:MenuItem Text="Foundation"></ej:MenuItem>

                    </Items>

                    <Items>

                        <ej:MenuItem Text="Launch"></ej:MenuItem>

                    </Items>

                    <Items>

                        <ej:MenuItem Text="About">

                            <Items>

                                <ej:MenuItem Text="Company"></ej:MenuItem>

                            </Items>

                            <Items>

                                <ej:MenuItem Text="Location"></ej:MenuItem>

                            </Items>

                        </ej:MenuItem>

                    </Items>



                </ej:MenuItem>

                <ej:MenuItem Id="Services" Text="Services">

                    <Items>

                        <ej:MenuItem Text="Consulting"></ej:MenuItem>

                    </Items>

                    <Items>

                        <ej:MenuItem Text="Outsourcing"></ej:MenuItem>

                    </Items>

                </ej:MenuItem>

                <ej:MenuItem Id="About" Text="About"></ej:MenuItem>

                <ej:MenuItem Id="Contact" Text="Contact us">

                    <Items>

                        <ej:MenuItem Text="Contact Number"></ej:MenuItem>

                    </Items>

                    <Items>

                        <ej:MenuItem Text="Email"></ej:MenuItem>

                    </Items>

                </ej:MenuItem>

                <ej:MenuItem Id="Careers" Text="Careers">

                    <Items>

                        <ej:MenuItem Text="Position">

                            <Items>

                                <ej:MenuItem Text="Developer"></ej:MenuItem>

                            </Items>

                            <Items>

                                <ej:MenuItem Text="Manager"></ej:MenuItem>

                            </Items>

                        </ej:MenuItem>

                    </Items>

                    <Items>

                        <ej:MenuItem Text="Apply online"></ej:MenuItem>

                    </Items>

                </ej:MenuItem>

            </Items>

        </ej:Menu>





{% endhighlight %}



Add the following code in your style section.

{% highlight css %}

    .Purple-dark {

        background: pink;

    }



    .Purple-dark.e-horizontal .e-list > a {

            color: #4800ff;

     }





{% endhighlight %}



Following screenshot displays the output of the above code example.

{ ![](Appearance-and-Styling_images/Appearance-and-Styling_img1.png) | markdownify }
{:.image }


### Background Template

Menu control also provide the support for template support. Normally menu control can be created by using UL and LI tags in the preferred way. In template supporting, you can customize the appearance of sub menu items rendering. 

Initialize the Template Menu as illustrated in the following code example. 

Add the following code example in your ASPX page.

{% highlight html %}



<ej:Menu ID="template" runat="server">

        <Items>

            <ej:MenuItem Text="My Computer">

                <Items>

                    <ej:MenuItem Text="Child1">

                        <Template>

                            <div class="temp temp1">

                                <span>Disks</span>

                                <ul>

                                    <li><a>Local Disk : C</a></li>

                                    <li><a>Local Disk : D</a></li>

                                </ul>

                                <ul>

                                    <li><a>Local Disk : E</a></li>

                                    <li><a>Local Disk : F</a></li>

                                </ul>

                            </div>

                        </Template>

                    </ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Text="Libraries">

                <Items>

                    <ej:MenuItem Text="Child1">

                        <Template>



                            <div class=" temp temp2">

                                <div>

                                    <span>Documents</span>

                                    <ul>

                                        <li><a>Images</a></li>

                                        <li><a>Videos</a></li>

                                    </ul>

                                    <ul>

                                        <li><a>Documents</a></li>

                                        <li><a>Music</a></li>

                                    </ul>

                                </div>

                            </div>



                        </Template>

                    </ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Text="Favourites">

                <Items>

                    <ej:MenuItem Text="Child1">

                        <Template>



                            <div class="temp temp3">

                                <div>

                                    <span>Favourites</span>

                                    <ul>

                                        <li><a>Download</a></li>

                                        <li><a>Recent Places</a></li>

                                    </ul>

                                    <ul>

                                        <li><a>Desktop</a></li>

                                    </ul>

                                </div>

                            </div>



                        </Template>

                    </ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Text="Gaming">

                <Items>

                    <ej:MenuItem Text="Child1">

                        <Template>



                            <div class=" temp temp2">

                                <div>

                                    <span>GAMING</span>

                                    <ul>

                                        <li><a>Upcoming</a></li>

                                        <li><a>Consoles</a></li>

                                    </ul>

                                    <ul>

                                        <li><a>FIFA 2999</a></li>

                                        <li><a>Carom legend</a></li>

                                    </ul>

                                </div>

                            </div>



                        </Template>

                    </ej:MenuItem>

                </Items>

            </ej:MenuItem>

        </Items>

    </ej:Menu>



{% endhighlight %}



Add the following code example in your style section

{% highlight css %}



    .temp {

        height: 237px;

        width: 375px;

        font-family: segoe UI;

        cursor: default;

        background-size: 100% 100%;

    }



        .temp span {

            color: red;

            float: left;

            font-size: 20px;

            left: 20px;

            position: relative;

            top: 25px;

            width: 100px;

        }



        .temp ul {

            float: left;

            font-size: 14px;

            left: -79px;

            list-style-type: none;

            margin: 0;

            padding: 0;

            position: relative;

            top: 50px;

            width: 128px;

        }



            .temp ul li {

                font-size: 13px;

            }



                .temp ul li a {

                    text-decoration: underline;

                    cursor: pointer;

                    color: #000;

                }



    .temp1 {

        background-image: url("1.jpg");

    }



    .temp2 {

        background-image: url("2.jpg");

    }



    .temp3 {

        background-image: url("3.jpg");

    }



    .temp4 {

        background-image: url("4.jpg");

    }



    .e-menu.e-horizontal li > ul, .e-menu.e-horizontal li > ul > li:hover {

        background-color: #fff;

    }



    .e-menu.e-horizontal > li > ul:after {

        border-color: transparent transparent #fff;

    }





{% endhighlight %}



Execute the above code example to render the following output.                       

{ ![](Appearance-and-Styling_images/Appearance-and-Styling_img2.png) | markdownify }
{:.image }


