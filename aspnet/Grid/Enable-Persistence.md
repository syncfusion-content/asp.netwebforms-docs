---
layout: post
title: Enable-Persistence
description: enable persistence
platform: aspnet
control: Grid
documentation: ug
---

# Enable Persistence

EnablePersistence is used to maintain the current state of the Grid model. When you refresh the page, the current grid state is stored in localStorage and it renders from stored model. 


{% highlight html %}
[ASP.NET]



   &lt;div&gt;

        <ej:Grid ID="OrdersGrid" runat="server" AllowSorting="true" AllowPaging="True" AllowGrouping="True"

            EnableAltRow="True" EnablePersistence="True">

            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="100" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="110" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="90" Format="{0:C}" /&gt;

                &lt;ej:Column Field="OrderDate" HeaderText="Order Date" Width="100" TextAlign="Right" Format="{0:MM/dd/yyyy}" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" /&gt;

            &lt;/Columns&gt;

            &lt;PageSettings PageSize="9" /&gt;

        &lt;/ej:Grid&gt;

    &lt;/div&gt;
{% endhighlight  %}
{% highlight c#  %}
[ASP.NET CS]



using System;

using System.Collections.Generic;

using System.Linq;

using System.Web;

using System.Web.UI;

using System.Web.UI.WebControls;



namespace WebSampleBrowser.Grid

{

    public partial class StateMaintenance : System.Web.UI.Page

    {

        private List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10000;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 32.38, new DateTime(2014, 12, 25), "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2, 11.61, new DateTime(2014, 12, 21), "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3, 45.34, new DateTime(2014, 10, 18), "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4, 37.28, new DateTime(2014, 11, 23), "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 67.00, new DateTime(2014, 05, 05), "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6, 23.32, new DateTime(2014, 10, 18), "Newyork"));

                orderId += 6;

                empId += 6;

            }

            this.OrdersGrid.DataSource = order;

            this.OrdersGrid.DataBind();

        }



        [Serializable]

        public class Orders

        {

            public Orders()

            {



            }

            public Orders(int orderId, string customerId, int empId, double freight, DateTime orderDate, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

        }

    }

}


{% endhighlight  %}
The following output is displayed as a result of the above code example.

![](Enable-Persistence_images/Enable-Persistence_img1.png)
{:.image }


