---
layout: post
title: Miscellaneous | GroupButton | ASP.NET Webforms | Syncfusion
description: miscellaneous
platform: aspnet
control: GroupButton
documentation: ug
---

# Miscellaneous

## Text

You can display your own text for Button. By using the **Text property**, you can easily set text content for button. This text property overwrites the text that is provided on input button element.

In the ASPX page, add the following button elements to configure Button with text



{% highlight html %}

<%--Set the text for button control as follows--%>

<ej:GroupButton runat="server" ID="GroupButton10" Size="Large">
<Items>
<ej:GroupButtonItem Text="Beverages"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Condiments"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Confections"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>

{% endhighlight %}



In the above code, the content of button “button” is replaced by the text value “Enter” that is given using the text property.

![](Miscellaneous_images/text.png)


## Show Rounded Corner

Specifies the corner of button in round shape. By default button doesn’t have rounded corner. To set rounded corner, you can enable the **ShowRoundedCorner** property.

In the ASPX page, add the following button elements to get rounded Button

{% highlight html %}

<%--Enable the rounded corner for button control as follows--%>

<ej:GroupButton runat="server" ID="GroupButton11" Size="Large" ShowRoundedCorner="true">
<Items>
<ej:GroupButtonItem Text="Beverages"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Condiments"></ej:GroupButtonItem>
<ej:GroupButtonItem Text="Confections"></ej:GroupButtonItem>
</Items>
</ej:GroupButton>



{% endhighlight %}

![](Miscellaneous_images/roundedcorner.png)


