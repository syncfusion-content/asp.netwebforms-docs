---
layout: post
title: Editing
description: editing
platform: aspnet
control: Grid
documentation: ug
---

# Editing

Essential Studio ASP.NET Grid has built-in support for editing Grid content. This can be achieved by defining an edit option for the Grid. You must provide toolbar support for editing records and validation support while editing the record. 

## Toolbar with edit option

Essential Studio Asp.NET Grid provides toolbar support and it can be customized. It contains the following built-in toolbar items: 

* Add
* Edit
* Delete
* Update
* Cancel

{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="90" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="90" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="70" EditType="Boolean"/>

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True">                           </EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>





{% endhighlight %}

The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img1.png)



## Cell edit type

Essential Studio Asp.Net Grid supports column edit type by using delegated controls for specific data types. They are:

* CheckBox control for boolean data type.
* NumericTextBox control for integers, double, and decimal types.
* InputTextBox control for string data types.
* DatePicker control for date data.
* DateTimePicker control for date-time data.
* DropDownList control for list of data.

The edit type of every column can be customized using the editType property.



{% highlight html %}





 <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="90" TextAlign="Right" Format="{0:MM/dd/yyyy}" EditType="DatePicker" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="80" EditType="Boolean"/>

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel,save"></ToolbarSettings>

        </ej:Grid>
{% endhighlight  %}
{% highlight c# %}


public partial class NormalEditingFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

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

                order.Add(new Orders(orderId + 1,"VINET",empId + 1,new DateTime(2014, 12, 25, 11, 30, 20),"Reims", true));

                order.Add(new Orders(orderId + 2,"TOMSP",empId + 2,new DateTime(2014, 12, 21, 10, 24, 40),"Munster",false));

                order.Add(new Orders(orderId + 3,"ANATER",empId + 3,new DateTime(2014, 10, 18, 20, 40, 34), "Berlin", true));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4,new DateTime(2014, 11, 23, 23, 4, 23), "Mexico", true));

                order.Add(new Orders(orderId + 5,"FRGYE",empId + 5,new DateTime(2014, 05, 05, 10, 8, 50),"Colcester", true));

                order.Add(new Orders(orderId + 6, "JGERT",empId + 6,new DateTime(2014, 10, 18, 06, 55, 59),"Newyork", true));

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

            public Orders(int orderId, string customerId, int empId, DateTime orderDate, string shipCity, bool verified)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

                this.Verified = verified;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

            public bool Verified { get; set; }

        }

      }

{% endhighlight %}



The following output is displayed as a result of the above code example.


![](Editing_images/Editing_img2.png)



### External DataSource for DropDown EditType Column

By default, the datasource for Dropdown Edit Column is set by Grid Control from its datasource. You can also bind external datasource to the Dropdown control of corresponding column in edit mode by using “DataSource” Grid Column property.

N> The external datasource must be given in a structure that it should contain properties “text” and  
“value” which holds the data
{% highlight html %}




<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" > 



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right"  Width="90" />

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" EditType="Numeric" />

                <ej:Column Field="ShipName" HeaderText="ShipName" Width="70" />

                <ej:Column Field="ShipCountry" HeaderText="ShipCountry" Width="90" EditType="Dropdown" />

            </Columns>



            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

</ej:Grid>
{% endhighlight %}
{% highlight c# %}




public partial class GridSample : System.Web.UI.Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {



        List<object> country = new List<object>();



       this.OrdersGrid.DataSource = new NorthwindDataContext().OrdersViews.ToList();

var index = this.OrdersGrid.Columns.FindIndex(col => col.Field == "ShipCountry");

            foreach (var val in dropdown)

            {

                country.Add(new { value = val, text = val });

            }

        this.OrdersGrid.Columns.ElementAt(index).DataSource = country;



       this.OrdersGrid.DataBind();



        }

    }

{% endhighlight  %}

The following output is displayed as a result of the above code example.

![](Editing_images/Editing_img4.png)



## Edit Template

Edit Template feature is used to create a custom editor to edit column values. Edit Template has three functions. Using EditTemplate property to achieved edit template feature.

* Create – It is used to create the control at time of initialize
* Read –  It is used to read the input value at time of save
* Write – It is used to assign the value to control at time of editing

