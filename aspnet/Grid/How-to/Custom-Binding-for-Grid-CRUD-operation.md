---
layout: post
title: Custom Binding for Grid CRUD operation | Grid | ASP.NET Webforms | Syncfusion
description: custom binding for grid crud operation
platform: aspnet
control: Control Name undefined
documentation: ug
---

### Custom Binding for Grid CRUD operation

In Grid control, DataManager is used for data processing. The adaptors of dataManager are customizable that can be extended for custom Binding with server-side for Grid CRUD operation.

For instance, bind the data to Grid by using “remoteSaveAdaptor” and extend it to modify its update method to bind the edited record values of Grid as “FormCollection” in server-side.

{% tabs %}

{% highlight html %}
        <ej:Grid ID="EmployeesGrid" runat="server" Load="load" AllowPaging="true" Width="1500px">

                    <EditSettings AllowAdding="True" AllowEditing="True" AllowDeleting="True"&gt;&lt;/EditSettings>

                    <DataManager Adaptor="remoteSaveAdaptor" UpdateURL="Default.aspx/Update" InsertURL="Default.aspx/Add" RemoveURL="Default.aspx/Delete">

                    <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

                    <Columns>

                        <ej:Column Field="OrderID" IsPrimaryKey="true" HeaderText="Order ID" Width="80" />

                        <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="80" />

                        <ej:Column Field="Freight" HeaderText="Freight" Width="100" EditType="Numeric" />

                        <ej:Column Field="ShipName" HeaderText="ShipName" Width="80" />

                    <Columns>

         </ej:Grid>


{% endhighlight %}

{% highlight js %}


var adaptor = new ej.remoteSaveAdaptor().extend({

        insert: function (dm, data, tableName) {

            return {

                url: dm.dataSource.insertUrl,

                dataType: 'json',

                contentType: "application/x-www-form-urlencoded; charset=utf-8",

                data: $("#EmployeesGridEditForm").serialize()

            };

        },

        update: function (dm, keyField, value, tableName) {

            return {

                type: "POST",

                url: dm.dataSource.updateUrl+"?id="+value.OrderID,

                dataType: 'json',

                contentType: "application/x-www-form-urlencoded; charset=utf-8",

                data: $("#EmployeesGridEditForm").serialize()

            };

        },

    })



    function load(args) {

        this.model.dataSource.adaptor = new adaptor();

    }



{% endhighlight  %}


{% highlight c# %}

public partial class GridSample : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {

            this.EmployeesGrid.DataManager.Json = new NORTHWNDEntities1().Orders.ToList();

            this.EmployeesGrid.DataBind();

        }

        [WebMethod]

        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

        public static object Update(int id, FormCollection value)

        {

            var ord = new EditableOrder();

            ord.OrderID = id;

            if (value["EmployeeID"] != "")

            ord.EmployeeID = Convert.ToInt32(value["EmployeeID"]);

            if (value["Freight"] != "")

            ord.Freight = Convert.ToDecimal(value["Freight"]);

            if (value["ShipCity"] != null)

            ord.ShipCity = value["ShipCity"];

            OrderRepository.Update(ord);
            var data = new NORTHWNDEntities1().Orders.ToList();

            return Json(data, JsonRequestBehavior.AllowGet);

      }

       public static object Insert(FormCollection value)

        {

            var ord = new EditableOrder();

            ord.OrderID = Convert.ToInt32(value["OrderID"]);

            if (value["EmployeeID"] != "")

                ord.EmployeeID = Convert.ToInt32(value["EmployeeID"]);

            if (value["Freight"] != "")

                ord.Freight = Convert.ToDecimal(value["Freight"]);

            if (value["ShipCity"] != null)

                ord.ShipCity = value["ShipCity"];

            OrderRepository.Add(ord);

            var data new NORTHWNDEntities1().Orders.ToList();

            return Json(data, JsonRequestBehavior.AllowGet);

        }

    }

}

{% endhighlight %}

{% endtabs %}
The output is as follows.

{% include image.html url="/aspnet/Grid/How-to/Custom-Binding-for-Grid-CRUD-operation_images/Custom-Binding-for-Grid-CRUD-operation_img1.png"%}
































