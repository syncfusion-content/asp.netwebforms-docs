---
layout: post
title: Getting Started | NumericTextbox | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: NumericTextbox
documentation: ug
---

# Getting Started



## Create your first Editor in ASP.NET

The Essential ASP.NET Web Forms Editors control includes Numeric, Percentage, Currency and MaskEdit textbox controls. Here, you can learn how to use ASP.NET Textboxes controls in the Electricity bill calculator Application. This guides you to use the wide range of TextBox functionalities to complete this application.

![](Getting-Started_images/Getting-Started_img1.jpeg) 



## Create Textboxes Controls

You can create a Web Forms Project and add the necessary Dll’s and Scripts with the help of the given [Web Forms-Getting Started](http://help.syncfusion.com/aspnetmvc/numerictextbox/getting-started) Documentation.

Add necessary TextBox control and initialize the corresponding TextBox control.



{% highlight html %}



  <div class="editors">

        <div class="element-icon">

        </div>

        <div class="element-txt" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>

                        <%--  Simple numeric text box creation with watermark text--%>

                        <ej:NumericTextBox ID="NumericTextBox" runat="server"WatermarkText="Units">

                        </ej:NumericTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Service Tax</label>

                    </td>

                    <td>

                        <%--  Percentage text box creation with watermark text --%>

                        <ej:PercentageTextBox ID="PercentageTextBox" runat="server"WatermarkText="Tax">

                        </ej:PercentageTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>

                        <%-- Simple currency text box creation with watermark text --%>

                        <ej:CurrencyTextBox ID="CurrencyTextBox" runat="server"WatermarkText="Amount perunit">

                        </ej:CurrencyTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>

                        <%-- Mask Edit text box creation with watermark text --%>

                 <ej:MaskEdit ID="MaskEdit" runat="server" WatermarkText="Phone number">

                        </ej:MaskEdit>

                    </td>

                </tr>

            </tbody>

        </table>

        <div class="pay-bill">

           <ej:Button ID="Button" runat="server" Text="Calculate" Type="Button"Size="Small">

            </ej:Button>

        </div>

    </div>





{% endhighlight %}



The following styles are added to arrange the TextBox.



{% highlight css %}

        .element-txt

        {

            display: inline-block;

            font-size: 20px;

            font-weight: bolder;

            height: 50px;

            position: relative;

            text-align: center;

            top: -20px;

        }

        .editors

        {

            max-width: 400px;

            border: 2px solid #DDDDDD;

            margin:100px 0 0 100px;

        }

        .editors td

        {

            padding-bottom:5px;

        }



        .editors table

        {

            border: 0px;

            padding-left: 50px;

        }

        .pay-bill

        {

            margin: 18px 0px 10px 244px;

        }

        table.editors

        {

            margin:0 0 0 61px;

        }

        .editors label

        {

            display: block;

            width: 130px;

        } 



{% endhighlight %}



Run the above code to render a TextBox control as follows

![](Getting-Started_images/Getting-Started_img2.jpeg)



## Set the MinValue, MaxValue and value in Textboxes

In the above mentioned use case scenario, you can set the MinValue, MaxValue and Value in Numeric, percentage and Currency TextBox for maintaining the range in TextBox controls. You can also enter the values between the ranges that are set as default. You can get the phone number from the user in the MaskEdit control by using the MaskFormat property. You can get the decimal values for CurrencyTextBox control by using the DecimalPlaces property. The following code example illustrates how to achieve this scenario.



{% highlight html %}

   <div class="editors">

        <div class="element-icon">

        </div>

        <div class="element-txt" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>

                        <ej:NumericTextBox ID="NumericTextBox" runat="server"WatermarkText="Units" MinValue="1" MaxValue="10000" Value="70">

                        </ej:NumericTextBox>

                    </td>

                </tr>

                <tr><td><label>Service Tax</label>

                    </td>

                    <td>

                        <ej:PercentageTextBox ID="PercentageTextBox" runat="server"WatermarkText="Tax" MinValue="5" MaxValue="100" Value="3">

                        </ej:PercentageTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>

                        <ej:CurrencyTextBox ID="CurrencyTextBox" runat="server"WatermarkText="Amount per unit" DecimalPlaces="2" MinValue="0.00"MaxValue="100000.00" Value="350.00">

                        </ej:CurrencyTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>

                        <ej:MaskEdit ID="MaskEdit" runat="server"WatermarkText="Phone number" MaskFormat="99-999-99999" Value="9090909090">

                        </ej:MaskEdit>

                    </td>

                </tr>

            </tbody>

        </table>

        <div class="pay-bill">

            <ej:Button ID="Button" runat="server" Text="Calculate" Type="Button"Size="Small">

            </ej:Button>

        </div>

    </div>



{% endhighlight %}

Run the above code to render the resultant output of the above steps

![](Getting-Started_images/Getting-Started_img3.jpeg) 



## Set the Strict Mode Option

You can set the “EnableStrictMode” option to restrict entering values defined outside the range. The following code example illustrates how to set strict mode option.



{% highlight html %}

   <div class="editors">

        </div>

        <div class="element-txt" style="">Electricity Bill Calculator</div>

        <br />

        <table class="editors">

            <tbody>

                <tr>

                    <td>

                        <label>Unit meters</label>

                    </td>

                    <td>

                        <ej:NumericTextBox ID="NumericTextBox" runat="server"WatermarkText="Units" MinValue="1" MaxValue="10000" Value="70"EnableStrictMode="true">

                        </ej:NumericTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Service Tax</label>

                    </td>

                    <td>

                        <ej:PercentageTextBox ID="PercentageTextBox" runat="server"WatermarkText="Tax" MinValue="5" MaxValue="100" Value="3">

                        </ej:PercentageTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Fare</label>

                    </td>

                    <td>

                        <ej:CurrencyTextBox ID="CurrencyTextBox" runat="server"WatermarkText="Amount per unit" DecimalPlaces="2" MinValue="0.00"MaxValue="100000.00" Value="350.00">

                        </ej:CurrencyTextBox>

                    </td>

                </tr>

                <tr>

                    <td>

                        <label>Mobile No</label>

                    </td>

                    <td>

                        <ej:MaskEdit ID="MaskEdit" runat="server"WatermarkText="Phone number" MaskFormat="99-999-99999" Value="9090909090">

                        </ej:MaskEdit>

                    </td>

                </tr>

            </tbody>

        </table>

        <div class="pay-bill">

            <ej:Button ID="Button" runat="server" Text="Calculate" Type="Button"Size="Small">

            </ej:Button>

        </div>

    </div>



{% endhighlight %}



Run the above code example and you can see that it restricts entering a value exceeding the MinValue and MaxValue range mentioned in the NumericTextBox.

## Set Calculation process with TextBox Control

You can use events to calculate the total amount and display the value. This is achieved by using the Click event in the button control. The calculation steps are written in the call back function of Click event button.

To customize the button, you can set the ContentType as TextAndImage to include the icon before the text and add the ClientSideOnClick event.

{% tabs %}

{% highlight html %}

  <div class="editors">

        // Please refer the table format for textboxes customization

  <div class="pay-bill">

            <ej:Button ID="Button" runat="server" Text="Calculate" Type="Button"Size="Small"ClientSideOnClick="calculateBill">

            </ej:Button>

        </div>



    </div>



{% endhighlight %}



{% highlight js %}

        function calculateBill() {

             // Declares Necessary variable creation

        var unitMeter, serviceTax, amountPerKm;

        unitMeter = $("#NumericTextBox").data("ejNumericTextbox");// Object of Numeric

        serviceTax = $("#PercentageTextBox").data("ejPercentageTextbox");// Object of Percentage

        amountPerKm = $("#CurrencyTextBox").data("ejCurrencyTextbox"); // Object of Currency

        mobileNumber = $("#MaskEdit").data("ejMaskEdit"); // Object of MaskEdit       

         // This is used to calculate the Net amount

        var netAmount = unitMeter.model.value * amountPerKm.model.value;

        // This is used to calculate the service tax amount

        var sTax = (netAmount * serviceTax.model.value) / 100;

        // This shows the calculated amount for the units

        alert("The amount $" + (netAmount + sTax) + " has been sent as message to " + mobileNumber.model.value + ".");

    } 





{% endhighlight %}

{% endtabs %}

Run the above code to render the TextBox control. Fill the required Textbox fields and click the Calculate button. The values are displayed and an alert message is shown. The following screenshot illustrates the final output of the Electricity bill calculator.

![](Getting-Started_images/Getting-Started_img4.jpeg) 



