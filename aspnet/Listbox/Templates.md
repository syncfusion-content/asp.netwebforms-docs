---
layout: post
title: Templates | ListBox | ASP.NET Webforms | Syncfusion
description: template support
platform: aspnet
control: ListBox
documentation: ug
---

# Templates

The ListBox widget’s appearance can be customized based on different needs using templates. The desired templates can be defined using the “template” property.

In the design page set the template property and create the data source in code behind.

{% tabs %}
{% highlight html %}

<div class="control">
     <ej:ListBox ID="ListBox" runat="server" Width="350" Template='<div><img class="image" src="../content/images/Employees/${eimg}.png" alt="employee"/><div class="ename"> ${Text} </div><div class="design"> ${design} </div><div class="country"> ${country} </div></div>'>
     </ej:ListBox>
</div>

{% endhighlight %}
{% highlight c# %}

public partial class Template : System.Web.UI.Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                List<EmployeeSpecialists> employee = new List<EmployeeSpecialists>();
                employee.Add(new EmployeeSpecialists { Text = "Erik Linden", EmployeeImg = "3", Design = "Representative", Country = "England" });
                employee.Add(new EmployeeSpecialists { Text = "John Linden", EmployeeImg = "6", Design = "Representative", Country = "Norway" });
                employee.Add(new EmployeeSpecialists { Text = "Louis", EmployeeImg = "7", Design = "Representative", Country = "Australia" });
                employee.Add(new EmployeeSpecialists { Text = "Lawrence", EmployeeImg = "8", Design = "Representative", Country = "India" });
                selectExperts.DataSource = employee;
            }
        }
        public class EmployeeSpecialists
        {
            public string Text { get; set; }
            public string EmployeeImg { get; set; }
            public string Design { get; set; }
            public string Country { get; set; }
        }


{% endhighlight %}
{% endtabs %}

Define the styles for the template as below.


{% highlight css %}

    .image {
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

        .e-design, .country {
            font-size: smaller;
            padding: 3px 3px 0px 0px;
        }

{% endhighlight %}


 ![](Templates_images/Templates_img1.png)