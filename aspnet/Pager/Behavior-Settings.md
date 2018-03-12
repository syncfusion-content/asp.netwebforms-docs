---
layout: post
title: behavior settings
description: behavior settings
platform: aspnet
control: Pager
documentation: ug
---

# Behavior Settings

## Page Size List

The **PageSizeList** property of the Pager control allows an option to have multiple options of page size values. By defining pageSizeList, a dropdown will render in a Pager with given values along with the current pageSize as selected value in dropdown. 

Selected value in a dropdown will be set to pageSize API and Pager will refresh based on this new pageSize.

{% highlight cshtml %}

        <%--Default.aspx--%>
        <ej:Pager ID="Pager" TotalRecordsCount="7" runat="server"></ej:Pager>

{% endhighlight %}

{% highlight c# %}

       //Default.aspx.cs
       protected void Page_Load(object sender, EventArgs e)
        {
            List<int> PageList = new List<int>();
            PageList.Add(1);
            PageList.Add(2);
            PageList.Add(3);
            this.Pager.PageSizeList = PageList;
        }

{% endhighlight %}

![pager](behavior-settings_images\pageSizeList.png)

## Page Size Message

The **PageSizeMessage** property allows to show a message along with the dropdown when **pageSizeList** API of Pager control is defined. In the below sample, the **PageSizeMessage** of Pager displays the current **pageSize** value of the Pager control and will also be updated whenever the pageSize value is changed by selecting a value from the dropdown.

{% highlight javascript %}

        <ej:Pager ID="Pager" TotalRecordsCount="7" PageSize="1" PageSizeMessage="PageSize:1" runat="server"></ej:Pager>

{% endhighlight %}

![pager](behavior-settings_images\pageSizeMessage.png)

## Responsive

The Pager control has responsive support such that control also fit with mobile resolutions. By enabling **isResponsive** API, you can make the Pager control responsive. While resizing the browser window, the inner elements in the Pager control will adjust automatically to equalize the size. By default, **isResponsive** API value is false. 

{% highlight javascript %}

      <ej:Pager ID="Pager" TotalRecordsCount="7" PageSize="1" IsResponsive="true" runat="server"></ej:Pager>

{% endhighlight %}

![pager](behavior-settings_images\Pager_Responsive.png)

## Current Page

The **CurrentPage** value of the Pager determines which page to be displayed currently. The default value of the **currentPage** API is 1

{% highlight javascript %}

       <ej:Pager ID="Pager" TotalRecordsCount="20" PageSize="1" PageCount="3" CurrentPage="2" runat="server"></ej:Pager>

{% endhighlight %}

![pager](behavior-settings_images\Pager_Currentpage.png)

## Enable/Disable

You can enable or disable Pager control by using **Enabled** property. Setting enabled API value as false will disable the user interaction with the Pager control.

{% highlight javascript %}

    @Html.EJ().Pager("Pager").PageSize(1).PageCount(3).Enabled(false).TotalRecordsCount(20)

{% endhighlight %}

![pager](behavior-settings_images\Pager_EnableDisable.png)