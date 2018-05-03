---
layout: post
title: Getting started with DropDownList control for Syncfusion ASP.NET WebForm
description: To get start with DropDownList by adding references.
platform: aspnet
control: DropDownList
documentation: ug
keywords: DropDownList, dropdown, Populating data
---

# Getting Started

## Creating your first DropDownList in ASP Web Forms

1. Create an ASP.NET Web Forms application and add DropDownList control to the Default.aspx page.

    ![](Getteing-Started_images/Getteing-Started_img3.jpeg)

2. Once the control is dragged and dropped into the page the embedded resource will add dependent script and CSS files from Syncfusion.EJ.Web assembly and the assembly will be referred from GAC. This will add the following appSetting key in web.config file to load resource files.

    {% highlight xml %}
        
        <appSettings>
                <add key="LoadEJResourcesFromAssembly" value="true"/>
                <add key="EJResources" value="jsrender:true;jqueryeasing:true;globalize:true;themes:true;"/>
        </appSettings>
            
    {% endhighlight %}
    
N> Refer the [ASP.NET-Getting Started](http://help.syncfusion.com/aspnet/getting-started#manual-integration-of-syncfusion-aspnet-controls-into-the-newexisting-application) Documentation to know further details about necessary assemblies, Script and CSS files.

3. Configure the DropDownList control using smart tag, to add DropDownList items

    ![](Getteing-Started_images/Getteing-Started_img4.jpeg)

    Switching from Design view to Source the DropDownList code looks like the below. Syncfusion namespace will be registered and control will be initialized from the Syncfusion.EJ.Web namespace tag prefix "ej". The items to DropDownList are added using the DropDownListItem child element under Items.

    {% highlight html %}

        <ej:DropDownList ID="DropDownList1" runat="server">
                <Items>
                    <ej:DropDownListItem ID="DropDownListItem1" runat="server" Text="ListItem 1" Value="item1">
                    </ej:DropDownListItem>
                    <ej:DropDownListItem ID="DropDownListItem2" runat="server" Text="ListItem 2" Value="item2">
                    </ej:DropDownListItem>
                    <ej:DropDownListItem ID="DropDownListItem3" runat="server" Text="ListItem 3" Value="item3">
                    </ej:DropDownListItem>
                    <ej:DropDownListItem ID="DropDownListItem4" runat="server" Text="ListItem 4" Value="item4">
                    </ej:DropDownListItem>
                    <ej:DropDownListItem ID="DropDownListItem5" runat="server" Text="ListItem 5" Value="item5">
                    </ej:DropDownListItem>
                </Items>
        </ej:DropDownList>
            
    {% endhighlight %}

4. Execute the code to get the below output

    ![](Getteing-Started_images/Getteing-Started_img1.jpeg)

## Populating data

The DropDownList can be bounded to both local list data binding like SQLDataSource, XMLDataSource, ObjectDataSource or LinqDataSource and remote data services. Assign the DataSourceID property with corresponding DataSource ID used and map the corresponding Data fields.

1. Configure the DropDownList control with SQL data source using smart tag.

    ![](Getteing-Started_images/Getteing-Started_img5.jpeg)

2. Assign the values for DropDownList Mapper fields from the properties panel.

    ![](Getteing-Started_images/Getteing-Started_img6.jpeg)

    > Create a connection string in Web.config file using SQL database.

    {% highlight xml %}
        
        <connectionStrings>
            <add name="ConnectionString" connectionString="Data Source=(LocalDB)\v11.0;AttachDbFilename=|DataDirectory|\NORTHWND.MDF;Integrated Security=True"
            providerName="System.Data.SqlClient" />
        </connectionStrings>
        
    {% endhighlight %}

Switching from Design view to Source the DropDownList code looks like the below with DataSource, DataTextField and DataValueField mapped.

    {% highlight html %}
        
            <ej:DropDownList ID="DropDownList1" runat="server" DataMember="DefaultView" DataSourceCachingMode="None" DataSourceID="SqlDataSource1" DataTextField="CustomerID" DataValueField="CustomerID" EnableIncrementalSearch="False" FilterType="Contains" MaxPopupHeight="" MaxPopupWidth="" MultiSelectMode="None" SortOrder="Ascending" VirtualScrollMode="Normal">
        </ej:DropDownList>
        <br />
        
        <asp:SqlDataSource ID="SqlDataSource1" runat="server" ConnectionString="<%$ ConnectionStrings:ConnectionString %>" SelectCommand="SELECT [CustomerID] FROM [Customers]"></asp:SqlDataSource>

    {% endhighlight %}

3. Execute the code to get the below output 

    ![](Getteing-Started_images/Getteing-Started_img2.jpeg)

## Setting Dimensions

DropDownList dimensions can be set using Width and Height Properties.
	
{% highlight html %}
	
       <ej:DropDownList ID="DropDownList1" runat="server" Width="300px" Height="50px">
            <Items>
                <ej:DropDownListItem ID="DropDownListItem1" runat="server" Text="ListItem 1" Value="item1">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem2" runat="server" Text="ListItem 2" Value="item2">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem3" runat="server" Text="ListItem 3" Value="item3">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem4" runat="server" Text="ListItem 4" Value="item4">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem5" runat="server" Text="ListItem 5" Value="item5">
                </ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
	
{% endhighlight %}

**Setting dimensions to Popup list**

PopupWidth and PopupHeight can be used to create a fixed size popup list.

{% highlight html %}
    
        <ej:DropDownList ID="DropDownList1" runat="server" Height="50px" Width="500px" PopupHeight="200px" PopupWidth="300px">
            <Items>
                <ej:DropDownListItem ID="DropDownListItem1" runat="server" Text="ListItem 1" Value="item1">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem2" runat="server" Text="ListItem 2" Value="item2">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem3" runat="server" Text="ListItem 3" Value="item3">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem4" runat="server" Text="ListItem 4" Value="item4">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem5" runat="server" Text="ListItem 5" Value="item5">
                </ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
        
{% endhighlight %}
    
## Setting and Getting Value

You can select single or multiple values from DropDownList control. To assign a value initially to the DropDownList, you can use <b>Value</b> property.

{% tabs %}
	
    {% highlight html %}
        
        <ej:DropDownList ID="DropDownList1" runat="server">
            <Items>
                <ej:DropDownListItem ID="DropDownListItem1" runat="server" Text="ListItem 1" Value="item1">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem2" runat="server" Text="ListItem 2" Value="item2">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem3" runat="server" Text="ListItem 3" Value="item3">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem4" runat="server" Text="ListItem 4" Value="item4">
                </ej:DropDownListItem>
                <ej:DropDownListItem ID="DropDownListItem5" runat="server" Text="ListItem 5" Value="item5">
                </ej:DropDownListItem>
            </Items>
        </ej:DropDownList>
        <br />
        <asp:Label runat="server" ID="Label1"></asp:Label><br />
        <ej:Button runat="server" ID="Button1" OnClick="Button1_Click" Type="Button" Text="Get value"></ej:Button>
            
	{% endhighlight %}
    
    {% highlight c# %}
        protected void Button1_Click(object Sender, Syncfusion.JavaScript.Web.ButtonEventArgs e)
        {
            Label1.Text = "Selected item value is " + DropDownList1.Value;
        }
    {% endhighlight %}

{% endtabs %}

