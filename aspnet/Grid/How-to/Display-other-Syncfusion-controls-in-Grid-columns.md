---
layout: post
title: Display other Syncfusion controls in Grid columns | Grid | ASP.NET Webforms | Syncfusion
description: Display other Syncfusion controls in Grid columns
platform: aspnet
control: Grid
documentation: ug
---

# Display other Syncfusion controls in Grid columns

We can display the other Syncfusion controls using `Template` property of Grid columns and `TemplateRefresh` event of Grid control.

{% tabs %}
{% highlight js %}

<script type="text/x-jsrender" id="columnTemplate">
    {{"{{"}}if EmployeeID<3{{}}}}

        <input type="text" class="rating" value="3" />

    {{"{{"}}else EmployeeID>2 && EmployeeID<5{{}}}}

        <input type="text" class="rating" value="3" />

    {{"{{"}}else EmployeeID>4{{}}}}
        <input type="text" class="rating" value="5" />

    {{"{{"}}/if{{}}}}
</script>

<script type="text/javascript">
    function template(args) {
        $(args.cell).find(".rating").ejRating({ allowReset: false });
    }
</script>

{% endhighlight %}
{% highlight html %}

    <ej:Grid ID="Grid" runat="server" AllowPaging="True">  
            <ClientSideEvents TemplateRefresh="template" />
            <Columns>
                <ej:Column HeaderText="Employee Rating" Template="#columnTemplate" Width="150" />                
                <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="90"/>
                <ej:Column Field="FirstName" HeaderText="First Name" Width="90"/>
                <ej:Column Field="LastName" HeaderText="Last Name" Width="90"/>  
                <ej:Column Field="Country" HeaderText="Country" Width="80"/>
            </Columns>
    </ej:Grid> 
        
{% endhighlight %}
{% highlight c# %}

    public partial class GridExporting : System.Web.UI.Page
    { 
        protected void Page_Load(object sender, EventArgs e)
        {
            this.Grid.DataSource = new NorthwindDataContext().EmployeeView.ToList();
            this.Grid.DataBind();
        }        
    }

{% endhighlight %}
{% endtabs %}

The following screenshot displays the exported grid with comments added to cells

![](Display-Other-controls/Display_Other_controls_img1.png)
