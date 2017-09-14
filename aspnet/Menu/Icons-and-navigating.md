---
layout: post
title: Icons and navigating | Menu | ASP.NET Webforms | Syncfusion
description: icons and navigating
platform: aspnet
control: Menu
documentation: ug
---

# Icons and navigating

Icons are the images that are to be displayed in the Menu control. To specify the menu with icons, you can use sprite property to display the icons. 

Add the following code example in your ASPX page.

{% highlight html %}



<ej:Menu ID="menuJson" DataIdField="id" DataParentIdField="parentId" DataTextField="text" DataSpriteCssField="sprite" runat="server"></ej:Menu>





{% endhighlight %}



In code behind add the following code example.

{% highlight c# %}



public partial class Menu : System.Web.UI.Page

{

    protected void Page_Load(object sender, EventArgs e)

    {

        List<icons> menu = new List<icons>();

        menu.Add(new icons { id = 1, text = "Inbox", parentId = null, sprite = "mail sprite-root" });

        menu.Add(new icons { id = 2, text = "Sent items", parentId = null, sprite = "mail sprite-sent-items" });

        menu.Add(new icons { id = 3, text = "All mail", parentId = null, sprite = "mail sprite-notes" });

        menu.Add(new icons { id = 4, text = "Outbox", parentId = null, sprite = "mail sprite-outbox" });

        menu.Add(new icons { id = 11, parentId = "1", text = "Mark as unread", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 12, parentId = "1", text = "Forward", sprite = "mail sprite-drafts" });

        menu.Add(new icons { id = 13, parentId = "1", text = "Mark as favorite", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 14, parentId = "1", text = "Mark as important", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 15, parentId = "2", text = "Move to trash", sprite = "mail sprite-junk" });

        menu.Add(new icons { id = 16, parentId = "2", text = "Delete", sprite = "mail sprite-deleted" });

        menu.Add(new icons { id = 17, parentId = "3", text = "New mail", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 18, parentId = "3", text = "Read mail", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 19, parentId = "3", text = "Unread mail", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 20, parentId = "4", text = "Discard draft", sprite = "mail sprite-drafts" });

        menu.Add(new icons { id = 21, parentId = "4", text = "Send again", sprite = "mail sprite-folder" });

        menu.Add(new icons { id = 22, parentId = "4", text = "Delete", sprite = "mail sprite-deleted" });

        menuJson.DataSource = menu;

    }

    public class icons

    {

        public string text { get; set; }

        public string sprite { get; set; }

        public int id { get; set; }

        public string parentId { get; set; }

    }

}



{% endhighlight %}



Add the following code example in your style section.

{% highlight css %}



    #<%=menuJson.ClientID%> {

        margin-left: 50px;

    }

    .e-menu li > ul > li > a {

        padding: 3px 24px 3px 35px;

    }

    .mail {

        background-image: url("Content/mails.png");

        height: 18px;

        left: 2px;

        top: 4px;

        width: 24px;

    }

    .sprite-root { background-position: -25px -49px; }

    .sprite-deleted { background-position: -24px -152px; }

    .sprite-drafts { background-position:-24px -83px; }

    .sprite-folder { background-position: -24px -464px; }

    .sprite-inbox { background-position: -25px -13px; }

    .sprite-junk { background-position: -23px -187px; }

    .sprite-notes { background-position: -26px -394px; }

    .sprite-outbox { background-position: -24px -500px; }

    .sprite-sent-items{ background-position: -26px -118px; }





{% endhighlight %}



The following screenshot displays the output for the above code example on Menu with Icons.  

![](Icons-and-navigating_images/Icons-and-navigating_img1.png) 