The following code example is for Edit Template.

{% highlight html %}



    <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="90"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right"  Width="90" >

  <EditTemplate Create="create" Read="read" Write="write" />

</ej:Column>

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="80" Format="{0:C}" EditType="Numeric">

                    <NumericEditOptions DecimalPlaces="2"></NumericEditOptions>

                </ej:Column>

                <ej:Column Field="ShipName" HeaderText="ShipName" Width="150" />

                <ej:Column Field="ShipCountry" HeaderText="ShipCountry" Width="90" EditType="Dropdown" />

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>

    </div>





    <script type="text/javascript">       

        function create() {

            return $("<input>");

        }



        function write(args) {

           args.element.ejMaskEdit({ width: "100%" ,maskFormat: "9",value: args.rowdata !== undefined ? args.rowdata["EmployeeID"]: "" });

        }



        function read(args) {

            return args.ejMaskEdit("get_StrippedValue");

        }

    </script>
{% endhighlight  %}
{% highlight c# %}



namespace WebSampleBrowser.Grid

{

    public partial class EditTemplate : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int orderId = 10643;

            int empId = 0;

            for (int i = 1; i < 9; i++)

            {

                order.Add(new Orders(orderId + 1, "ALFKI", empId + 1, 32.38, "Alfreds Futterkiste ", "Germany"));

                order.Add(new Orders(orderId + 2, "ANATR", empId + 2, 11.61, "Ana Trujillo Emparedados y helados", "Mexico"));

                order.Add(new Orders(orderId + 3, "ANTON", empId + 3, 45.34, "Antonio Moreno Taquería", "Mexico"));

                order.Add(new Orders(orderId + 4, "AROUT", empId + 4, 37.28, "Around the Horn", "UK"));

                order.Add(new Orders(orderId + 5, "BERGS", empId + 5, 67.00, "Berglunds snabbköp", "Sweden"));

                order.Add(new Orders(orderId + 6, "BLONP", empId + 6, 23.32, "Blondel père et fils", "France"));

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

            public Orders(int orderId, string customerId, int empId, double freight, string shipName, string shipCountry)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.ShipName = shipName;

                this.ShipCountry = shipCountry;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public double Freight { get; set; }

            public string ShipName { get; set; }

            public string ShipCountry { get; set; }

        }

    }

}

{% endhighlight  %}

![](Editing_images/Editing_img5.png) 





## Edit Mode

Essential Studio Asp.Net Grid supports eight modes of editing feature in grid. They are:

* Normal row editing
* Inline form editing
* Inline template form editing
* Dialog editing
* Dialog template form editing
* External form editing
* External template form editing
* Batch editing


### Normal Editing


This feature allows you to edit various fields of a single record, simultaneously. The row goes to editable state. The following code example shows you how to set EditMode as Normal.

{% highlight html %}



<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="90" TextAlign="Right" Format="{0:MM/dd/yyyy}" EditType="DatePicker" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="80" EditType="Boolean"/>

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Normal"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>
		
{% endhighlight %}		
{% highlight c# %}


public partial class NormalEditingFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

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

                order.Add(new Orders(orderId + 1,"VINET",empId + 1,new DateTime(2014, 12, 25, 11, 30, 20),"Reims", true));

                order.Add(new Orders(orderId + 2,"TOMSP",empId + 2,new DateTime(2014, 12, 21, 10, 24, 40),"Munster",false));

                order.Add(new Orders(orderId + 3,"ANATER",empId + 3,new DateTime(2014, 10, 18, 20, 40, 34), "Berlin", true));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4,new DateTime(2014, 11, 23, 23, 4, 23), "Mexico", true));

                order.Add(new Orders(orderId + 5,"FRGYE",empId + 5,new DateTime(2014, 05, 05, 10, 8, 50),"Colcester", true));

                order.Add(new Orders(orderId + 6, "JGERT",empId + 6,new DateTime(2014, 10, 18, 06, 55, 59),"Newyork", true));

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

            public Orders(int orderId, string customerId, int empId, DateTime orderDate, string shipCity, bool verified)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

                this.Verified = verified;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

            public bool Verified { get; set; }

        }

      }



{% endhighlight  %}

The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img6.png) 



### Dialog Editing

