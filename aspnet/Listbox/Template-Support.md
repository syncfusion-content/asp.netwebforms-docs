---
layout: post
title: Template-Support
description: template support
platform: aspnet
control: Control Name undefined
documentation: ug
---

# Template Support

ListBox widget provides the template support, when binding the data for the ListBox. For this behaviour, set the common syntax /element in template property. You can add any HTML mark-up element inside the ListBox using this property.

The following steps explains you the behaviour of template support with ListBox.

In an ASPX page, add an elementto configure ListBox.

Note: Images for this sample are available in ‘installed location/images/Employee’ 


{% highlight html %}

<div id="controlitem">

    <div>

        Template Support</div>

    <ej:listbox id="selectExperts" runat="server" Height="240" ItemsCount="5" Template="<img class='eimg' src='/Content/images/Employee/${eimg}.png' alt='employee' height='50px' width='50px'/><div class='ename'> ${text} </div><div class='desig'> ${desig} </div><div class='cont'> ${country} </div>">

                        </ej:listbox>

</div>





{% endhighlight %}



{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

        {

      List<EmployeeSpecialists> empl = new List<EmployeeSpecialists>();



      empl.Add(new EmployeeSpecialists { text = "Erik Linden", eimg = "3", desig = "Representative", country = "England" });

      empl.Add(new EmployeeSpecialists { text = "John Linden", eimg = "6", desig = "Representative", country = "Norway" });

      empl.Add(new EmployeeSpecialists { text = "Louis", eimg = "7", desig = "Representative", country = "Australia" });

      empl.Add(new EmployeeSpecialists { text = "Lawrence", eimg = "8", desig = "Representative", country = "India" });

      empl.Add(new EmployeeSpecialists { text = "Erik Linden", eimg = "3", desig = "Representative", country = "England" });

      empl.Add(new EmployeeSpecialists { text = "John Linden", eimg = "6", desig = "Representative", country = "Norway" });

      empl.Add(new EmployeeSpecialists { text = "Louis", eimg = "7", desig = "Representative", country = "Australia" });

      empl.Add(new EmployeeSpecialists { text = "Lawrence", eimg = "8", desig = "Representative", country = "India" });

      selectExperts.DataSource = empl;

        }

        public class EmployeeSpecialists

        {

            public string text { get; set; }

            public string eimg { get; set; }

            public string desig { get; set; }

            public string country { get; set; }

        }





{% endhighlight %}



Customize the template in CSS. 


{% highlight css %}

    .eimg {

        margin: 0;

        padding: 3px 10px 3px 3px;

        border: 0 none;

        width: 60px;

        height: 60px;

        float: left;

    }



    .ename {

        font-weight: bold;

        padding: 6px 3px 1px 3px;

    }



    .desig, .cont {

        font-size: smaller;

        padding: 3px 3px -1px 0px;

    }



    #<%=selectexperts.ClientID%> li {

        width: 200px;

        height: 70px;

        padding: 5px;

    }



{% endhighlight %}



Output of the above steps.




 ![C:/Users/Rajaveni/Desktop/docs/UG images/moditemplate.PNG](Template-Support_images/Template-Support_img1.png)



