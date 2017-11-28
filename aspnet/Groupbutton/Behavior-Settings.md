---
layout: post
title: Button Type | GroupButton | ASP.NET Webforms | Syncfusion
description: Groupbutton type
platform: aspnet
control: GroupButton
documentation: ug
---

# Behavior settings

Groupbutton provides options through which you can customize the default behavior of Groupbutton control.

## Groupbutton Mode

The default behavior of Groupbutton is like Radiobutton, i.e., only one item can be selected at a time.

{% highlight html %}

<ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="RadioButton"  Size="Large">
<Items>
<ej:GroupButtonItem Text="Daily"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Weekly"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Monthly"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}

![](Behavior-Settings_images/Radiobutton.png)

RadioButton mode
{:.caption}

To enable selection of one or more Groupbutton items at a time, you can set the Groupbutton mode to Checkbox. With this, you can toggle the each button’s state to perform actions, since all the button will behave like individual buttons.

{% highlight html %}

<ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="CheckBox" Size="Large">
<Items>
<ej:GroupButtonItem Text="Daily"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Weekly"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Monthly"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>   

{% endhighlight %}

![](Behavior-Settings_images/Checkbox.png)

CheckBox mode
{:.caption}

## SelectedItemIndex

The state of the button can be changed by clicking on the button. Also the selection state of the button can be achieved by using **SelectedItemIndex** API which is used to select the button items in GroupButton based on index.

This property will accept the array values and its value will be differ based on current mode of Button. If the Button mode is “Radio”, then the selected items can have single value within the array, since we can select a single button only in this mode. Whereas for the “checkbox” mode, the selectedItemIndex can have the multiple values within an array, since multiple button can be in active state in this mode.

**Setting SelectedItemIndex for RadioButton Mode**

{% tabs %}
{% highlight html %}

    <ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="RadioButton"  Size="Large">
        <Items>
            <ej:GroupButtonItem Text="Daily"></ej:GroupButtonItem>
            <ej:GroupButtonItem Text="Weekly"></ej:GroupButtonItem>
            <ej:GroupButtonItem Text="Monthly"></ej:GroupButtonItem>
        </Items>
    </ej:GroupButton>   
    
{% endhighlight  %}
{% highlight c# %}

    public partial class _Default : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
           List<int> index = new List<int>();
            index.Add(2);
            this.GroupButton2.SelectedItemIndex = index;
		}
    }

{% endhighlight  %}
{% endtabs %} 

![](Behavior-Settings_images/RadioButton_selectedItem.png)

RadioButton mode
{:.caption}


**Setting SelectedItemIndex for CheckBox Mode**

{% tabs %}
{% highlight html %}

    <ej:GroupButton ID="GroupButton2" runat="server" GroupButtonMode="CheckBox"  Size="Large">
        <Items>
            <ej:GroupButtonItem Text="Daily"></ej:GroupButtonItem>
            <ej:GroupButtonItem Text="Weekly"></ej:GroupButtonItem>
            <ej:GroupButtonItem Text="Monthly"></ej:GroupButtonItem>
        </Items>
    </ej:GroupButton>   
    
{% endhighlight  %}
{% highlight c# %}

    public partial class _Default : Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
           List<int> index = new List<int>();
            index.Add(0);
            index.Add(2);
            this.GroupButton2.SelectedItemIndex = index;
		}
    }

{% endhighlight  %}
{% endtabs %} 

![](Behavior-Settings_images/Checkbox_selectedItem.png)

CheckBox mode
{:.caption}