The Dialog Edit feature allows you to edit data, using a dialog box that has fields associated with the data record being edited. You can only edit the data stored in the fields that you have rendered to be visible. The following code example shows you how to set EditMode as Dialog.
{% highlight html %}


   <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="90" TextAlign="Right" Format="{0:MM/dd/yyyy}" EditType="DatePicker" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="80" EditType="Boolean"></ej:Column>

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Dialog"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>







The following output is displayed as a result of the above code example.


{% endhighlight %}
![](Editing_images/Editing_img7.png)



### Inline Form Editing

This feature allows you to edit various fields of a single record, simultaneously. It is called inline because it is shown in between two rows, called as rows of control. After you have edited a row, the inline form is displayed. 
{% highlight html %}


   <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100"/>

                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="90" TextAlign="Right" Format="{0:MM/dd/yyyy}"

                    EditType="DatePicker" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="80" EditType="Boolean"></ej:Column>

            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="InlineForm"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>
{% endhighlight %}
{% highlight c# %}


public partial class NormalEditingFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

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

                order.Add(new Orders(orderId + 1,"VINET",empId + 1,new DateTime(2014, 12, 25, 11, 30, 20),"Reims", true));

                order.Add(new Orders(orderId + 2,"TOMSP",empId + 2,new DateTime(2014, 12, 21, 10, 24, 40),"Munster",false));

                order.Add(new Orders(orderId + 3,"ANATER",empId + 3,new DateTime(2014, 10, 18, 20, 40, 34), "Berlin", true));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4,new DateTime(2014, 11, 23, 23, 4, 23), "Mexico", true));

                order.Add(new Orders(orderId + 5,"FRGYE",empId + 5,new DateTime(2014, 05, 05, 10, 8, 50),"Colcester", true));

                order.Add(new Orders(orderId + 6, "JGERT",empId + 6,new DateTime(2014, 10, 18, 06, 55, 59),"Newyork", true));

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

            public Orders(int orderId, string customerId, int empId, DateTime orderDate, string shipCity, bool verified)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.OrderDate = orderDate;

                this.ShipCity = shipCity;

                this.Verified = verified;

            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public DateTime OrderDate { get; set; }

            public string ShipCity { get; set; }

            public bool Verified { get; set; }

        }

      }



{% endhighlight  %}



The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img8.png)



### External Form Editing

The External Form Edit Mode helps you edit various data entries in the Grid, one at a time, using an external edit form.

This is different from the Dialog Editing mode in that it allows you to see the other entries in the Grid while you are editing one.

You can position the edit form either in the top-right corner or the bottom-left corner (by default) of the Grid. The following code example shows you how to set EditMode as External Form.

{% highlight html %}


   <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >



              <Columns>

<ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown" />

                <ej:Column Field="OrderDate" HeaderText="Order Date" Width="90" TextAlign="Right" Format="{0:MM/dd/yyyy}"

EditType="DatePicker" />

                <ej:Column Field="Verified" HeaderText="Verified" Width="80" EditType="Boolean"></ej:Column>

            </Columns>

<EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="ExternalForm" FormPosition="BottomLeft"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>




{% endhighlight  %}
The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img9.png) 



### Template Form Editing

You can edit any of the fields pertaining to a single record of data and apply it to a template so that the same format is applied to all the other records that you may edit later.

You can also edit the fields that are not visible in the Grid using this template. You are provided with three template editing support in Grid.

* Inline template form editing
* Dialog template form editing
* External template form editing


#### Inline Template Form Editing


In Inline Template, you can specify the template inside the script tag and select the type as text/template. Only then the HTML elements defined in the template will not be displayed in the browser. You can define the template as follows. Using InlineFormTemplateID we are able to set inline template form.


{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True">



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" />



            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="InlineTemplateForm"                      InlineFormTemplateID="#template" ></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>




{% endhighlight  %}


The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img10.png)



In the above screenshot you can see that the elements are not rendered based on the type of the column. For example, in Freight column, the textbox is rendered instead of NumericTextBox.

While using template, you can change the elements that are defined in the template, to appropriate control based on the column type. 

Through the ActionCompleteGrid event, you can achieve this.

{% highlight html %}


      <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

<ClientSideEvents ActionComplete="complete" />

      </ej:Grid>
{% endhighlight %}
{% highlight js %}


