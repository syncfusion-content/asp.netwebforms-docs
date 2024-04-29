---
layout: post
title: Customization in DropDownList control for Syncfusion ASP.NET WebForm
description: Learn here about customization in DropDownList control for Syncfusion ASP.NET WebForm its elements and more
platform: aspnet
control: DropDownList
documentation: ug
keywords: Customization, DropDownList, dropdown, watermark text

---

# Customization in ASP.NET DropDownList

## Adding watermark text

It provides the short description of the expected value in dropdown and will display the text until any item is selected. You can set this text using WatermarkText property.

{% highlight html %}

        <ej:DropDownList ID="DropDownList1" runat="server" WatermarkText="Select an Item">
            <Items>
                <ej:DropDownListItem Text="ListItem 1" Value="item1"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 2" Value="item2"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 3" Value="item3"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 4" Value="item4"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 5" Value="item5"></ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
        
{% endhighlight %}

![Customization in ASP.NET DropDownList](customization_images/aspnet-dropdownlist-customization.jpeg)

![ Adding watermark text in ASPNET DropDownList](customization_images/aspnet-dropdownlist-adding-watermark-text.jpeg)

## Applying Rounded Corner

You can use ShowRoundedCorner property to add rounded borders to the input and popup elements. By default, rounded corner property is disabled in DropDownList.

{% highlight html %}

        <ej:DropDownList ID="DropDownList1" runat="server" ShowRoundedCorner="true">
            <Items>
                <ej:DropDownListItem Text="ListItem 1" Value="item1"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 2" Value="item2"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 3" Value="item3"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 4" Value="item4"></ej:DropDownListItem>
                <ej:DropDownListItem Text="ListItem 5" Value="item5"></ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
        
{% endhighlight %}

![Applying Rounded Corner in ASPNET DropDownList ](customization_images/aspnet-dropdownlist-applying-rounded-corner.jpeg)

I> The browser support details for rounded corner is given [here](http://www.w3schools.com/cssref/css3_pr_border-radius.asp).

## Enable/Disable the control

The Enabled property is used to indicate whether the control can respond to the user interaction or not. You can disable it by assigning false to this property. When the control is disabled state, you cannot interact with the control.

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" runat="server" Enabled="false">
        <Items>
            <ej:DropDownListItem Text="ListItem 1" Value="item1"></ej:DropDownListItem>
            <ej:DropDownListItem Text="ListItem 2" Value="item2"></ej:DropDownListItem>
            <ej:DropDownListItem Text="ListItem 3" Value="item3"></ej:DropDownListItem>
            <ej:DropDownListItem Text="ListItem 4" Value="item4"></ej:DropDownListItem>
            <ej:DropDownListItem Text="ListItem 5" Value="item5"></ej:DropDownListItem>
        </Items>
    </ej:DropDownList>
    
{% endhighlight %}
    
![Enable/Disable the Control ](customization_images/aspnet-dropdownlist-enable-disable-the-control.jpeg)

## Applying HTML Attributes

Additional HTML attributes can be applied to the control by using HtmlAttributes property. The attributes such as name, required, read-only and disabled are directly applied to the input element of DropDownList, and other attributes such as style, class will be applied to the outer wrapper element of DropDownList.

{% tabs %}

    {% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" DataHtmlAttributesField="HtmlAttr" DataTextField="Text" DataValueField="Value"></ej:DropDownList>
    
	{% endhighlight %}
    
    {% highlight c# %}
    
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Data> DropDownData = new List<Data>();
            DropDownData.Add(new Data { Value = "item1", Text = "ListItem 1", HtmlAttr="style='border:1px solid red;'" });
            DropDownData.Add(new Data { Value = "item2", Text = "ListItem 2", HtmlAttr = "style='border:1px solid red;'" });
            DropDownData.Add(new Data { Value = "item3", Text = "ListItem 3", HtmlAttr = "style='border:1px solid red;'" });
            DropDownData.Add(new Data { Value = "item4", Text = "ListItem 4", HtmlAttr = "style='border:1px solid red;'" });
            DropDownData.Add(new Data { Value = "item5", Text = "ListItem 5", HtmlAttr = "style='border:1px solid red;'" });
            DropDownList1.DataSource = DropDownData;
        }
        public class Data
        {
            public string Value { get; set; }
            public string Text { get; set; }
            public string HtmlAttr { get; set; }
        }
        
    {% endhighlight %}
    
{% endtabs %}

![Applying HTML Attributes ](customization_images/aspnet-dropdownlist-applying-html-attributes.jpeg)

