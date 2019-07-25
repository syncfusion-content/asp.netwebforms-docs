---
layout: post
title: Data binding | Menu | ASP.NET Webforms | Syncfusion
description: Menu data binding for Webforms
platform: aspnet
control: Menu
documentation: ug
---

# Data binding

Data binding enables you to synchronize the elements with different sources of data. You can bind data by using two ways, Local data and remote data. 

## Field Members

Field is a property that includes the object type. Fields are used to bind the data source and it includes the following field members to make binding easier.

<table>
<tr>
<th>
{{ '**Name**' | markdownify }}</th><th>
{{ '**Description**' | markdownify }}</th></tr>
<tr>
<td>
DataSource</td><td>
DataSource receives list that are to be added in DropDownList items. </td></tr>
<tr>
<td>
Query</td><td>
It receives query to retrieve data from the table (query is same as SQL). Example:  ej.Query().from("Categories").select("CategoryID,CategoryName").take(3);</td></tr>
<tr>
<td>
TableName</td><td>
It receives table name to execute query on the corresponding table</td></tr>
<tr>
<td>
DataIdField</td><td>
Specifies the id to menu items list</td></tr>
<tr>
<td>
DataParentIdField</td><td>
Specifies the parent id of the table to create sub menus based on this Id</td></tr>
<tr>
<td>
DataTextField</td><td>
Specifies the text of menu items list</td></tr>
<tr>
<td>
DataSpriteCssField</td><td>
Specifies the sprite CSS class to “LI” item list</td></tr>
<tr>
<td>
DataLinkAttributeField</td><td>
Specifies the link attribute to “A” tag in item list</td></tr>
<tr>
<td>
DataImageAttributeField</td><td>
Specifies the image attribute to “IMG” tag inside items list </td></tr>
<tr>
<td>
DataHtmlAttributeField</td><td>
Specifies the HTML attributes to “LI” item list</td></tr>
<tr>
<td>
DataImageUrlField</td><td>
Specifies the image URL to “IMG” tag inside item list. </td></tr>
</table>


## Remote data

The menu control also provides supports for Remote data binding. Here the remote data is placed in a Web service. Here the menu items are fetched from the web service by using Service URL. The data comes in the format of JSON. 

DataManager is used to manage relational data in JavaScript. Query generates data queries that are to be read by DataManager. 

