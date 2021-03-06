---
layout: post
title: Antiforgery  | DataManager | ASP.NET Webforms | Syncfusion
description: Learn here all about Antiforgery support in Syncfusion Essential Studio ASP.NET Webforms DataManager Control, its elements, and more.
platform: aspnet
control: DataManager
documentation: ug
keywords: antiforgery, enableAntiForgery

---

# Anti Forgery Token in ASP.NET Webforms DataManager

Anti forgery tokens prevents anyone from submitting requests to your site while postback the data that are generated by a malicious script not generated by the actual user. 

For this purpose, the input element with hidden value field and name attribute is created. The value from the input element stored in cookies. To enable the anti forgery, set `enableAntiForgery` property as true.

{% highlight html %}

    <input type="hidden" name="_ejRequestVerifyToken" value="f2cd20a3-5ae1-4e19-be61-d409191be3b1">
     
{% endhighlight %}


{% highlight html %}

 <ej:TabItem ID="Grid" Text="FirstGrid" >
    <ContentSection>
           <div>
    
    <ej:DataManager runat="server" ID="DataManager" URL="Default.aspx/DataSource" UpdateURL="Default.aspx/Update"  RemoveURL="Default.aspx/Remove" InsertURL="Default.aspx/Insert" Adaptor="WebMethodAdaptor" EnableAntiForgery="true"/>
    
    <ej:Grid  runat="server"  ID="gridDistributors" EnableViewState="false" AllowPaging="true" Load="OnLoad" DataManagerID="DataManager" >      
        <Columns>
           <ej:Column Field="OrderID" HeaderText="OrderID" IsPrimaryKey="true"  TextAlign="Right" />
                <ej:Column Field="CustomerID"  HeaderText="CustomerID" />
                <ej:Column Field="EmployeeID" EditType="Dropdown"  Priority="2" HeaderText="EmployeeID"/>
                <ej:Column Field="Freight" HeaderText="Freight" Format="{0:C2}" TextAlign="Right" />   
        </Columns>
       <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" ></EditSettings>
        <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings> 
    </ej:Grid>
        </div>
            </ContentSection>
                 </ej:TabItem>


{% endhighlight %}

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object DataSource(DataManager value)
         {

            if (HttpContext.Current.Request.Cookies["_ejRequestVerifyToken"].Value == value.antiForgery)
            {
                IEnumerable data = GetAllRecords();
                var count = data.AsQueryable().Count();
                DataOperations ds = new DataOperations();
                data = ds.Execute(data, value);
                return value.RequiresCounts ? new { result = data, count = count } : data as Object;
            }
            return null;
        }

{% endhighlight %}

![anti forgery token](Antiforgery_images/Antiforgery.png)

In the header, You can find the anti-forgery token value

![anti forgery header](Antiforgery_images/Antiforgery_header.png)
