---
layout: post
title: Refresh datasource | Grid | ASP.NET Webforms | Syncfusion
description: Learn here about refresh datasource in Syncfusion Essential ASP.NET Webforms Grid Control, its elements, and more.
platform: aspnet
control: Grid
documentation: ug
---

# Refresh datasource in ASP.NET Webforms Grid

Grid allows you to refresh datasource dynamically after Grid initialization. It is useful to refresh Grid datasource.

{% tabs %}

 {% highlight html %}

<ej:Button ID="refresh" runat="server" Type="Button" Text="Refresh" ClientSideOnClick="refresh">

</ej:Button>

<ej:Grid ID="Grid" runat="server">

    <Columns>

        <ej:Column Field="FirstName" HeaderText="First Name" />

        <ej:Column Field="LastName" HeaderText="Last Name" />

        <ej:Column Field="Email" HeaderText="Email" />

    </Columns>

</ej:Grid>







<script type="text/javascript">

    var newData = [

        { FirstName: "Carter", LastName: "Beckett", Email: "carter@syncfusion.com" },

        { FirstName: "Joe", LastName: "Beckett", Email: "joe@syncfusion.com" },

        { FirstName: "Sam", LastName: "Beckett", Email: "sam@syncfusion.com" }

    ];



    function refresh() {

$("#Grid").ejGrid("dataSource", newData);

    }



</script>

{% endhighlight %}

 {% highlight c# %}



public partial class _Default : System.Web.UI.Page

{

    List<Person> Persons = new List<Person>();

    protected void Page_Load(object sender, EventArgs e)

    {

        BindDataSource();

    }

    private void BindDataSource()

    {       

        Persons.Add(new Person() { FirstName = "John", LastName = "Beckett", Email = "john@syncfusion.com" });

        Persons.Add(new Person() { FirstName = "Ben", LastName = "Beckett", Email = "ben@syncfusion.com" });

        Persons.Add(new Person() { FirstName = "Andrew", LastName = "Beckett", Email = "andrew@syncfusion.com" });



        this.Grid.DataSource = Persons;

        this.Grid.DataBind();

    }

    public class Person

    {

        public Person()

        {



        }

        public Person(string firstName, string lastName, string email)

        {

            this.FirstName = firstName;

            this.LastName = lastName;

            this.Email = email;          

        }       

        public string FirstName { get; set; }

        public string LastName { get; set; }

        public string Email { get; set; }       

    }



}


{% endhighlight %}

{% endtabs %}


The following screenshot displays the Grid data source before refreshing.



 ![ASP.NET Webforms Grid Refresh datasource](Refresh-datasource_images/Refresh-datasource_img1.png) 



The following screenshot displays the Grid data source after refreshing.

![ASP.NET Webforms Grid after refreshing datasource](Refresh-datasource_images/Refresh-datasource_img2.png) 



