---
layout: post
title: Template-Support
description: template support
platform: aspnet
control: DropDownList
documentation: ug
---

# Template Support

DropDown widget provides the template support for the DropDownList, when binding the data for the DropDown. For this behaviour, you need to set the common syntax /element in the template property. You can add any Html mark-up element inside DropDown list by using this property.

The following steps explain the behaviour of template support with DropDownList.

In an ASPX page, add an element to configure the DropDownList widget.

> Note: Images for this sample are available in the ‘installed location /themes/images’. 


{% highlight html %}

<div class="control">

    <ej:DropDownList ID="dropdownlist" Template="<img class='eimg' src='../Content/images/Employee/${eimg}.png' alt='employee' height='50px' width='50px'/><div class='customalign'><div class='ename'> ${text} </div><div class='desig'> ${desig} </div><div class='cont'> ${country}</div></div>"

        Width="200px" runat="server">

    </ej:DropDownList>

</div>





{% endhighlight %}



{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

        {



            List<employee> EmpList = new List<employee>();

            EmpList.Add(new employee() { Text = "Erik Linden", Image = "3", Designation = " Representative", Country = "England" });

            EmpList.Add(new employee() { Text = "John Linden", Image = "6", Designation = "Representative", Country = "Norway" });

            EmpList.Add(new employee() { Text = "Louis", Image = "7", Designation = "Representative", Country = "Australia" });

            EmpList.Add(new employee() { Text = "Lawrence", Image = "8", Designation = "Representative", Country = "India" });

            dropdownlist.DataSource = EmpList;



        }

   public class employee

        {

            public string Image{get; set;}

            public string Text {get; set;}

            public string Designation{ get; set;}

            public string Country{get;set; }

        }





{% endhighlight %}



Customize the template in CSS. 

{% highlight css %}

  <style type="text/css">

        .customalign {

            display: inline;

            float: right;

        }

    </style>



{% endhighlight %}



Output of the above steps.

![](Template-Support_images/Template-Support_img2.png) 



