---
layout: post
title: Set-Dynamic-DataSource-to-Grid
description: set dynamic datasource to grid
platform: aspnet
control: Grid
documentation: ug
---

### Set Dynamic DataSource to Grid

Grid control is capable of updating its dataSource as and when required. Grid method “dataSource” helps in achieving this and in this method parameter, you have to pass the new dataSource as json array.

For instance, consider a textbox above Grid and depending on its value, you can update a new datasource to Grid dynamically.



[ASPX]



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

    &lt;div&gt;

        Enter EmployeeID Field Value:

        &lt;input type="text" id="colValue" /&gt;

        &lt;ej:Button ID="customButton" runat="server" Size="Normal" ClientSideOnClick="btnClick" Text="Change DataSource"&gt;&lt;/ej:Button&gt;

        &lt;ej:Grid ID="FlatGrid" runat="server" AllowSorting="True" AllowPaging="True"&gt;

            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="True" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="75" Format="{0:C}" /&gt;

                &lt;ej:Column Field="OrderDate" HeaderText="Order Date" TextAlign="Right" Width="80" Format="{0:MM/dd/yyyy}" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="110" /&gt;

            &lt;/Columns&gt;

        &lt;/ej:Grid&gt;

    &lt;/div&gt;

&lt;/asp:Content&gt;



&lt;script type="text/javascript"&gt;





function btnClick(args) { //updating dataSource in an external button click event

            var obj = $("#Grid").ejGrid("instance");

            var value = $("#colValue").val();

            //Add custom paramter to the server

            var query = new ej.Query().addParams("EmployeeID", value);



            //Creating ejDataManager with UrlAdaptor



            var dm = ej.DataManager({ url: "GridSample.aspx/GetData", adaptor: new ej.UrlAdaptor() });



            var promise = dm.executeQuery(query);



            promise.done(function (e) {

                //Assign the result to the grid dataSource using "dataSource" method.

                obj.dataSource(e.result);

            });



}

&lt;/script&gt;



[ASPX.CS]

public partial class GridSample : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            this.FlatGrid.DataSource = new DataClasses1DataContext().Orders.ToList();   

            this.FlatGrid.DataBind();

        }

[WebMethod]
[ScriptMethod(ResponseFormat = ResponseFormat.Json)]
public static object GetData(int EmployeeID)

        {

            var data = new DataClasses1DataContext().Orders.Where(ds => ds.EmployeeID ==  EmployeeID).ToList();

            return Json(data, JsonRequestBehavior.AllowGet);

        }

    }



The following screenshot illustrates the output.

{ ![C:/Users/ApoorvahR/Desktop/1.png](Set-Dynamic-DataSource-to-Grid_images/Set-Dynamic-DataSource-to-Grid_img1.png) | markdownify }
{:.image }


