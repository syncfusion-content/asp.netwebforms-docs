---
layout: post
title: Getting Started | ListView | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: ListView
documentation: ug
---
# Getting Started

This section explains briefly on how to create a ListView control in your application.

## Create ListBox

The Essential Studio ListView widget builds an interactive list view interface. This control allows you to select an item from a list-like interface and provides the infrastructure to display a set of data items in different layouts or views. Lists display data, data navigation, result lists, and data entry.

![](Getting-Started_images\Getting-Started_img1.png)

The following steps guide you to add a ListView control in an ASP application.

## Create a simple ListView
1.	You can create an ASP Project and add necessary Dll’s and Scripts with the help of the given [ASP Getting Started](http://help.syncfusion.com/aspnet/getting-started) Documentation.
2.	Create listview wrapper with its view items as in the below code snippet..

{% highlight html %}

<ej:ListView ID="ListView1" runat="server">
    <Items>

        <ej:ListViewItems Text="Inbox"></ej:ListViewItems>
        <ej:ListViewItems Text="VIP"></ej:ListViewItems>
        <ej:ListViewItems Text="Drafts"></ej:ListViewItems>
        <ej:ListViewItems Text="Sent"></ej:ListViewItems>
        <ej:ListViewItems Text="Junk"></ej:ListViewItems>
        <ej:ListViewItems Text="Trash"></ej:ListViewItems>
        <ej:ListViewItems Text="All mails"></ej:ListViewItems>
        <ej:ListViewItems Text="Mail"></ej:ListViewItems>

    </Items>
</ej:ListView>

{% endhighlight %}


Run the above code to render the following output.

![](Getting-Started_images\Getting-Started_img2.png)

## Add header
You can add a header for ListView using `ShowHeader` property. Refer to the following code example.

{% highlight html %}

<ej:ListView ID="ListView1" ShowHeader="true" HeaderTitle="MailBox" runat="server">
    <Items>

        <ej:ListViewItems Text="Inbox"></ej:ListViewItems>
        <ej:ListViewItems Text="VIP"></ej:ListViewItems>
        <ej:ListViewItems Text="Drafts"></ej:ListViewItems>
        <ej:ListViewItems Text="Sent"></ej:ListViewItems>
        <ej:ListViewItems Text="Junk"></ej:ListViewItems>
        <ej:ListViewItems Text="Trash"></ej:ListViewItems>
        <ej:ListViewItems Text="All mails"></ej:ListViewItems>
        <ej:ListViewItems Text="Mail"></ej:ListViewItems>

    </Items>
</ej:ListView>

{% endhighlight %}

Run the above code to render the following output.

![](Getting-Started_images\Getting-Started_img1.png)