---
layout: post
title: customization
description: customization
platform: aspnet
control: Pager
documentation: ug
---

# Customization

## Show Go To Page

The **ShowGoToPage** property of Pager renders a textbox within the Pager element.


{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageCount="3" PageSize="1" ShowGoToPage="true" runat="server"></ej:Pager>
     
{% endhighlight %}

Run the above code to get the below output.

![pager](customization_images\showGoToPage.png)
        
## Show Page Info

The **ShowPageInfo** property of the Pager control determines whether to show the page related information like total records count, total pages, current page in a Pager.


{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageCount="3" PageSize="1" ShowPageInfo="false" runat="server"></ej:Pager> 

{% endhighlight %}

Run the above code to get the below output.

![pager](customization_images\pageInfo.png)

## Custom Text

The **CustomText** property of Pager allows to add the custom text along with numeric values in the Pager numeric elements that are used for navigation in Pager control. 

{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageCount="3" PageSize="1" CustomText="Page " runat="server"></ej:Pager>

{% endhighlight %}

Run the above code to get the below output.

![pager](customization_images\customText.png)

## External Message

The Pager control also allows to define a external message using externalMessage API to display an additional information. To use external message, we need to enable it using enableExternalMessage API. In the sample below, the externalMessage of Pager is used to show the current active page of the Pager control. Whenever the current page value of the Pager changes, the externalMessage will be updated with the current page value.


{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageCount="3" PageSize="1" EnableExternalMessage="true" ExternalMessage="Current Page : 1" ClientSideOnChange="onChange" runat="server"></ej:Pager>
            <script>
                function onChange(e) {
                    var a = $("#MainContent_Pager").ejPager("instance");
                    a.option("externalMessage", "CurrentPage: " + e.currentPage);
                }
            </script>

{% endhighlight %}

Run the above code to get the below output.

![pager](customization_images\externalMessage.png)

## Custom CSS

Pager control allows you to customize the appearance using user defined CSS and custom skin options such as colors and backgrounds. To apply custom themes, we can make use of cssClass property. Using cssClass property, we can override the existing theme styles. In the following sample, value for cssClass property is set as customCss and this root class is used to customize the Pager control theme.


{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageCount="3" PageSize="1" CssClass="customCss" runat="server"></ej:Pager>

{% endhighlight %}

### Defining custom class.

{% highlight html %}

        <style>
                .e-Pager.customCss .e-link.e-currentitem{
                        background:lightblue;
                }
                .e-Pager.customCss .e-numericitem, .e-Pager.customCss .e-Pagermsg{
                    font-family:monospace;
                }
                .e-Pager.customCss .e-Pagercontainer,.e-Pager.customCss .e-link ,.e-Pager.customCss .e-icon {
                    background-color: rgba(33,33,33,0.35);
                }
                .e-Pager.customCss {
                    color:white;
                    background-color: rgba(33,33,33,0.30);
                }
                .e-Pager.customCss :hover {
                    color:white
                }
                .e-Pager.customCss .e-hover.e-numericitem, .e-Pager.customCss .e-hover.e-icon{
                    background-color:rgba(173,216,230,0.30);
                }
                .e-Pager.customCss .e-hover.e-icon.e-disable {
                    background-color: rgba(33,33,33,0.35);
                
                }
                .e-Pager.customCss .e-icon, .e-Pager.customCss .e-numericitem{
                    color:white;
                    border-right-color: #777;
                }
        </style>

{% endhighlight %}

Run the above code to get the below output.

![pager](customization_images\cssClass.png)