<script type="text/javascript">

         function complete(args) {

            $("#EmployeeID").ejNumericTextbox({ value: parseInt($("#EmployeeID").val()) });

            $("#Freight").ejNumericTextbox({ value: parseFloat($("#Freight").val()) });

            $("#ShipCity").ejDropDownList();



            }

</script>


{% endhighlight  %}




Now, the elements defined in the templates, are changed to Asp.Net controls. You can see the entire code example for Template editing as follows.


{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>



<ClientSideEvents ActionComplete="complete" />



            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown" />



            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="InlineTemplateForm"                InlineFormTemplateID="#template">

             </EditSettings>                                                                                                        

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>
{% endhighlight  %}
{% highlight js %}


<script type="text/javascript">

function complete(args) {

            $("#EmployeeID").ejNumericTextbox({ value: parseInt($("#EmployeeID").val()) });

            $("#Freight").ejNumericTextbox({ value: parseFloat($("#Freight").val()) });

            $("#ShipCity").ejDropDownList();



        }

</script>

{% endhighlight  %}







The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img11.png) 



#### External Template Form Editing

The above mentioned procedure applies to ExternalTemplate editing feature also. Use the given code example instead of setting inlineTemplateForm as editMode. Using ExternaleFormTemplateID we are able to achieve external template form for editing.

{% highlight html %}



<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

       <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="ExternalFormTemplate"               ExternalFormTemplateID="#template"></EditSettings>

        </ej:Grid>


{% endhighlight %}
The following screenshot shows External Template Form Editing.



![](Editing_images/Editing_img12.png)



#### Dialog Template Editing

The above mentioned procedure applies to DialogTemplate editing feature also. Use the given code example instead of setting for DialogTemplate as editMode. Using DialogEditorTemplateID we are able to use dialog template form for editing.


{% highlight html %}

<ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" >

       <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="DialogTemplate" DialogEditorTemplateID="#template"></EditSettings>

        </ej:Grid>

{% endhighlight %}

The following screenshot shows Dialog Template Form Editing.



![](Editing_images/Editing_img13.png)



### Batch Editing

This feature allows you to edit various fields of the Grid, simultaneously, with the ease of Excel-like functionality in editing data.

Edited data is marked on the Grid, so that you know which fields or cells have been edited.
These markers are not shown after the updated data is rendered. The following code example shows you how to enable Excel-like editing, also called Batchediting, in Grid.
{% highlight html %}

  <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" ActionComplete="complete">

<DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"></DataManager>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" />

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" />



            </Columns>

            <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Batch"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>

        </ej:Grid>


{% endhighlight %}


The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img14.png)



When the Save or Cancel button is clicked, or performing an action before you save the edited records, the Confirmation message is displayed. 

The following screenshot shows the Confirmation Dialog box.



![](Editing_images/Editing_img15.png) 





## Validation

Essential Asp.Net Grid supports all the standard validation methods of jquery. Using this feature you can validate the value of the edited record cell before the edited record cell values are saved.

For validation you can refer the following two jquery validation script files.

1. jquery.validate.min.js
2. jquery.validate.unobtrusive.min.js

### jQuery Validation Methods


The following are jquery validation methods.

_List of jquery validation methods_

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
Required</td><td>
 Requires an element.</td></tr>
<tr>
<td>
Remote</td><td>
 Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
 Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
 Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
rangelength</td><td>
 Requires the element to be in given value range.</td></tr>
<tr>
<td>
Min</td><td>
 The element requires a given minimum.</td></tr>
<tr>
<td>
Max</td><td>
 The element requires a given maximum.</td></tr>
<tr>
<td>
range</td><td>
 Requires the element to be in a given value range.</td></tr>
<tr>
<td>
email</td><td>
 The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
 The element requires a valid url</td></tr>
<tr>
<td>
Date</td><td>
 Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
 The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
 The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
 The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
 Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
 Requires the element to be the same as another.</td></tr>
</table>


The following code example shows you how to include the jquery validation support for Grid while editing the records.

Using ValidationRules we are able to add validation rules for editing

