---
layout: post
title: Configure Persistence in ASP.NET Webforms MaskEdit Control| Syncfusion
description: Learn here about configure persistence support in Syncfusion Essential ASP.NET Webforms MaskEdit Control, its elements, and more.
platform: aspnet
control: MaskEdit
documentation: ug
---

# Configure Persistence Support in ASP.NET Webforms MaskEdit

The following steps explains the implementation of EnablePersistence in MaskEditTextbox.



{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" EnablePersistence="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox with EnablePersistence before page load and after page load are as follows.

![ASP.NET Webforms MaskEdit Enabled or Disabled](Configure-Persistence-Support_images/Configure-Persistence-Support_img1.png) ![ASP.NET Webforms MaskEdit Configure Enabled or Disabled](Configure-Persistence-Support_images/Configure-Persistence-Support_img2.png)


## Enabled or Disabled

The MaskEditTextbox control have an option to enable or disable its element. You can set the Enabled property as true to enable the MaskEditTextbox control. Enabled property accepts Boolean value. By default the value of enabled is set as true.

### Configure Enabled or Disabled 

The following steps explains the implementation of Enabled in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Enabled="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox when “Enabled” is “true” and “Enabled” is “false”.

![ASP.NET Webforms MaskEdit Adjusting Textbox Size](Configure-Persistence-Support_images/Configure-Persistence-Support_img3.png) ![ASP.NET Webforms MaskEdit Configure Height and Width](Configure-Persistence-Support_images/Configure-Persistence-Support_img4.png)



### Adjusting Textbox Size

The MaskEditTextbox size can be modified by using the Height and Width property. You can customize the size of MaskEditTextbox by using these properties.

#### Configure Height and Width 

The following steps explains the implementation of Height and Width in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Width="100" Height="20" runat="server"> </ej:MaskEdit>





{% endhighlight %}



The output for MaskEditTextbox after setting the “Height” and “Width”.


![ASP.NET Webforms MaskEdit Define Value](Configure-Persistence-Support_images/Configure-Persistence-Support_img5.png)




### Define Value

The value of MaskEditTextbox can be assigned by using the Value property. The default value for Value property is null.

#### Configure Value

The following steps explains the implementation of Value in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="Mask" Value="1234567" runat="server"></ej:MaskEdit>





{% endhighlight %}



The output for MaskEditTextbox with Value.


![ASP.NET Webforms MaskEdit Configure Persistence Support](Configure-Persistence-Support_images/Configure-Persistence-Support_img6.png)





### Read Only Support

The MaskEditTextbox supports read only option. When enabling read only property to the control, the value can’t be changed or editable in the MaskEditTextbox. You can set the ReadOnly property as true to enable this option.

#### Configure Read Only

The following steps explains the implementation of ReadOnly in MaskEditTextbox.

Add the following code example in your ASPX page to render the MaskEditTextbox control.

{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999"  ReadOnly="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox when “ReadOnly” is “true”. The MaskEditTextbox values can not be edited or changed.

![ASP.NET Webforms MaskEdit Error Visibility](Configure-Persistence-Support_images/Configure-Persistence-Support_img7.png)


### Error Visibility

The MaskEdit Textbox have an option to show the error value with red color text. It is used to validate the Mask Edit value. You can set the ShowError property as true to enable this option.

#### Configure Error Visibility

The following steps explains the implementation of ShowError in Mask Edit Textbox.

Add the following code example in your ASPX page to render the Textbox control.

{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Value="1234567" ShowError="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for Textbox when “ShowError” is “true”. 

![ASP.NET Webforms MaskEdit Configure Error Visibility](Configure-Persistence-Support_images/Configure-Persistence-Support_img8.png)

![ASP.NET Webforms MaskEdit ShowError](Configure-Persistence-Support_images/Configure-Persistence-Support_img9.png)


