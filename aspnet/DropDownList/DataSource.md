---
layout: post
title: CheckBox with DropDownList widget for Syncfusion ASP.NET WebForm
description: Describes about Checkbox functionalities in DropDownList control for Syncfusion ASP.NET WebForm
platform: aspnet
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, data binding, SQL, LINQ, Xml, Entity, Access
---

# Data Source

ASP.NET includes data source controls that allow you to work with different types of data sources such as a database, an XML file, or a middle-tier business object. Data source controls connect to and retrieve data from a data source and make it available for other controls (DropDownList, Grid, Schedule) to bind to, without requiring code. They can also support modifying data.

## SqlDataSource

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

## LinqDataSource

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
            data.Add(new DropDownData(9, "Aero planes"));
            data.Add(new DropDownData(10,"Helicopters"));
            data.Add(new DropDownData(11,"Ships"));
            data.Add(new DropDownData(12,"Submarines"));
            return data;
        }

    }

{% endhighlight %}

Output of the above steps.

![](Databinding_images/Data-binding_img8.png)

## XmlDataSource

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

## EntityDataSource

Bind data to the DropDownList through Entity Framework. Please follow the below steps.

1.	Create an entity data model

Please refer the [link](http://www.entityframeworktutorial.net/EntityFramework5/create-dbcontext-in-entity-framework5.aspx) for more information.

2.	Refer the entity data model to your project and bind the data to the DropDownList

In code behind, create an object for the Entity mode (NORTHWNDEntities) and fetch the data from the Employees class and stored it to the List.
Assign the data to the DropDownList’s DataSource property. Specify the column names in the fields property.

{% highlight html %}

    using EntityDataBinding.Models;
    using System.Data.Entity;
    
    protected void Page_Load(object sender, EventArgs e)
    {
        NORTHWNDEntities sample = new NORTHWNDEntities();
        var dataset = sample.Employees
                    .Select(x => new Employee
                    {
                        EmployeeID = x.EmployeeID,
                        FirstName = x.FirstName                     
                    }).ToList();
        DropDownList1.DataSource = dataset;
    }
    public class Employee
    {
        public int EmployeeID { get; set; }
        public string FirstName { get; set; }
    }
    
{% endhighlight %}

{% highlight html %}

    <ej:DropDownList ID="DropDownList1" DataTextField="FirstName" DataValueField="EmployeeID" runat="server"> </ej:DropDownList>
    
{% endhighlight %}

## AccessDataSource

The data can also be bound to the DropDownList using OLEDB database as depicted below

{% highlight html %}

    <ej:DropDownList ID="DropDownList2"  DataTextField="Name" DataValueField="ID" runat="server"></ej:DropDownList>
    
{% endhighlight %}

The server-side code to retrieve and bind the data to DropDownList are as follows. Also, define a class with all the required fields as depicted in the below code example.

{% highlight html %}

    using System.Data.OleDb;
    protected void Page_Load(object sender, EventArgs e)
    {
        
        OleDbConnection conn = new OleDbConnection(@"Provider=Microsoft.Jet.OLEDB.4.0;Data Source=|DataDirectory|\Database.mdb");
        conn.Open();
        OleDbCommand cmd = new OleDbCommand(" SELECT * from [Employees]", conn);
        OleDbDataReader reader = null;
        List<Details> data = new List<Details>();
        reader = cmd.ExecuteReader();
        while (reader.Read())
        {
            data.Add(new Details(reader["Name"].ToString(), reader["Designation"].ToString())); 
        }
        conn.Close();
        DropDownList2.DataSource = data;

    }
    public class Details
    {
        public string Name { get; set; }
        public string Designation { get; set; }
        public Details(string name, string deg)
        {
            this.Name = name;
            this.Designation = deg;

        }
    }

{% endhighlight %}

## LINQ to SQL Data Source

The LINQ to SQL can be used as the data source of the DropDownList in which the data model of a relational database is mapped to an object model and allow us to use the LINQ technology to access SQL database.

The following code example describes the above behavior.

{% highlight html %}

    <ej:DropDownList ID="DrpDwnsql" runat="server" DataTextField="Text" Width="100%" DataValueField="Id" DataSourceID="LinqDataSource1" WatermarkText="Select an Album">
    </ej:DropDownList>


    <asp:LinqDataSource ID="LinqDataSource1" runat="server" ContextTypeName="WebSampleBrowser.database.Linq_Common_DataDataContext" EntityTypeName="" TableName="Databindings"></asp:LinqDataSource>

{% endhighlight %}