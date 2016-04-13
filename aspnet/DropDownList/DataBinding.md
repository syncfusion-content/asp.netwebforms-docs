---
layout: post
title: Data binding in DropDownList control for Syncfusion ASP.NET WebForm
description: Describes about the data binding in DropDownList control for Syncfusion ASP.NET WebForm
platform: Web
control: DropDownList
documentation: ug
---

# Data Binding

To populate data in the DropDownList control, define DataSource property with associated fields. You can bind any list, database and other remote services in the DropDownList.

## Fields

The following properties provides you a way to bind either local or remote data to the DropDownList control.
<table>
    <tr>
        <th>
            Properties
            <br/>
        </th>
        <th>
            Description
            <br/>
        </th>
    </tr>
    <tr>
        <td>
            DataSource
            <br/>
        </td>
        <td>
            The data source contains the list of data for generating the popup list items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Query
            <br/>
        </td>
        <td>
            It specifies the query to retrieve the data from the online server.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Fields
            <br/>
        </td>
        <td>
            It specifies the mapping fields for the data items of the DropDownList control.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ID
            <br/>
        </td>
        <td>
            It specifies the ID of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Text
            <br/>
        </td>
        <td>
            It specifies the text content of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Value
            <br/>
        </td>
        <td>
            It specifies the value of the tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Category
            <br/>
        </td>
        <td>
            It is used to categorize the items based on a specific field. The value mapped to this field must be able to group the popup items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ImageUrl
            <br/>
        </td>
        <td>
            It defines the image location.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            ImageAttributes
            <br/>
        </td>
        <td>
            It defines the image attributes such as height, width, styles, etc.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            SpriteCssClass
            <br/>
        </td>
        <td>
            It defines the sprite CSS for the image tag to add a prefix icon to all popup items.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            HtmlAttributes
            <br/>
        </td>
        <td>
            It defines the HTML attributes such as class and styles for an item.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            Selected
            <br/>
        </td>
        <td>
            This field defines the tag value to be selected initially. Corresponding field mapped has Boolean values to select the list items on control creation. The data with value true in this field is selected automatically when the control is initialized with checkbox.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            TableName
            <br/>
        </td>
        <td>
            It defines the table name for the tag value or displays text while rendering remote data.
            <br/>
        </td>
    </tr>
     <tr>
        <td>
            DataIdField
            <br/>
        </td>
        <td>
            It specifies the ID field name that is to be mapped.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSourceID
            <br/>
        </td>
        <td>
            Specifies the ID of the DataSource.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataMember
            <br/>
        </td>
        <td>
            Specifies the member in a data source to bind to the data list control.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataTextField
            <br/>
        </td>
        <td>
            It specifies the name of the column value that binds the DropDownList text.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataValueField
            <br/>
        </td>
        <td>
            It specifies the value field to be bound.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataImageUrlField
            <br/>
        </td>
        <td>
            It maps the imageURL field name that have the image location.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataImageAttributesField
            <br/>
        </td>
        <td>
            It maps the field name that has image attributes such as height, width, styles, etc.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSpriteCssField
            <br/>
        </td>
        <td>
            It maps to the field having sprite CSS for the image tag.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataHtmlAttributesField
            <br/>
        </td>
        <td>
            It maps the field name that has the HTML attributes such as ID, class, styles for the item.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataSelectedField
            <br/>
        </td>
        <td>
            This field defines the tag value to be selected initially. Corresponding field that is mapped has boolean values to select the list items on control creation. The data with value true in this field is selected automatically when the control is initialized.
            <br/>
        </td>
    </tr>
    <tr>
        <td>
            DataTableNameField
            <br/>
        </td>
        <td>
            It defines the table name for tag value or displays text while rendering remote data.
            <br/>
        </td>
    </tr>
</table>

## Local Data

Define a List data and initialize the control with DataSource property. Specify the column names in the Fields property. <br/>

N> The columns are bounded automatically when the fields are specified with the default names like id, text, etc...