In the following code example, [http://mvc.syncfusion.com/Services/Northwnd.svc/](http://mvc.syncfusion.com/Services/Northwnd.svc/) is used as the URL. Here, it acts as web service that is located in the Syncfusion server. The web service used here is Northwnd.svc.

Add the following code example in your ASPX page.

{% highlight html %}

<ej:Menu ID="Menu1" runat="server" DataIdField="CategoryID" DataTextField="CategoryName" Width="400px">

    </ej:Menu>



{% endhighlight %}



Add the following code example in the code behind to configure the DataSource and Query.

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

{

   Menu1.DataSource = "http://mvc.syncfusion.com/Services/Northwnd.svc/";

   Menu1.Query = "ej.Query().from('Categories').select('CategoryID,CategoryName').take(3)";

}



{% endhighlight %}



The following screenshot displays the output of the above code example. 

![Remote Data](Data-binding_images/Data-binding_img1.png) 



## SQL Data binding

SqlDataSource is designed to work with SQL Server databases. It uses the SQL Server .NET data provider internally. SQL Server .NET data provider classes are defined in the System.Data.SqlClient namespace. To bind the SqlDataSource to Menu, DataSourceID should be the id of SqlDataSource. You can select the table from SelectCommand. 

Add the following code example in your ASPX page to SQL Data binding.

{% highlight html %}



<ej:Menu ID="TreeSQL" DataTextField="Text" DataSourceID="SqlDataSource1" DataIdField="ID" DataParentIdField="ParentID" runat="server">

</ej:Menu>



<asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:TreeDBConnectionString %>"

SelectCommand="SELECT * FROM [TreeBind]"></asp:SqlDataSource>





{% endhighlight %}



The following screenshot displays the output for the above code example.                                                                                                       

![SQL Data](Data-binding_images/Data-binding_img2.png) 



## Object Data binding

The ObjectDataSource control lets you bind a specific data layer in the same manner by which you bind to the database by using other controls. The ObjectDataSource control can bind to any method that returns a DataSet or an IEnumerable object (for example, a DataReader or a collection of Classes). The major advantage of binding via ObjectDataSource is, only records that are required in the current view are retrieved from the database, greatly optimizing the performance and runtime memory usage.

Add the following code example in your ASPX page

{% highlight html %}





<ej:Menu ID="Menu1" DataSourceID="ObjectDataSource2" DataIdField="ID" DataParentIdField="ParentID" DataTextField="Text" runat="server">

    </ej:Menu>

    <asp:ObjectDataSource ID="ObjectDataSource2" runat="server" TypeName="MenuLocalDataSource" SelectMethod="GetMenuDataItems"> </asp:ObjectDataSource>





{% endhighlight %}



Define Object DataSource elements with the DataIdField, DataParentIdField and DataTextField that are to be mapped to Menu in code behind and map the list data to DataSource property.

{% highlight c# %}



public class MenuSource

    {

    }

    [Serializable]

    public class MenuLocalDataSource

    {

        //private int? ParentID;

        public MenuLocalDataSource()

        { }

        public MenuLocalDataSource(int _id, int? _parent, string _text, string _hasChild, string _expanded)

        {



            this.ID = _id;

            this.ParentID = _parent;

            this.Text = _text;

            this.HasChild = _hasChild;

            this.Expanded = _expanded;

        }

        [Browsable(true)]

        public int ID

        {

            get;

            set;

        }



        [Browsable(true)]

        public int? ParentID

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

        [Browsable(true)]

        public string HasChild

        {

            get;

            set;

        }

        [Browsable(true)]

        public string Expanded

        {

            get;

            set;

        }

        public List<MenuLocalDataSource> GetMenuDataItems()

        {

            List<MenuLocalDataSource> data = new List<MenuLocalDataSource>();

      data.Add(new MenuLocalDataSource(1, null, "Discover Music", "true", "true"));

      data.Add(new MenuLocalDataSource(2, 1, "Hot Singles", "", ""));

      data.Add(new MenuLocalDataSource(3, 1, "Rising Artists", "", ""));

      data.Add(new MenuLocalDataSource(4, 1, "Live Music", "", ""));

      data.Add(new MenuLocalDataSource(6, 1, "Best of 2013 So Far", "", ""));

      data.Add(new MenuLocalDataSource(7, null, "Sales and Events", "true", "true"));

      data.Add(new MenuLocalDataSource(8, 7, "100 Albums - $5 Each", "", ""));

      data.Add(new MenuLocalDataSource(9, 7, "Hip-Hop and R&B Sale", "", ""));

      data.Add(new MenuLocalDataSource(10, 7, "CD Deals", "", ""));

      data.Add(new MenuLocalDataSource(11, null, "Categories", "true", ""));

      data.Add(new MenuLocalDataSource(12, 11, "Songs", "", ""));

      data.Add(new MenuLocalDataSource(13, 11, "Bestselling Albums", "", ""));

      data.Add(new MenuLocalDataSource(14, 11, "New Releases", "", ""));

      data.Add(new MenuLocalDataSource(15, 11, "Bestselling Songs", "", ""));

      data.Add(new MenuLocalDataSource(16, null, "MP3 Albums", "true", ""));

      data.Add(new MenuLocalDataSource(17, 16, "Rock", "", ""));

      data.Add(new MenuLocalDataSource(18, 16, "Gospel", "", ""));

      data.Add(new MenuLocalDataSource(19, 16, "Latin Music", "", ""));

      data.Add(new MenuLocalDataSource(20, 16, "Jazz", "", ""));

      data.Add(new MenuLocalDataSource(21, null, "More in Music", "true", ""));

      data.Add(new MenuLocalDataSource(22, 21, "Music Trade-In", "", ""));

      data.Add(new MenuLocalDataSource(23, 21, "Redeem a Gift Card", "", ""));

      data.Add(new MenuLocalDataSource(24, 21, "Band T-Shirts", "", ""));

      data.Add(new MenuLocalDataSource(25, 21, "Mobile MVC", "", ""));

          return data;

        }

    }



{% endhighlight %}



The following screenshot displays the output for the above code example.  
    
![Object Data binding](Data-binding_images/Data-binding_img3.png) 



## XML Data binding

XmlDataSource is used to work with XML documents. To bind the XmlDataSource to Menu, DataSourceID of the menu has to be the id of XmlDataSource.

In the Design page, assign the values for DataTextField, DataParentIdField.In DataSourceID field assign the ID of the existing XML datasource

{% highlight html %}



<ej:Menu ID="TreeXmlDSr" runat="server" DataSourceID="XmlDataSource1" DataTextField="Item" DataParentIdField="RootItem"></ej:Menu>

        <asp:XmlDataSource ID="XmlDataSource1" runat="server" DataFile="~\App_Data\XMLData.xml"></asp:XmlDataSource>





{% endhighlight %}



Load the menu items in the XML data as illustrated in the following code example in a XML file “XMLData.xml”.

{% highlight xml %}

<?xml version="1.0" encoding="utf-8" ?>

<Items>

  <RootItem Text="Home" Expanded="True" Url="#">

    <Item Text="Foundation" Url="#"></Item>

    <Item Text="Launch" Url="#"></Item>

    <RootItem Text="About" Url="#">

      <Item Text="Company" Url="#"></Item>

      <Item Text="Location" Url="#"></Item>

    </RootItem>

  </RootItem>



  <RootItem Text="Services" Expanded="True" Url="#">

    <Item Text="Consulting" Url="#"></Item>

    <Item Text="Outsourcing" Url="#"></Item>

  </RootItem>

  <RootItem Text="About" Url="#"></RootItem>

  <RootItem Text="Contact us" Url="#">

    <Item Text="Contact Number" Url="#"></Item>

    <Item Text="Email" Url="#"></Item>

  </RootItem>



  <RootItem Text="Career" Url="#">

    <RootItem Text="Position" Url="#">

      <Item Text="Developer" Url="#"></Item>

      <Item Text="Manager" Url="#"></Item>

    </RootItem>

    <Item Text="Apply online" Url="#"></Item>

  </RootItem>

</Items>



{% endhighlight %}



The following screenshot displays the output for the XML Data binding.                                                                                                       

![XML Data binding](Data-binding_images/Data-binding_img4.png) 



## LINQ-to-SQL Data binding

The LINQ data source is used to bind Menu data via LINQ to SQL. The property ContextTypeName indicates the location of the data source. You have to mention exact table name of your database in TableName property. The id of LinqDataSource must be provided to DataSourceID of Menu. Define a LINQ-to-SQL data source in the web page and configure the data source as per your requirement by using the database.

In the Design page, assign values for DataTextField, DataIdField, DataParentIdField. In DataSourceID field assign the ID of the existing LINQ-to-SQL data source



{% highlight html %}



     <ej:Menu ID="TreeSQL" DataTextField="Text" DataSourceID="linq" DataIdField="ID"

        DataParentIdField="ParentID" runat="server">

    </ej:Menu>

    <asp:LinqDataSource ID="linq" runat="server" ContextTypeName="WebSampleBrowser.Menu.MenuLinqSQLDataContext" EntityTypeName="" TableName="TreeBinds"></asp:LinqDataSource>





{% endhighlight %}



The following screenshot displays the output for the above code example.                                                                                                       

![LINQ-to-SQL Data binding](Data-binding_images/Data-binding_img5.png) 

## Data binding from DataTable

The DataTable is a table representation of data. It provides a collection of columns and rows to store data in grid format. The menu items can be rendered from this DataTable using SQL commands. 

In the following code example, dataSource for menu is set from DataTable.
 
{% highlight html %}

      <ej:Menu ID="Menu1" runat="server"></ej:Menu>

{% endhighlight %}

{% highlight c# %}
  
    protected void Page_Load(object sender, EventArgs e)
        {
            string constr = @"Data Source=(LocalDB)\MSSQLLocalDB;AttachDbFilename=|DataDirectory|Linq_To_SQL.mdf;Integrated Security=True;Connect Timeout=30";
            SqlConnection con = new SqlConnection(constr);
            con.Open();
            SqlDataAdapter adpt = new SqlDataAdapter();
            SqlCommand command = new SqlCommand("select * from  Databinding", con); //select from corresponding table.
            adpt.SelectCommand = command;
            DataTable dt = new DataTable();
            adpt.Fill(dt);
            if (dt.Rows.Count > 0)
            {
                Menu1.DataSource = dt;
                Menu1.DataTextField = "Text";
                Menu1.DataIdField = "Id";
                Menu1.DataParentIdField = "ParentId";
                Menu1.DataBind();
            }
        }


{% endhighlight %}

Sample can be downloaded [here](http://www.syncfusion.com/downloads/support/directtrac/233237/ze/Menu921663815)

Now , the menu will be displayed as shown below

![DataTable](Data-binding_images/Data-binding_img6.png) 