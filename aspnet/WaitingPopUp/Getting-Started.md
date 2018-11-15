---
layout: post
title: Getting Started | WaitingPopup | ASP.NET | Syncfusion
description: getting started
platform: aspnet
control: WaitingPopup
documentation: ug
---

# Getting Started

## Create your first Waiting Popup in ASP.NET  

Essential ASP.NET Waiting Popup provides support to display a Waiting Popup within your web page. From the following guidelines, you can learn how to create a Waiting Popup in the real-time login page authentication scenario.

The following screenshot illustrates the functionality of a Waiting Popup with login page scenario.

![WaitingPopup](Getting-Started_images/Getting-Started_img1.jpeg) 



You can give the Username and Password in the login page. When you click the Login button, you get the Waiting Popup. After loading, the alert box pops up with the message Signed in successfully.

### Create Waiting Popup

You can create a WEB Project and add the necessary assemblies, styles, and scripts with the help of [ASP-Getting Started](http://help.syncfusion.com/aspnetmvc/captcha/getting-started#create-your-first-captcha-in-aspnet-mvc) Documentation.

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

                            <input type="text" runat="server">

                        </td>

                    </tr>

                    <tr>

                        <td>

                            Password

                        </td>

                        <td>

                            <input type="password" runat="server">

                        </td>

                    </tr>

                    <tr>

                        <td>

                        </td>

                        <td>

                            <ej:Button ID="buttonnormal" runat="server" Type="Button" Text="login" Size="Large"

                                ShowRoundedCorner="true" ClientSideOnClick="btnClick">

                            </ej:Button>

                        </td>

                        <ej:WaitingPopup ID="target" runat="server" ShowOnInit="false">

                        </ej:WaitingPopup>

                    </tr>

                </table>

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

The following screenshot displays the User login.

 ![](Getting-Started_images/Getting-Started_img2.png) 



### Add Waiting Popup Widget

In a real-time login page scenario, when you click the Login button, the Waiting Popup is displayed.

{% highlight js %}

 <script type="text/javascript">

        function btnClick(e) {

            var popup = $("#<%=target.ClientID%>").data("ejWaitingPopup");

            popup.show();

            setTimeout(success, 5000);

        }

        function success() {

            alert("Signed in successfully");

           $("#<%=target.ClientID%>").ejWaitingPopup("hide");

        }

</script>

{% endhighlight %}



The following screenshot shows the output of the code example.

 ![WaitingPopup](Getting-Started_images/Getting-Started_img3.png) 



The following screenshot displays an alert box displayed with the message signed in successfully after loading.

![Alert](Getting-Started_images/Getting-Started_img4.jpeg) 



