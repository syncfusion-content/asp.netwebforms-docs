---
layout: post
title: Getting Started | Captcha | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Captcha
documentation: ug
---

# Getting Started

## Create your first Captcha in ASP.NET 

This section enables you to configure the Captcha control in your ASP.NET WEB application and also in learning how to use Captcha with auto validation in Web Forms.

![](Getting-Started_images/Getting-Started_img1.png)


### Create Captcha Control

The Captcha is one of the ways to prevent dictionary attacks. It basically comes with the random text. 

The following steps are used to create the Captcha control.  

You can create a Web Project and add necessary assembly and script with the given [ASP-Getting Started Documentation](http://help.syncfusion.com/aspnet/captcha/getting-started).



Add the following code to the corresponding ASPX page for Captcha rendering.



{% highlight html %}

    <ej:Captcha ID="SignUpCaptcha" runat="server"></ej:Captcha>

{% endhighlight %}



Add the following handler codes to the web.config file for the Captcha rendering.



{% highlight html %}



<!--Add the following code in <system.web>-->

 <system.web>

    <httpHandlers>

      <add verb="*" path="captimage.axd" type="Syncfusion.JavaScript.ImageHandler, Syncfusion.EJ, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3D67ED1F87D44C89" />

    </httpHandlers>

</system.web>

<!--Add the following code in <system.webserver>-->

<system.webserver>    

-----------------------

-----------------------

    <handlers>      

      <add verb="*" path="captimage.axd" name="syncfusion_generatetools" type="Syncfusion.JavaScript.ImageHandler, Syncfusion.EJ, Version= {{ site.45esreleaseversion }}, Culture=neutral, PublicKeyToken=3d67ed1f87d44c89" />      

    </handlers>
    
    <validation validateIntegratedModeConfiguration="false"/>

</system.webserver>

{% endhighlight %}


N> Version= {{ site.45esreleaseversion }}  - It will vary depend up on .NET Framework version and Essential Studio version you are using. If you are using Essential Studio version as- {{ site.releaseversion }} and .NET Framework is 4.5 use like following Version= {{ site.45esreleaseversion }}



The following screenshot displays the output of the above codes.

![](Getting-Started_images/Getting-Started_img2.png)


### Show AudioButton and Refresh

The Captcha control supports captcha in the form of audio. When you click the audio button, it readouts the captcha characters. You can achieve this by setting the ShowAudioButton property to true. ShowRefreshButton is used to refresh or change the captcha image without full page refresh. This is achieved by adding the ShowRefreshButton property to true. Also include Mapper to refresh support.

Add the following code example to ASPX to render captcha with Audio and Refresh.

{% highlight html %}



<ej:Captcha ID="SignUpCaptcha" ShowAudioButton="true" ShowRefreshButton="true" Mapper="Refresh"runat="server"></ej:Captcha>





{% endhighlight %}



Add the following code example to the corresponding CS page to render Captcha with Audio and Refresh.

This method is used to handle AJAX post when refresh and validation actions are performed. When these actions are performed, the following values are received from client-side by AJAX post and the values are forwarded to source to perform the corresponding action. The following values are required to perform validation and refresh action.

{% highlight c# %}

    public static string GetCurrentItem(Dictionary<object, object> captchaModel)

    {

        return Syncfusion.JavaScript.Web.Captcha.GetModel(captchaModel).ExecuteResult();

    }


{% endhighlight %}



The following screenshot displays the output of the above codes.

![](Getting-Started_images/Getting-Started_img3.png)


### Auto Validation   

The Captcha supports automatic validation by enabling the property EnableAutoValidation. When this property is set to true, captcha validation is done automatically. When the validation fails, CustomErrorMessage property supports to display the customized error message.

Add the following code example to ASPX page for auto validation.

{% highlight html %}



<div class="frame" style="width: 500px">

    <div class="control">

        <table class="tabprop">

            <h1>Sign Up </h1>

            <tr>

                <td><span class="NodeText">Enter Name</span>

                </td>

                <td>

                    <asp:textbox id="Name" runat="server"></asp:textbox>



                    <span id="Uname" runat="server" style="color: red; display: block; width: 200px;float: right"></span>



                </td>

            </tr>

            <tr>

                <td><span class="NodeText" style="width: 200px">Email</span>

                </td>

                <td>

                    <asp:textbox id="Email" textmode="Email" runat="server"></asp:textbox>



                    <span id="Emailid" runat="server" style="color: red; width: 200px; display: block;float: right"></span>

                </td>

            </tr>

            <tr>

                <td><span class="NodeText" style="width: 200px">Enter Password</span>

                </td>

                <td>

                    <asp:textbox id="Password" textmode="Password" runat="server"></asp:textbox>



                    <span id="Pwd" runat="server" style="color: red; width: 200px; display: block;float: right"></span>

                </td>

            </tr>

            <tr>

                <td><span runat="server" class="NodeText">Re-Enter Password</span>

                </td>

                <td>

                    <asp:textbox id="RePassword" textmode="Password" runat="server"></asp:textbox>

                    <span id="RePwd" runat="server" style="color: red; width: 200px; display: block;float: right"></span>

                </td>

            </tr>



            <tr>

                <td></td>

                <td>

                    <div style="width: 185px;">

                        <ej:captcha id="SignUpCaptcha" ShowAudioButton="true" ShowRefreshButton="true" mapper="Refresh" EnableAutoValidation="true" CustomErrorMessage="InValid Captcha code entered.Please try again" targetbutton="btnSubmit" runat="server"></ej:captcha>

                    </div>

                </td>

            </tr>

            <tr style="height: 30px; display: block">

                <td></td>

                <td></td>

            </tr>

            <tr>

                <td></td>

                <td>

                    <ej:button id="btnSubmit" runat="server" text="submit" size="Large" type="Button" ClientSideOnClick="onValidate"></ej:button>

                </td>

            </tr>

        </table>

    </div>

</div>



{% endhighlight %}



Add the following code example to ASPX to render Captcha with Audio and Refresh.

{% highlight js %}



  <script type="text/javascript">

    function onValidate(args) {

        var name = $("#<%= Name.ClientID %>").val();

         var email = $("#<%= Emailid.ClientID %>").val();

         var password = $("#<%= Password.ClientID %>").val();

         var rePassword = $("#<%= RePassword.ClientID %>").val();

         var value = $("#myCaptcha_CaptchaMessage")[0].innerHTML;

         var UserNameStatus;

         var PasswordStatus;

         if (name == "")

             $("#<%= Uname.ClientID %>").html("Name required");

            else

                UserNameStatus = true;

            if (email == "")

                $("#<%= Emailid.ClientID %>").html("Email required");

            if (password == "")

                $("#<%= Pwd.ClientID %>").html("Password required");

            if (rePassword == "")

                $("#<%= RePwd.ClientID %>").html("Re-Enter Password required");



            if (password != rePassword)

                $("#<%= Pwd.ClientID %>").html("Invalid password");

            else

                PasswordStatus = true;



            if (UserNameStatus && PasswordStatus && !(password == "") && (value != "InValid Captcha code entered.Please try again")) {

                alert("Thank you for registering");

                $("#<%= Uname.ClientID %>").html("");

                $("#<%= Emailid.ClientID %>").html("");

                $("#<%= Pwd.ClientID %>").html("");

                $("#<%= RePwd.ClientID %>").html("");

                $("#<%= Name.ClientID %>").val("");

            }

        }

</script>





{% endhighlight %}



Add the following code example to ASPX to render Captcha with Audio and Refresh.

{% highlight css %}



<style>

    .NodeText {

        color: black;

        font-size: 15px;

        font-weight: bold;

    }



    .tabprop {

        width: 500px;

        height: 275px;

        margin-left: 25px;

    }



</style>



{% endhighlight %}



Add the following code example to the corresponding CS page for Captcha with Auto-Validation support.

{% highlight c# %}



    [System.Web.Services.WebMethod]

    public static string Refresh(Dictionary<object, object> captchaModel)

    {	

        return Syncfusion.JavaScript.Web.Captcha.GetModel(captchaModel).ExecuteResult();

    }





{% endhighlight %}



The following screenshot is the output for the above code example.

![](Getting-Started_images/Getting-Started_img4.jpeg)


