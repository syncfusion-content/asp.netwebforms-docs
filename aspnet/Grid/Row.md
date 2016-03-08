---
layout: post
title: Row | Grid | ASP.NET Webforms | Syncfusion
description: row
platform: aspnet
control: Grid
documentation: ug
---

# Row

## Details Template

Details Template feature provides a detailed view about additional information of each row. If you want to view the detailed information, you can expand a row. Using DetailsTemplate property to achieve detail template feature.

{% tabs %}

{% highlight html %}

<asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent">

    <script id="tabGridContents" type="text/x-jsrender">

    <div id="contact{{:EmployeeID}}" style="font-weight: bold; padding: 5px;">

        <div id="cont">

            contact:{{:Address}}<br />

            city:{{:City}}<br />

            Country:{{:Country}}<br />

            phone:{{:HomePhone}}<br />

        </div>

    </div>

</script>



<ej:Grid ID="DetailTemplate" runat="server" DetailsTemplate="#tabGridContents">

    <Columns>

        <ej:Column Field="EmployeeID" HeaderText="Employee ID" />

        <ej:Column Field="FirstName" HeaderText="First Name" />

        <ej:Column Field="Title" HeaderText="Title" />

        <ej:Column Field="City" HeaderText="City" />

        <ej:Column Field="Country" HeaderText="Country" />

    </Columns>

</ej:Grid>
{% endhighlight  %}
{% highlight c# %}


protected void Page_Load(object sender, EventArgs e)

    {

        this.DetailTemplate.DataSource = new NorthwindDataContext().Employees.Take(9).ToList();

        this.DetailTemplate.DataBind();

    }


{% endhighlight %}

{% endtabs %}
The following output is displayed as a result of the above code example.



![](Row_images/Row_img1.png)



## Hierarchy

In this section, you can learn how to use the Hierarchy in GridView. The following code example is of HierarchyGrid.

{% tabs %}

{% highlight html %}



<ej:Grid ID="DetailTemplate" runat="server" DetailsTemplate="#tabGridContents" >

  <ClientSideEvents DetailsDataBound="detailGridData" />

    <Columns>

        <ej:Column Field="EmployeeID" HeaderText="Employee ID" />

        <ej:Column Field="FirstName" HeaderText="First Name" />

        <ej:Column Field="Title" HeaderText="Title" />

        <ej:Column Field="City" HeaderText="City" />

        <ej:Column Field="Country" HeaderText="Country" />

    </Columns>

</ej:Grid>



<script src="Scripts/jsondata.min.js"></script>

<script id="tabGridContents" type="text/x-jsrender">

    <div class="tabcontrol" id="Test">

        <div id="detailGrid">

        </div>

        <label id="employeeDet" style="display: none">{{:EmployeeID}}</label>

    </div>

</script>



<script type="text/javascript">

    function detailGridData(e) {

        var filteredData = e.detailsElement.find("#employeeDet").text();

        // the datasource "window.ordersView" is referred from jsondata.min.js

        var data = ej.DataManager(window.ordersView).executeLocal(ej.Query().where("EmployeeID", "equal", parseInt(filteredData), true));

        e.detailsElement.find("#detailGrid").ejGrid({

            dataSource: data,

            columns: [

                { field: "OrderID", key: true, headerText: "Order ID", width: 80, textAlign: ej.TextAlign.Right },

                { field: "CustomerID", headerText: 'Customer ID', width: 80, textAlign: ej.TextAlign.Left },

                { field: "CompanyName", headerText: 'Company Name', width: 120, textAlign: ej.TextAlign.Left },

                { field: "ShipCity", headerText: 'Ship City', width: 120, textAlign: ej.TextAlign.Left }

            ]

        });

    }

</script>

{% endhighlight %}
{% highlight c# %}


public partial class DetailTemplate : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            order.Add(new Orders(1, "Nancy", "Sales Representative", "Seattle", "USA"));

            order.Add(new Orders(2, "Andrew", "Vice President, Sales", "Tacoma", "USA"));

            order.Add(new Orders(3, "Janet", "Sales Representative", "Kirkland", "USA"));

            order.Add(new Orders(4, "Margaret", "Sales Representative", "Redmond", "USA"));

            order.Add(new Orders(5, "Steven", "Sales Manager", "London", "UK"));

            order.Add(new Orders(6, "Michael", "Sales Representative", "London", "UK"));

            order.Add(new Orders(7, "Robert", "Sales Representative", "London", "UK"));

            order.Add(new Orders(8, "Laura", "Inside Sales Coordinator", "Seattle", "USA"));

            order.Add(new Orders(9, "Anne", "Sales Representative", "London", "UK"));



            this.EmployeesGrid.DataSource = order;

            this.EmployeesGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(int EmployeeId, string FirstName, string Title, string City, string Country)

            {



                this.EmployeeID = EmployeeId;

                this.FirstName = FirstName;

                this.Title = Title;

                this.City = City;

                this.Country = Country;

            }

            public int EmployeeID { get; set; }

            public string FirstName { get; set; }

            public string Title { get; set; }

            public string City { get; set; }

            public string Country { get; set; }

        }

    }


{% endhighlight %}

{% endtabs %}
The following output is displayed as a result of the above code example.



![](Row_images/Row_img2.png)


## Row Template

