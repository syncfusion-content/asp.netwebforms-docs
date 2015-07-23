---
layout: post
title: Grouping-Support
description: grouping support
platform: aspnet
control: DropDownList
documentation: ug
---

# Grouping Support

## Grouping Support using DataSource

Grouping DropDownList items can be done by using the category field. Set the category field and define it in the DataSource. Then, map the fields for the data items of the DropDownList and set AllowGrouping property value to true.

The following step explains how to group data items in the DropDownList control by using the DataSource.

In an ASPX page, add an element to configure the DropDownList widget.

{% highlight html %}

<ej:DropDownList ID="dropdownlist" Width="200px" runat="server" DataIdField="id"

    DataTextField="text" AllowGrouping="true">

</ej:DropDownList>





{% endhighlight %}



{% highlight c# %}

    List<Books> book = new List<Books>();

    public ActionResult Index()

    {



        book.Add(new Books { id = 1, text = "Austria", category = "A" });

        book.Add(new Books { id = 2, text = "Australia", category = "A" });

        book.Add(new Books { id = 3, text = "Bangladesh", category = "B" });

        book.Add(new Books { id = 4, text = "Belgium", category = "B" });

        book.Add(new Books { id = 5, text = "Canada", category = "C" });

        book.Add(new Books { id = 6, text = "Denmark", category = "D" });

        book.Add(new Books { id = 7, text = "Egypt", category = "E" });

        book.Add(new Books { id = 8, text = "England", category = "E" });

        book.Add(new Books { id = 9, text = "India", category = "I" });

        book.Add(new Books { id = 10, text = "Italy", category = "I" });

        book.Add(new Books { id = 11, text = "Haiti", category = "H" });

        book.Add(new Books { id = 12, text = "Jordan", category = "J" });

        book.Add(new Books { id = 13, text = "Jamaica", category = "J" });

        ViewBag.datasource = book;

        return View();

    }

    public class Books

    {



        public int id { get; set; }

        public string text { get; set; }

        public string category { get; set; }

    }



{% endhighlight %}



![](Grouping-Support_images/Grouping-Support_img1.png)