{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="Text" DataValueField="Country" DataGroupByField="Role" DataImageUrlField="Image" DataImageAttributesField="ImgAttr"></ej:DropDownList>
	
    {% endhighlight %}
    
    {% highlight css %}

    	.imgId {
        	margin: -7px;
        	padding: 3px 10px 3px 3px;
        	border: 0 none;
        	width: 60px;
        	height: 60px;
        	float: none;
    	}

    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Employee> EmpData = new List<Employee>();
            EmpData.Add(new Employee
            {
                Text = "Erik Linden",
                Role = "Executive",
                Country = "England",
                Image = "../Content/Employees/3.png",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "John Linden",
                Role = "Representative",
                Country = "Norway",
                Image = "../Content/Employees/6.png",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "Louis",
                Role = "Representative",
                Country = "Australia",
                Image = "../Content/Employees/7.png",
                ImgAttr = "class='imgId'"
            });
            EmpData.Add(new Employee
            {
                Text = "Lawrence",
                Role = "Executive",
                Country = "India",
                Image = "../Content/Employees/8.png",
                ImgAttr = "class='imgId'"
            });
            DropDownList1.DataSource = EmpData;
        }
        public class Employee
        {
            public string Text { get; set; }
            public string Role { get; set; }
            public string Country { get; set; }
            public string Image { get; set; }
            public string ImgAttr { get; set; }
        }
    {% endhighlight %}
    
{% endtabs %}


![](DataBinding_images/DataBinding_img1.jpeg)

N> Images for this sample are available in (installed location)\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\samples\web\themes\images<br/> 

## SQLDataSource

SqlDataSource is designed to work with SQL Server databases. It uses internally, the SQL Server .NET data provider. SQL Server .NET data provider classes are defined in the System.Data.SqlClient namespace. 

The following step explains the details about the data binding from SQLDataSource. 

In the ASPX page, add DropDownList.

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="text" DataValueField="id" DataSourceID="SqlDataSource1"> </ej:DropDownList>

    <asp:SqlDataSource ID="SqlDataSource1" runat="server" SelectCommand="SELECT [id], [text] FROM [Vehicle]"ConnectionString='<%$ ConnectionStrings:DatabindingConnectionString %>'></asp:SqlDataSource>

{% endhighlight %}



 Create a data table in .mdf format with the following structure and add it in APP_Data folder 


![](Databinding_images/Data-binding_img2.png)



Add connection string in the Web.config file.

N> Change the username with your system name in the following connection string.



{% highlight xml %}

    <configuration>

    <connectionStrings>

        <add name="DatabindingConnectionString" connectionString="Data Source=SystemName;Initial Catalog=Databinding;Integrated Security=True"

        providerName="System.Data.SqlClient" />

    </connectionStrings>

    </configuration>


{% endhighlight %}



Output of the above steps.

![](Databinding_images/Data-binding_img4.png)



## LINQDataSource

LinqDataSource is designed to work with DataContext. It uses internally, the data model (dbml) file. Data model contains list of tables from specific database. 

The following step explains the details about the data binding from LinqDataSource. 

In the ASPX page, add DropDownList.



{% highlight html %}

    <ej:DropDownList ID="DropDownList1" Width="200px" DataTextField="text" DataValueField="id" DataSourceID="LinqDataSource1" runat="server"> </ej:DropDownList>

    <asp:LinqDataSource ID="LinqDataSource1" runat="server" ContextTypeName="dropdownlist.Database.common_datamodelDataContext"

        TableName="Vehicles" EntityTypeName="">

    </asp:LinqDataSource>


{% endhighlight %}



Create a table in .mdf format by using the following table structure. Create a dbml file in APP_DATA folder and drag and drop table into it. 



![](Databinding_images/Data-binding_img5.png)



Add connection String in the Web.config file.


N> Change the username with your system name in the following connection string.



{% highlight xml %}

    <configuration>

    <connectionStrings>

        <add name="DatabindingConnectionString" connectionString="Data Source=SystemName;Initial Catalog=Databinding;Integrated Security=True"

        providerName="System.Data.SqlClient" />

    </connectionStrings>

    </configuration>

{% endhighlight %}

Output of the above steps

![](Databinding_images/Data-binding_img7.png)



## ObjectDataSource

The ObjectDataSource control allows you to bind a specific data layer in a similar manner where other controls bind to the database.The ObjectDataSource control can bind to any method that returns a DataSet or an IEnumerable object. For example, a DataReader or a collection of Classes. The major advantage of binding via ObjectDataSource is only the records required in the current view are retrieved from the database, greatly optimizing the performance and runtime memory usage. 

The following steps explain the details about the data binding from ObjectDataSource.

In the ASPX page, add DropDownList.

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" Width="200px" DataTextField="Text" DataValueField="ID" DataSourceID="ObjectDataSource1" runat="server"> </ej:DropDownList>

    <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" TypeName="DropDownData" SelectMethod="GetItems"> </asp:ObjectDataSource>

{% endhighlight %}



Create new CS file in App_Data folder and name as ‘Data.cs’ and add the following codes in the page. 

