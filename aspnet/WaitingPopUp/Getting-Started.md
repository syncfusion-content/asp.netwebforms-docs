---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: WaitingPopup
documentation: ug
---

# Getting Started

## Create your first Waiting Popup in ASP.NET  

Essential ASP.NET Waiting Popup provides support to display a Waiting Popup within your webpage. From the following guidelines, you can learn how to create a Waiting Popup in the real-time login page authentication scenario.

The following screenshot illustrates the functionality of a Waiting Popup with login page scenario.

![http://help.syncfusion.com/ug/js/ImagesExt/image17_7.jpg](Getting-Started_images/Getting-Started_img1.jpeg) 



You can give the Username and Password in the login page. When you click the Login button, you get the Waiting Popup. After loading, the alert box pops up with the message Signed in successfully.

### Create Waiting Popup

You can create a WEB Project and add the necessary assemblies, styles, and scripts with the help of [ASP-Getting Started](http://help.syncfusion.com/ug/js/Documents/gettingstartedwithmv.htm) Documentation.

 Create an aspx page and add the following code to the aspx file.

{% highlight html %}

<div class="content-container-fluid">

        <div class="row">

            <div class="cols-sample-area">

                <table>

                    <tr>

                        <td>

                            Username

                        </td>

                        <td>

                            <input type="text">

                        </td>

                    </tr>

                    <tr>

                        <td>

                            Password

                        </td>

                        <td>

                            <input type="password">

                        </td>

                    </tr>

                    <tr>

                        <td>

                        </td>

                        <td>

                            <ej:Button ID="buttonnormal" runat="server"Type="Button" Text="login" Size="Large"

                                ShowRoundedCorner="true"ClientSideOnClick="btnClick">

                            </ej:Button>

                        </td>

                        <ej:WaitingPopup ID="target" runat="server"ShowOnInit="false">

                        </ej:WaitingPopup>

                    </tr>

                </table>

                <div id="target" class="targetpostion">

                </div>

            </div>

        </div>

    </div>



{% endhighlight %}

 Add the following styles in the aspx page to show the Waiting Popup.



{% highlight css %}

<style type="text/css" class="cssStyles">

        .content-container-fluid

        {

            margin: 100px 10px 10px 100px;

        }



        #target_WaitingPopup .e-image

        {

            display: block;

            height: 70px;

            top: 120px !important;

        }

    </style>



{% endhighlight %}

The following screenshot displays the Userlogin.

 ![http://help.syncfusion.com/ug/js/ImagesExt/image17_8.png](Getting-Started_images/Getting-Started_img2.png) 



### Add Waiting Popup Widget

In a real-time login page scenario, when you click the Login button, the Waiting Popup is displayed.

{% highlight js %}

 <script type="text/javascript">

        function btnClick(e) {

            var wp = $("#target").data("ejWaitingPopup");

            wp.show();

            setTimeout(success, 5000);

        }

        function success() {

            alert("Signed in successfully");

            $("#target").ejWaitingPopup("hide");

        }

    </script>





{% endhighlight %}



The following screenshot shows the output of the code example.

 ![http://help.syncfusion.com/ug/js/ImagesExt/image17_9.png](Getting-Started_images/Getting-Started_img3.png) 



The following screenshot displays an alert box displayed with the message signed in successfully after loading.

![http://help.syncfusion.com/ug/js/ImagesExt/image17_10.jpg](Getting-Started_images/Getting-Started_img4.jpeg) 



