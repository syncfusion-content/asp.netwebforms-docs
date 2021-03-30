---
layout: post
title: grouped list | ListView | ASP.NET Webforms | Syncfusion
description: This section explains how to group the set of items in the Syncfusion ASP.NET Web Forms ListView component.
platform: aspnet
control: ListView
documentation: ug
---

# Grouped List

**First Level Group List**

The **ListView** widget can make as grouped list by setting the `EnableGroupList` property as **“true”**. This groups the set of items listed under **ul**. You can identify the grouped items with the header title specified respectively.

Refer the following code example.


{% highlight html %}

<ej:ListView ID="List" runat="server" ShowHeader="true" HeaderTitle="MailBox" Height="450" Width="400" EnableGroupList="true">
        <GroupItems>
            <ej:ListViewGroupItems Title="Network">
                <ej:ListViewItems Text="Airplane_Mode"></ej:ListViewItems>
                <ej:ListViewItems Text="Wi-Fi"></ej:ListViewItems>
                <ej:ListViewItems Text="Notifications"></ej:ListViewItems>
                <ej:ListViewItems Text="Location_Services"></ej:ListViewItems>
            </ej:ListViewGroupItems>
            <ej:ListViewGroupItems Title="Apps">
                <ej:ListViewItems Text="Sound"></ej:ListViewItems>
                <ej:ListViewItems Text="Brightness"></ej:ListViewItems>
                <ej:ListViewItems Text="Wallpaper"></ej:ListViewItems>
            </ej:ListViewGroupItems>
            <ej:ListViewGroupItems Title="Settings">
                <ej:ListViewItems Text="General"></ej:ListViewItems>
                <ej:ListViewItems Text="Brightness"></ej:ListViewItems>
                <ej:ListViewItems Text="Wallpaper"></ej:ListViewItems>
            </ej:ListViewGroupItems>
        </GroupItems>
</ej:ListView>

{% endhighlight %}

Run the codes to get the following output

![ASPNET ListView Grouped-List Image1](Grouped-List_images/Grouped-List_img1.png) 


**Nested Child Group List**

While selecting a list item that is grouped, you can also render another set of list items. This is achieved by defining the desired **child item list** within the list containing **”PrimaryKeyValue”.** This `PrimaryKeyValue` property relates the parent child for identifying its appropriate child when clicking on the parent list item.

Refer the following code examples.


{% highlight html %}
<ej:ListView ID="List" runat="server" ShowHeader="true" HeaderTitle="MailBox" Height="450" Width="400" EnableGroupList="true">
        <GroupItems>
            <ej:ListViewGroupItems Title="Network">
                <ej:ListViewItems Text="Airplane_Mode"></ej:ListViewItems>
                <ej:ListViewItems Text="Wi-Fi"></ej:ListViewItems>
                <ej:ListViewItems Text="Notifications"></ej:ListViewItems>
                <ej:ListViewItems Text="Location_Services"></ej:ListViewItems>
            </ej:ListViewGroupItems>
            <ej:ListViewGroupItems Title="Apps">
                <ej:ListViewItems Text="Sound" PrimaryKey="1">
                    <Items>
                        <ej:ListViewItems Text="Ring Tone"></ej:ListViewItems>
                        <ej:ListViewItems Text="Message Tone"></ej:ListViewItems>
                        <ej:ListViewItems Text="Notification Tone"></ej:ListViewItems>
                    </Items>
                </ej:ListViewItems>
                <ej:ListViewItems Text="Brightness"></ej:ListViewItems>
                <ej:ListViewItems Text="Wallpaper"></ej:ListViewItems>
            </ej:ListViewGroupItems>
            <ej:ListViewGroupItems Title="Settings">
                <ej:ListViewItems Text="General"></ej:ListViewItems>
                <ej:ListViewItems Text="Brightness"></ej:ListViewItems>
                <ej:ListViewItems Text="Wallpaper"></ej:ListViewItems>
            </ej:ListViewGroupItems>
        </GroupItems> 
</ej:ListView>

{% endhighlight %}

Run the codes to get the following output

![ASPNET ListView Grouped-List Image2](Grouped-List_images/Grouped-List_img2.png) 