Row template is used to render your template in every row. It is used to place elements inside Grid rows. This feature makes it easier to customize Grid rows with HTML elements. Using RowTemplate property achieve row template feature.

{% tabs %}

{% highlight js %}


<script id="templateData" type="text/x-jsrender">

    <tr>

        <td class="photo">

            <img style="width: 130px; height: 160px" src="http://js.syncfusion.com/demos/web/themes/images/Employees//{{:EmployeeID}}.png" alt="{{:EmployeeID}}" />

        </td>

        <td class="details">

            <table class="CardTable" cellpadding="3" cellspacing="6">

                <colgroup>

                    <col width="50%">

                    <col width="50%">

                </colgroup>

                <tbody>

                    <tr>

                        <td class="CardHeader">First Name: </td>

                        <td style="padding: 20px">{{:FirstName}} </td>

                    </tr>

                    <tr>



                        <td class="CardHeader">Birth Date:

                        </td>

                        <td style="padding: 20px">{{:BirthDate.toLocaleDateString()}}

                        </td>

                    </tr>

                    <tr>



                        <td class="CardHeader">Hire Date:

                        </td>

                        <td style="padding: 20px">{{:HireDate.toLocaleDateString()}}

                        </td>

                    </tr>

                </tbody>

            </table>

        </td>

    </tr>

</script>

{% endhighlight %}

{% highlight css %}

<style>

    .CardHeader {

        font-weight: bold;

        font-size: 14px;

        padding: 20px;

    }

</style>
{% endhighlight  %}
{% highlight html %}

<ej:Grid ID="Grid" runat="server" AllowScrolling="True" RowTemplate="#templateData">

    <ScrollSettings Height="480" Width="500" />

    <Columns>

        <ej:Column HeaderText="Photo" Width="30" />

        <ej:Column HeaderText="Employee Details" Width="70" />

    </Columns>

</ej:Grid>
{% endhighlight %}
{% highlight c# %}


public partial class RowTemplate : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            order.Add(new Orders(1, "Nancy", "Davolio","Sales Representative", new DateTime(1948, 12, 08),new DateTime(1992,05,01)));

            order.Add(new Orders(2, "Andrew", "Fuller","Vice President, Sales", new DateTime(1952, 02, 19),new DateTime(1992,08,14) ));

            order.Add(new Orders(3, "Janet", "Leverling","Sales Representative", new DateTime(1963, 08, 30),new DateTime(1992,04,01)));

            order.Add(new Orders(4, "Margaret", "Peacock",	"Sales Representative", new DateTime(1937, 09, 19),new DateTime(1993,05,03)));

            order.Add(new Orders(5, "Steven", "Buchanan",	"Sales Manager", new DateTime(1955, 03, 04),new DateTime(1993,10,17)));

            order.Add(new Orders(6, "Michael", "Suyama", "Sales Representative", new DateTime(1963, 07, 02), new DateTime(1993, 10, 17)));

            order.Add(new Orders(7, "Robert", "King", "Sales Representative",new DateTime(1960, 05, 29),new DateTime(1994,01,02)));

            order.Add(new Orders(8, "Laura", "Callahan", "Inside Sales Coordinator", new DateTime(1958, 01, 09),new DateTime(1994,03,05)));

            order.Add(new Orders(9, "Anne", "Dodsworth", "Sales Representative", new DateTime(1966, 01, 27), new DateTime(1994, 11, 15)));



            this.EmployeesGrid.DataSource = order;

            this.EmployeesGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(int EmployeeID, string FirstName, string LastName, string Title, DateTime BirthDate, DateTime HireDate)

            {

                this.EmployeeID = EmployeeID;

                this.FirstName = FirstName;

                this.LastName = LastName;

                this.Title = Title;

                this.BirthDate = BirthDate;

                this.HireDate = HireDate;

            }

            public int EmployeeID { get; set; }

            public string FirstName { get; set; }

            public string LastName { get; set; }

            public string Title { get; set; }

            public DateTime BirthDate { get; set; }

            public DateTime HireDate { get; set; }

        }

    }

{% endhighlight  %}

{% endtabs %}

The following output is displayed as a result of the above code example.



![](Row_images/Row_img3.png)



## Customize Hover and AltRow 

EnableAltRow and EnableRowHover are graphical features in Grid that are used to enable alternate row color in Grid and enable hover effects while hovering over row cells. By default, these two features are enabled in Grid. In this section, you can learn how to customize alternative rows color and hover color in the Grid controls.

{% tabs %}

{% highlight css %}

<style>

    .e-grid .e-alt_row {

        background-color: lightgreen !important;

    }



    .e-grid .e-hover {

        background: black !important;

    }

</style>

{% endhighlight  %}
{% highlight html %}
<ej:Grid ID="Grid" runat="server" AllowPaging="True" EnableAltRow="True" EnableRowHover="True">

    <PageSettings PageSize="5"></PageSettings>

</ej:Grid>

{% endhighlight  %}
{% highlight c# %}


protected void Page_Load(object sender, EventArgs e)

    {

        this.Grid.DataSource = new NorthwindDataContext().Orders.ToList();

        this.Grid.DataBind();

    }

{% endhighlight %}

{% endtabs %}

The following output is displayed as a result of the above code example.


![](Row_images/Row_img4.png)