{% highlight html %}



  <ej:Grid ID="OrdersGrid" runat="server"  AllowPaging="True">

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90">

                     <ValidationRule>

                        <ej:KeyValue Key="required" Value="true" />

                        <ej:KeyValue Key="number" Value="true" />

                    </ValidationRule>

                    </ej:Column>



                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="100" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="110" EditType="Numeric"/>

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="90" Format="{0:C}" EditType="Numeric">

<ValidationRule>

                        <ej:KeyValue Key="required" Value="true" />

                         <ej:KeyValue Key="range" Value="[0,1000]" />

                    </ValidationRule>

                </ej:Column>

               <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Normal"/>

            </Columns>

         <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Normal"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>



        </ej:Grid>
{% endhighlight %}
{% highlight c# %}


public partial class DefaultFunctionalities : System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

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

                order.Add(new Orders(orderId + 1, "VINET", empId + 1, 29.40, "Reims"));

                order.Add(new Orders(orderId + 2, "TOMSP", empId + 2,23.9 , "Munster"));

                order.Add(new Orders(orderId + 3, "ANATER", empId + 3,10.2, "Berlin"));

                order.Add(new Orders(orderId + 4, "ALFKI", empId + 4,23.6 , "Mexico"));

                order.Add(new Orders(orderId + 5, "FRGYE", empId + 5, 98.9, "Colchester"));

                order.Add(new Orders(orderId + 6, "JGERT", empId + 6,12.2, "Newyork"));

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

            public Orders(int orderId, string customerId, int empId,double freight, string shipCity)

            {

                this.OrderID = orderId;

                this.CustomerID = customerId;

                this.EmployeeID = empId;

                this.Freight = freight;

                this.ShipCity = shipCity;



            }

            public int OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public string ShipCity { get; set; }

            public double Freight{ get; set; }

        }





    }

{% endhighlight  %}

The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img16.png)



### Custom Validation

In addition to jquery validation methods, you can also add your own custom validation methods for a specific column. The following code example shows you how to specify the custom validation for a specific column.
{% highlight html %}


  <ej:Grid ID="OrdersGrid" runat="server"  AllowPaging="True">

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90">

                     <ValidationRule>

                        <ej:KeyValue Key="required" Value="true" />

                        <ej:KeyValue Key="number" Value="true" />

                    </ValidationRule>

                    </ej:Column>



                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="100" >

                <ValidationRule>

                        <ej:KeyValue Key="customRegex" Value="5" />

                       </ValidationRule>

                       </ej:Column>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="110" EditType="Numeric"/>

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="90" Format="{0:C}" EditType="Numeric">

                  <ValidationRule>

                        <ej:KeyValue Key="customCompare" Value="[1,9]" />



                    </ValidationRule>

                </ej:Column>

               <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown"/>

            </Columns>

         <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Normal"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>



        </ej:Grid>
{% endhighlight  %}
{% highlight js %}




<script type="text/javascript">

    $(function () {

        $.validator.addMethod("customCompare", function (value, element, params) {

            return element.value > params[0] && element.value < params[1]

        }, "Freight value must be between 1 and 9");



        $.validator.addMethod("customRegex", function (value, element, params) {

            if (element.value.length == params)

                return true;

            return false;

        }, "Customer ID must be 5 characters");

    });

</script>


{% endhighlight  %}


The following output is displayed as a result of the above code example.



![](Editing_images/Editing_img17.png)



## CRUD Operation With Server-Side

The Server-Side CRUD operation can be performed by using the following adaptor methods in Grid.

1. Url Adaptor
2. RemoteSaveAdaptor

The Server-Side function is declared with the following parameters for each editing functionality.

_Parameters Table_

<table>
<tr>
<th>Action</th>
<th>Parameter Name</th>
<th>Example</th>
</tr>
<tr>
<td rowspan = "2">Update, Insert</td>
<td rowspan = "2">value</td>
<td>public ActionResult Update(EditableOrder value){}</td>
</tr>
<tr>
<td>public ActionResult Insert(EditableOrder value){}</td>
</tr>
<tr>
<td>Remove</td>
<td>key</td>
<td>public ActionResult Remove(int key){}</td>
</tr>
</table>





### URL Adaptor

You can use the UrlAdaptor of DataManger when binding datasource from remote data. At initial load of Grid, using URL property of DataManager, data are fetched from remote data and binded to Grid. You can map CRUD operation in Grid to Server-Side Controller action using the properties “InsertURL”, “UpdateURL” and “RemoveURL”.

