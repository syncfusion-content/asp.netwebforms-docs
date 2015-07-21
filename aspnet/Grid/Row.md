---
layout: post
title: Row
description: row
platform: aspnet
control: Grid
documentation: ug
---

# Row

## Details Template

Details Template feature provides a detailed view about additional information of each row. If you want to view the detailed information, you can expand a row. Using DetailsTemplate property to achieve detail template feature.
{% highlight html %}
[ASP]

[aspx]

&lt;asp:Content runat="server" ID="BodyContent" ContentPlaceHolderID="MainContent"&gt;

    &lt;script id="tabGridContents" type="text/x-jsrender"&gt;

    &lt;div id="contact{{:EmployeeID}}" style="font-weight: bold; padding: 5px;"&gt;

        &lt;div id="cont"&gt;

            contact:{{:Address}}&lt;br /&gt;

            city:{{:City}}&lt;br /&gt;

            Country:{{:Country}}&lt;br /&gt;

            phone:{{:HomePhone}}&lt;br /&gt;

        &lt;/div&gt;

    &lt;/div&gt;

&lt;/script&gt;



&lt;ej:Grid ID="DetailTemplate" runat="server" DetailsTemplate="#tabGridContents"&gt;

    &lt;Columns&gt;

        &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" /&gt;

        &lt;ej:Column Field="FirstName" HeaderText="First Name" /&gt;

        &lt;ej:Column Field="Title" HeaderText="Title" /&gt;

        &lt;ej:Column Field="City" HeaderText="City" /&gt;

        &lt;ej:Column Field="Country" HeaderText="Country" /&gt;

    &lt;/Columns&gt;

&lt;/ej:Grid&gt;
{% endhighlight  %}
{% highlight c# %}
[cs]

protected void Page_Load(object sender, EventArgs e)

    {

        this.DetailTemplate.DataSource = new NorthwindDataContext().Employees.Take(9).ToList();

        this.DetailTemplate.DataBind();

    }


{% endhighlight %}
The following output is displayed as a result of the above code example.



![](Row_images/Row_img1.png)
{:.image }


## Hierarchy

In this section, you can learn how to use the Hierachytree in GridView. The following code example is of HierachyGrid.

{% highlight html %}

[ASP]

[aspx]

&lt;ej:Grid ID="DetailTemplate" runat="server" DetailsTemplate="#tabGridContents" &gt;

  &lt;ClientSideEvents DetailsDataBound="detailGridData" /&gt;

    &lt;Columns&gt;

        &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" /&gt;

        &lt;ej:Column Field="FirstName" HeaderText="First Name" /&gt;

        &lt;ej:Column Field="Title" HeaderText="Title" /&gt;

        &lt;ej:Column Field="City" HeaderText="City" /&gt;

        &lt;ej:Column Field="Country" HeaderText="Country" /&gt;

    &lt;/Columns&gt;

&lt;/ej:Grid&gt;



&lt;script src="Scripts/jsondata.min.js"&gt;&lt;/script&gt;

&lt;script id="tabGridContents" type="text/x-jsrender"&gt;

    &lt;div class="tabcontrol" id="Test"&gt;

        &lt;div id="detailGrid"&gt;

        &lt;/div&gt;

        &lt;label id="employeeDet" style="display: none"&gt;{{:EmployeeID}}&lt;/label&gt;

    &lt;/div&gt;

&lt;/script&gt;



&lt;script type="text/javascript"&gt;

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

&lt;/script&gt;

{% endhighlight %}
{% highlight c# %}
[cs]

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
The following output is displayed as a result of the above code example.



![](Row_images/Row_img2.png)
{:.image }


## Row Template

Row template is used to render your template in every row. It is used to place elements inside Grid rows. This feature makes it easier to customise Grid rows with HTML elements. Using RowTemplate property achieve row template feature.
{% highlight html %}
[ASP]

[aspx]

&lt;script id="templateData" type="text/x-jsrender"&gt;

    &lt;tr&gt;

        &lt;td class="photo"&gt;

            &lt;img style="width: 130px; height: 160px" src="http://js.syncfusion.com/demos/web/themes/images/Employees//{{:EmployeeID}}.png" alt="{{:EmployeeID}}" /&gt;

        &lt;/td&gt;

        &lt;td class="details"&gt;

            &lt;table class="CardTable" cellpadding="3" cellspacing="6"&gt;

                &lt;colgroup&gt;

                    &lt;col width="50%"&gt;

                    &lt;col width="50%"&gt;

                &lt;/colgroup&gt;

                &lt;tbody&gt;

                    &lt;tr&gt;

                        <td class="CardHeader">First Name: &lt;/td&gt;

                        &lt;td style="padding: 20px"&gt;{{:FirstName}} &lt;/td&gt;

                    &lt;/tr&gt;

                    &lt;tr&gt;



                        <td class="CardHeader">Birth Date:

                        &lt;/td&gt;

                        &lt;td style="padding: 20px"&gt;{{:BirthDate.toLocaleDateString()}}

                        &lt;/td&gt;

                    &lt;/tr&gt;

                    &lt;tr&gt;



                        <td class="CardHeader">Hire Date:

                        &lt;/td&gt;

                        &lt;td style="padding: 20px"&gt;{{:HireDate.toLocaleDateString()}}

                        &lt;/td&gt;

                    &lt;/tr&gt;

                &lt;/tbody&gt;

            &lt;/table&gt;

        &lt;/td&gt;

    &lt;/tr&gt;

&lt;/script&gt;



&lt;style&gt;

    .CardHeader {

        font-weight: bold;

        font-size: 14px;

        padding: 20px;

    }

&lt;/style&gt;



&lt;ej:Grid ID="Grid" runat="server" AllowScrolling="True" RowTemplate="#templateData"&gt;

    &lt;ScrollSettings Height="480" Width="500" /&gt;

    &lt;Columns&gt;

        &lt;ej:Column HeaderText="Photo" Width="30" /&gt;

        &lt;ej:Column HeaderText="Employee Details" Width="70" /&gt;

    &lt;/Columns&gt;

&lt;/ej:Grid&gt;
{% endhighlight %}
{% highlight c# %}
[CS]

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

The following output is displayed as a result of the above code example.



![](Row_images/Row_img3.png)
{:.image }


## Customize Hover and AltRow 

EnableAltRow and EnableRowHover are graphical features in Grid that are used to enable alternate row color in Grid and enable hover effects while hovering over row cells. By default, these two features are enabled in Grid. In this section, you can learn how to cutomize alternative rows color and hover color in the Grid controls.

{% highlight html %}

[ASP]

[aspx]



@*custom style*@

&lt;style&gt;

    .e-grid .e-alt_row {

        background-color: lightgreen !important;

    }



    .e-grid .e-hover {

        background: black !important;

    }

&lt;/style&gt;



&lt;ej:Grid ID="Grid" runat="server" AllowPaging="True" EnableAltRow="True" EnableRowHover="True"&gt;

    &lt;PageSettings PageSize="5"&gt;&lt;/PageSettings&gt;

&lt;/ej:Grid&gt;

{% endhighlight  %}
{% highlight c# %}
[cs]

protected void Page_Load(object sender, EventArgs e)

    {

        this.Grid.DataSource = new NorthwindDataContext().Orders.ToList();

        this.Grid.DataBind();

    }

{% endhighlight %}

The following output is displayed as a result of the above code example.



![](Row_images/Row_img4.png) 
{:.image }


