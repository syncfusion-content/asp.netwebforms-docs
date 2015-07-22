---
layout: post
title: Configure-Persistence-Support
description: configure persistence support 
platform: aspnet
control: MaskEdit
documentation: ug
---

# Configure Persistence Support 

The following steps explains the implementation of EnablePersistence in MaskEditTextbox.



{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" EnablePersistence="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox with EnablePersistencebefore page load and after page load are as follows.

![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img1.png)
{:.image }
![C:/Users/giftline.jebamani/Desktop/b.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img2.png)
{:.image }


## Enabled or Disabled

The MaskEditTextbox control have an option to enable or disable its element. You can set the Enabled property as true to enable the MaskEditTextbox control. Enabled property accepts Boolean value. By default the value of enabled isset as true.

### Configure Enabled or Disabled 

The following steps explains the implementation of Enabled in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Enabled="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox when “Enabled” is“true”and “Enabled” is “false”.

![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img3.png)
{:.image }
![C:/Users/giftline.jebamani/Desktop/b.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img4.png)
{:.image }


### Adjusting Textbox Size

The MaskEditTextbox size can be modified by using the Height and Width property. You can customize the size of MaskEditTextbox by using these properties.

#### Configure Height and Width 

The following steps explains the implementation of HeightandWidth in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Width="100" Height="20" runat="server"> </ej:MaskEdit>





{% endhighlight %}



The output for MaskEditTextbox after setting the “Height” and “Width”.
![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img5.png)
{:.image }



### Define Value

The value of MaskEditTextbox can be assigned by using the Value property. The default value for Value property is null.

#### Configure Value

The following steps explains the implementation of Value in MaskEditTextbox.



{% highlight html %}



<ej:MaskEdit ID="Mask" Value="1234567" runat="server"></ej:MaskEdit>





{% endhighlight %}



The output for MaskEditTextbox with Value.
![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img6.png)
{:.image }




### Read Only Support

The MaskEditTextbox supports read only option. When enabling read only property to the control, the value can’t be changed or editable in the MaskEditTextbox. You can set the ReadOnly property as true to enable this option.

#### Configure Read Only

The following steps explains the implementation of ReadOnlyin MaskEditTextbox.

Add the following code example in your ASPX page to render the MaskEditTextbox control.

{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999"  ReadOnly="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for MaskEditTextbox when “ReadOnly” is “true”. The MaskEditTextbox values can not be edited or changed.

![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img7.png)
{:.image }

### Error Visibility

The MaskEdit Textbox have an option to show the error value with red color text. It is used to validate the Mask Edit value. You can set the ShowError property as true to enable this option.

#### Configure Error Visibility

The following steps explains the implementation of ShowErrorin Mask Edit Textbox.

Add the following code example in your ASPX page to render the Textbox control.

{% highlight html %}

<ej:MaskEdit ID="mask" MaskFormat="99-999-99999" Value="1234567" ShowError="true" runat="server"> </ej:MaskEdit>



{% endhighlight %}



The output for Textbox when “ShowError” is “true”. 

![C:/Users/giftline.jebamani/Desktop/a.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img8.png)
{:.image }
![C:/Users/giftline.jebamani/Desktop/b.png](Configure-Persistence-Support_images/Configure-Persistence-Support_img9.png)
{:.image }

