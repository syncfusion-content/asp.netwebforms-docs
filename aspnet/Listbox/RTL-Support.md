---
layout: post
title: RTL-Support
description: rtl support
platform: aspnet
control: Control Name undefined
documentation: ug
---

# RTL Support

This feature supports to change the left-to-right alignment of the ListBox widget to right-to-left (RTL). 

## Defining the RTL property

The following steps explains you the configuration of EnableRTL properties in ListBox.

In an ASPX page, add an elementto configure ListBox.


{% highlight html %}

<div id="control">

    <div class="ctrllabel">

        Select a skill</div>

    <ej:listbox id="listboxsample" runat="server" DataTextField="Name"  EnableRTL="true"></ej:listbox>

</div>



{% endhighlight %}



{% highlight c# %}

        protected void Page_Load(object sender, EventArgs e)

        {

            listboxsample.DataSource = GetData();



        }

        private List<Languages> GetData()

        {

            List<Languages> data = new List<Languages>();

            data.Add(new Languages() { Name = "ASP.NET" });

            data.Add(new Languages() { Name = "ActionScript" });

            data.Add(new Languages() { Name = "Basic" });

            data.Add(new Languages() { Name = "C++" });

            data.Add(new Languages() { Name = "C#" });

            data.Add(new Languages() { Name = "dBase" });

            data.Add(new Languages() { Name = "Delphi" });

            data.Add(new Languages() { Name = "ESPOL" });

            data.Add(new Languages() { Name = "F#" });

            data.Add(new Languages() { Name = "FoxPro" });

            data.Add(new Languages() { Name = "Java" });

            data.Add(new Languages() { Name = "J#" });

            data.Add(new Languages() { Name = "Lisp" });

            data.Add(new Languages() { Name = "Logo" });

            data.Add(new Languages() { Name = "PHP" });

            return data;

        }



        public class Languages

        {

            public string Name;

        }





{% endhighlight %}



Output of the above steps.


 ![C:/Users/Rajaveni/Desktop/docs/UG images/rtl.PNG](RTL-Support_images/RTL-Support_img1.png)



