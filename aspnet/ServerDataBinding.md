---
layout: post
title: Server Data Binding to Syncfusion ASP.NET controls
description: Server Data Binding to Syncfusion ASP.NET controls
platform: ASP.NET
control: Introduction
documentation: ug
---
# Server Data Binding

Seamlessly data-bind to any .NET framework data source controls such as SqlDataSource, ObjectDataSource, LinqDataSource and XmlDataSource to reduce our efforts. The data source control connects to a data source such as a database or middle-tier object and then retrieves or updates data. The data-bound control can then use this data. To perform the binding, you set the data-bound control's DataSourceID property to point to a data source control. When a data-bound control is bound to a data source control, little or no additional code is required for data operations, because the data-bound control can automatically take advantage of the data services provided by the data source control.

DropDownList supports binding to all DataSource components, including:

* SqlDataSource
* LinqDataSource
* EntityDataSource
* ObjectDataSource
* XmlDataSource

To bind to a DataSource component, all you need to do is set the DataSourceID property of DropDownList to the ID of the DataSource component. You should also set the DataTextField and DataValueField properties of DropDownList to map the Text and Value properties of the items to the respective columns / fields from the data source.

## SqlDataSource

{% highlight html %}

    <ej:DropDownList ID="DrpDwnsql" runat="server" 
        DataTextField="text" 
        DataValueField="id" 
        DataSourceID="SqlDataSource1" WatermarkText="Select a Transport" Width="100%">
    </ej:DropDownList>

    <asp:SqlDataSource ID="SqlDataSource1" runat="server" 
        SelectCommand="SELECT * FROM [Vehicle]"
        ConnectionString='<%$ ConnectionStrings:Linq_To_SQLConnectionString %>'
        ProviderName='<%$ ConnectionStrings:Linq_To_SQLConnectionString.ProviderName %>'>
    </asp:SqlDataSource>

{% endhighlight %}

For more information, see  [Binding SqlDataSource To DropDownList](https://help.syncfusion.com/aspnet/dropdownlist/datasource#sqldatasource)

## LinqDataSource

{% highlight html %}

    <ej:DropDownList ID="DrpDwnsql" runat="server" Width="100%"
        DataTextField="Text"  
        DataValueField="Id" 
        DataSourceID="LinqDataSource1" WatermarkText="Select an Album">
    </ej:DropDownList>

    <asp:LinqDataSource ID="LinqDataSource1" runat="server" 
        ContextTypeName="WebSampleBrowser.database.Linq_Common_DataDataContext" EntityTypeName="" 
        TableName="Databindings">
    </asp:LinqDataSource>

{% endhighlight %}

For more information, see  [Binding LinqDataSource To DropDownList](https://help.syncfusion.com/aspnet/dropdownlist/datasource#linqdatasource)

## EntityDataSource

{% highlight html %}

    <ej:DropDownList ID="DrpDwnsql" runat="server" Width="100%"
        DataTextField="ContactName"  
        DataValueField="ContactName" 
        DataSourceID="EntityDataSource1" WatermarkText="Select a Customer">
    </ej:DropDownList>

    <asp:EntityDataSource ID="EntityDataSource1" runat="server" 
        ConnectionString="name=NorthwindEntities35"
        DefaultContainerName="NorthwindEntities35" EntitySetName="Customers" Select="it.[ContactName], it.[City], it.[ContactTitle]"
        AutoPage="true" OrderBy="it.[ContactName]">
    </asp:EntityDataSource>

{% endhighlight %}

For more information, see  [Binding EntityDataSource To DropDownList](https://help.syncfusion.com/aspnet/dropdownlist/datasource#entitydatasource)

## ObjectDataSource

{% highlight html %}

   <ej:DropDownList ID="Transportlist" runat="server"
        DataSourceID="ObjectDataSource1"
        DataTextField="Text" 
        DataValueField="ID" WatermarkText="Select a Transport" Width="100%">
    </ej:DropDownList>

    <asp:ObjectDataSource ID="ObjectDataSource1" runat="server" 
        TypeName="TabData" SelectMethod="GetItems">
    </asp:ObjectDataSource>

{% endhighlight %}

GetItems methods returns the DropDownList's items, let we define the GetItems method as follows,

{% highlight html %}

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

For more information, see  [Binding ObjectDataSource To DropDownList](https://help.syncfusion.com/aspnet/dropdownlist/datasource#objectdatasource)

## XmlDataSource

{% highlight html %}

    <ej:DropDownList ID="DrpDwnxml" DataMember="RootItem" 
        DataTextField="Text" 
        DataValueField="Text" runat="server" 
        DataSourceID="XmlDataSource1" WatermarkText="Select a Product" Width="100%">
    </ej:DropDownList>

    <asp:XmlDataSource ID="XmlDataSource1" runat="server" 
        DataFile="~/App_Data/XMLData.xml">
    </asp:XmlDataSource>


{% endhighlight %}

When using an XmlDataSource, the XML file should have the format shown below:

{% highlight html %}

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

For more information, see  [Binding XmlDataSource To DropDownList](https://help.syncfusion.com/aspnet/dropdownlist/datasource#xmldatasource)