{% highlight c# %}

    public class DropDownData

    {

        public DropDownData(int _id,string _text)

        {

            this.ID = _id;

            this.Text = _text;

        }

        public DropDownData() { }

        [Browsable(true)]

        public int ID

        {

            get;

            set;

        }
        
        [Browsable(true)]

        public string Text

        {

            get;

            set;

        }

        public List<DropDownData> GetItems()

        {

            List<DropDownData> data = new List<DropDownData>();

            data.Add(new DropDownData(1, "Railways"));

            data.Add(new DropDownData(2, "Roadways"));

            data.Add(new DropDownData(3, "Airways"));

            data.Add(new DropDownData(4, "Waterways"));

            data.Add(new DropDownData(5, "Electric Trains"));

            data.Add(new DropDownData(6, "Diesel Trains"));

            data.Add(new DropDownData(7, "Heavy Motor Vehicles"));

            data.Add(new DropDownData(8, "Light Motor Vehicles"));

            data.Add(new DropDownData(9, "Aeroplanes"));

            data.Add(new DropDownData(10,"Helicopters"));

            data.Add(new DropDownData(11,"Ships"));

            data.Add(new DropDownData(12,"Submarines"));

            return data;

        }

    }


{% endhighlight %}



Output of the above steps.

![](Databinding_images/Data-binding_img8.png)



## XMLDataSource

XmlDataSource is used to work with XML documents. The following steps explain the details about the data binding from XmlDataSource.

In the ASPX page, add DropDownList. 

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" runat="server" Width="200px" DataValueField="Id" DataTextField="Text" DataSourceID="XmlDataSource1" DataMember="Items"> </ej:DropDownList>

    <asp:XmlDataSource ID="XmlDataSource1" runat="server" DataFile="~/App_Data/XMLData.xml"> </asp:XmlDataSource>

{% endhighlight %}

Create new XML file in App_Data folder as ‘XMLData.xml’ and add the following codes in the page. 

{% highlight xml %}

    <Items>

        <Item Id="1" Text=" Railways">

        </Item>

        <Item Id="2" Text="Roadways">

        </Item>

        <Item Id="3" Text="Airways">

        </Item>

        <Item Id="4" Text="Waterways">

        </Item>

        <Item Id="5" Text="Electric Trains">

        </Item>

    </Items>



{% endhighlight %}



Output of the above steps

![](Databinding_images/Data-binding_img9.png)

## Remote data 

To bind remote data to the DropDownList, you can assign a service data as an instance of DataManager to the Datasource property.

### OData

OData is a standardized protocol for creating and consuming data. You can provide the [OData service](http://www.odata.org/) URL directly to the Datasource URL property.

{% highlight html %}
    
    <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipName" DataValueField="ShipCountry"></ej:DropDownList>
    
{% endhighlight %}

{% highlight c# %}
    
    protected void Page_Load(object sender, EventArgs e)
    {
        DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
    }

{% endhighlight %}
           
## Virtual Scrolling 

To improve the performance when displaying large data set, you can use “AllowVirtualScrolling” and VirtualScrollMode property. This retrieves only a fixed amount of list items and loads remaining data on scrolling. The items will be fetched via AJAX request.

This supports two modes of virtualization. They are,

* Normal Mode
* Continuous Mode

I> 1. Sorting and Grouping is not supported with Virtual Scrolling
I> 2. “VirtualScrollMode” property accepts Syncfusion.JavaScript.VirtualScrollMode enum value.

### Normal Mode

It loads the data on scrolling the list of items. This can be achieved by setting Syncfusion.JavaScript.VirtualScrollMode.Normal value to the VirtualScrollMode property.


{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipCountry" DataValueField="ShipCountry" AllowVirtualScrolling="true" VirtualScrollMode="Normal" ItemsCount="7">
	
    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
        }
        
    {% endhighlight %}
    
{% endtabs %}


### Continuous Mode

It loads the set of items when the scroller reaches at the end. This behaves like infinity scrolling. So when scroll reaches the end, it will fetch the remaining set of items and bind with your DropDownList. This can be achieved by setting Syncfusion.JavaScript.Continuous value to the "VirtualScrollMode" property.

N> In both modes, set of items will be fetched based on the count specified in the ItemsCount property and next set of items will be loaded on scrolling.

{% tabs %}

	{% highlight html %}
       
       <ej:DropDownList ID="DropDownList1" runat="server" DataTextField="ShipCountry" DataValueField="ShipCountry" AllowVirtualScrolling="true" VirtualScrollMode="Continuous" ItemsCount="7">
	
    {% endhighlight %}
    
    {% highlight c# %}
        protected void Page_Load(object sender, EventArgs e)
        {
            DropDownList1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/Orders";
        }
        
    {% endhighlight %}
    
{% endtabs %}