Also when you use UrlAdaptor, you need to return the data as JSON and the JSON object must contain field name as “result” with its value as dataSource and one more field name as “count” with its value as dataSource total records count.
{% highlight html %}



<ej:Grid ID="EmployeesGrid" runat="server" Load="load" Create="create" AllowPaging="true" Width="1500px" OnServerEditRow="EmployeesGrid_ServerEditRow">

                    <EditSettings AllowAdding="True" AllowEditing="True" AllowDeleting="True"></EditSettings>

                    <DataManager URL="Default.aspx/Data" UpdateURL="Default.aspx/Update" InsertURL="Default.aspx/Add" RemoveURL="Default.aspx/Delete" />

                    <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>



                    <Columns>

                        <ej:Column Field="OrderID" IsPrimaryKey="true" HeaderText="Order ID" Width="80" />

                        <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="80" />

                        <ej:Column Field="Freight" HeaderText="Freight" Width="100" EditType="Numeric" />

                        <ej:Column Field="ShipCity" HeaderText="ShipCity" Width="80" />



                    </Columns>



                </ej:Grid>

{% endhighlight  %}
{% highlight c#  %}



  public partial class _Default : Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {





        }



        [WebMethod]

        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

        public static object Data(int skip, int take)

        {



            var DataSource = OrderRepository.GetAllRecords();

            DataResult ds = new DataResult();

          ds.result=DataSource.Skip(skip).Take(take);

           ds.count= ds.count = DataSource.Count();

           return ds;



        }

      [WebMethod]

        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

        public static object Update(Order value)

      {

      NORTHWNDEntities1 obj = new NORTHWNDEntities1();

         obj.Entry(value).State = EntityState.Modified;

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }



      [WebMethod]

      [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

      public static object Delete(int key)

      {

          NORTHWNDEntities1 obj = new NORTHWNDEntities1();

          var data = obj.Orders.Find(key);



          obj.Orders.Remove(data);

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }

      [WebMethod]

      [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

      public static object Add(Order value)

      {

          NORTHWNDEntities1 obj = new NORTHWNDEntities1();

          obj.Orders.Add(value);

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }



    }
{% endhighlight  %}
### remoteSave Adaptor

The RemoteSaveAdaptor of DataManager can be used when you bind local data to Grid datasource. CRUD operations in Grid local data can be mapped to server-side controller using CRUDURL’s “InsertUrl”, “UpdateUrl” and “RemoveUrl”.

When you use RemoteSaveAdaptor, server-side post back occurs only for CRUD actions in Grid. Rest of the Grid actions(paging, sorting, filtering, etc.,) can be handled at client-side itself.

{% highlight html %}


<ej:Grid ID="EmployeesGrid" runat="server" Load="load" Create="create" AllowPaging="true" Width="1500px" OnServerEditRow="EmployeesGrid_ServerEditRow">

                    <EditSettings AllowAdding="True" AllowEditing="True" AllowDeleting="True"></EditSettings>

                    <DataManager Adaptor="remoteSaveAdaptor" UpdateURL="Default.aspx/Update" InsertURL="Default.aspx/Add" RemoveURL="Default.aspx/Delete" />

                    <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>



                    <Columns>

                        <ej:Column Field="OrderID" IsPrimaryKey="true" HeaderText="Order ID" Width="80" />

                        <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="80" />

                        <ej:Column Field="Freight" HeaderText="Freight" Width="100" EditType="Numeric" />

                        <ej:Column Field="ShipCity" HeaderText="ShipCity" Width="80" />



                    </Columns>



                </ej:Grid>

{% endhighlight  %}
{% highlight c# %}


public partial class _Default : Page

    {

        protected void Page_Load(object sender, EventArgs e)

        {



            this.EmployeesGrid.DataManager.Json = new NORTHWNDEntities1().Orders.ToList();

            this.EmployeesGrid.DataBind();



        }



      [WebMethod]

        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

        public static object Update(Order value)

      {

      NORTHWNDEntities1 obj = new NORTHWNDEntities1();

         obj.Entry(value).State = EntityState.Modified;

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }



      [WebMethod]

      [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

      public static object Delete(int key)

      {

          NORTHWNDEntities1 obj = new NORTHWNDEntities1();

          var data = obj.Orders.Find(key);



          obj.Orders.Remove(data);

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }

      [WebMethod]

      [ScriptMethod(ResponseFormat = ResponseFormat.Json)]

      public static object Add(Order value)

      {

          NORTHWNDEntities1 obj = new NORTHWNDEntities1();

          obj.Orders.Add(value);

          obj.SaveChanges();

          var dataSource = OrderRepository.GetAllRecords();

          return dataSource;

      }



    }

{% endhighlight %}

The output for the Server Binding of records is as follows:



![](Editing_images/Editing_img18.png)





![](Editing_images/Editing_img19.png)



![](Editing_images/Editing_img20.png)





## Editing Remote Data

In general, the client-side controls cannot be directly bound to SQL Server database. To access or modify the database, you must create web services that will return the JSON data, based on the request made.  DataManager can be bound to any web services. For a quick start, you can use ODataServices like WebApi, WCF DataServices.

Refer to the following steps to create WCF dataservice.

The Grid control for Asp.Net allows you to bind and edit data from the local server. Refer to the following steps to edit local server data.

1.  Open Visual Studio 2012. In the File menu, click New and select Project. The New Project Dialog box is opened.

    ![](Editing_images/Editing_img21.png)



2.  Select ASP.NETEmpty Web Application and click OK.
3.  Create empty folders named App_Data and Models in the root of the application.
4.  Add an HTML page in the root of the application. 
5.  Add the NORTHWND.MDF file into the App_Data folder, and the corresponding NORTHWND_log.ldf is created automatically.
6.  Right-click the Models folder in the Solution Explorer window and select the menu option Add New Item.
7.  In the Add New Item dialog, select the Data category.

    ![](Editing_images/Editing_img22.png)

8.  Select the ADO.NET Entity Data Model template, give the Entity Data Model the name Northwind.edmx, and click the Add button. Click Add to launch the Data Model Wizard. 
9.  In the Choose Model Contents step, choose the Generate from database option and click Next.

    ![](Editing_images/Editing_img23.png)



10. In the Choose Your Data Connection step, select the NORTHWND.MDF database connection, enter the entities connection settings name NORTHWNDEntities and click Next.

    ![](Editing_images/Editing_img24.png)



11. In the Choose Your Database Objects step, select all the database tables and click Finish.

    ![](Editing_images/Editing_img25.png)



    When you are finished, you can see the following image.



    ![](Editing_images/Editing_img26.png)



12. Right-click the Models folder in the Solution Explorer window and select the Menu option Add New Item.
13. In the Add New Item dialog, in the Web category, select WCF Data Service, enter Northwnd.svc in the Name textbox and click Add. 

    ![](Editing_images/Editing_img27.png)



14. The WCF Data Service file is created. Open the Nothwnd.svs.cs file and set the NORTHWNDEntities as a class for the DataService.

    ~~~ cs

		public class Northwnd : DataService

		</* TODO: put your data source class name here.*/>

		Replace the above line with the following:

		public class Northwnd : DataService<NORTHWNDEntities>

    ~~~
	{:.prettyprint }

15. Add the highlighted line in the Nothwnd.svs.cs.

    ~~~ cs

		public static void InitializeService(DataServiceConfiguration config)

				{

					// TODO: Set rules to indicate which entity sets and service operations are visible, updatable, etc.

					// Examples:

					// config.SetEntitySetAccessRule("MyEntityset", EntitySetRights.AllRead);

					// config.SetServiceOperationAccessRule("MyServiceOperation", ServiceOperationRights.All);

					config.DataServiceBehavior.MaxProtocolVersion = DataServiceProtocolVersion.V3;

					config.SetEntitySetAccessRule("*", EntitySetRights.All);

				}


    ~~~
	{:.prettyprint }

16. Refer to the following code sample to get the data from the local server.

    ~~~ html

		var dataManger = ej.DataManager({

						url: "/model/Northwnd.svc/Orders"

		});

    ~~~
	{:.prettyprint }

17. Add the following codes into the HTML page.


{% highlight html %}


<ej:Grid ID="OrdersGrid" runat="server"  AllowPaging="True" >

             <DataManager URL="/model/Northwnd.svc/Orders"></DataManager>

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="90"/>

                <ej:Column Field="CustomerID" HeaderText="Customer ID" Width="100"/>

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="110" EditType="Numeric"/>

                <ej:Column Field="Freight" HeaderText="Freight" TextAlign="Right" Width="90" Format="{0:C}" EditType="Numeric"/>

                <ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown"/>

            </Columns>





         <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Normal"></EditSettings>

            <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>



        </ej:Grid>


{% endhighlight  %}

The output for the above Grid creation with editing options code example is as follows.



![](Editing_images/Editing_img28.png)



## Adding New Row Position

Adding new row position allows you to add new row in the top or bottom position that depends upon the requirement. 

Grid supports two types of rowposition. They are

* Top
* Bottom

The following code example illustrates you how to set RowPosition. Using RowPosition we are able to set row position for adding.
{% highlight html %}


        <ej:Grid ID="Grid" runat="server" DataSourceID="ObjectData" AllowScrolling="True">

            <Columns>

                <ej:Column Field="OrderID" HeaderText="Order ID" TextAlign="Right"  />

                <ej:Column Field="CustomerID" HeaderText="Customer ID" />

                <ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right"   />

                <ej:Column Field="ShipCity" HeaderText="Ship City" EditType="Dropdown" />

            </Columns>

            <ScrollSettings Height="300" Width="900" ></ScrollSettings>

            <EditSettings RowPosition="Bottom” AllowAdding="True" AllowEditing="True" AllowDeleting="True" ></EditSettings>

        </ej:Grid>
{% endhighlight  %}

{% highlight c# %}


using System;

using System.Collections.Generic;

using System.Linq;

using System.Web;

using System.Web.UI;

using System.Web.UI.WebControls;



namespace WebSampleBrowser.Grid

{

    public partial class RowPosition: System.Web.UI.Page

    {

        List<Orders> order = new List<Orders>();

        protected void Page_Load(object sender, EventArgs e)

        {

            BindDataSource();

        }



        private void BindDataSource()

        {

            int code = 10000;

            for (int i = 1; i < 10; i++)

            {

                order.Add(new Orders(code + 1, i + 0, "Berlin", 2.3 * i));

                order.Add(new Orders(code + 2, i + 2, "Madrid", 3.3 * i));

                order.Add(new Orders(code + 3, i + 1, "Cholchester", 4.3 * i));

                order.Add(new Orders(code + 4, i + 3, "Marseille", 5.3 * i));

                order.Add(new Orders(code + 5, i + 4, "London", 6.3 * i));

                code += 5;

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

            public Orders(long OrderId, string CustomerId, int EmployeeId, string ShipCity )

            {

                this.OrderID = OrderId;

                this.CustomerID = CustomerId;

                this.EmployeeID = EmployeeId;

                this.ShipCity = ShipCity;

            }

            public long OrderID { get; set; }

            public string CustomerID { get; set; }

            public int EmployeeID { get; set; }

            public string ShipCity{ get; set; }

        }

    }

}


{% endhighlight  %}
The following output is displayed as a result of the above code example.



![C:/Users/ApoorvahR/Desktop/1.png](Editing_images/Editing_img29.png)



## Render grid with add new row

In Grid, there is an option toshow the newly add row at the bottom or top of the Grid content during Grid Initialize that is achieved by using ShowAddNewRow property of EditSettings in Grid. The default value is false.

This property helps you to add a new row dynamically and save the record either top or bottom of the Grid.
{% highlight html %}




     <ej:Grid ID="FlatGrid" runat="server">

       <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,save,cancel"></ToolbarSettings>

       <Columns>

            <ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey ="true" />

            <ej:Column Field="CustomerID" HeaderText="Customer ID" /> 

            <ej:Column Field="EmployeeID" HeaderText="Employee ID" />

            <ej:Column Field="ShipCity" HeaderText="Ship City" />

            <ej:Column Field="ShipCity" HeaderText="Ship Name" />

       </Columns>

       <EditSettings AllowAdding ="true" AllowEditing="true" AllowDeleting ="true" RowPosition="Bottom" ShowAddNewRow="true" ></EditSettings>

   </ej:Grid>



{% endhighlight  %}



The following screenshot is the output of the above code example.

![](Editing_images/Editing_img30.png)



