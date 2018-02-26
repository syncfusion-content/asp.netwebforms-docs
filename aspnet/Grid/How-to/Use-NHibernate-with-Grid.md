---
layout: post
title: Use NHibernate with Grid | Grid | ASP.NET Webforms | Syncfusion
description: use nhibernate with grid
platform: aspnet
control: Grid
documentation: ug
---

## Use NHibernate with Grid

### NHibernate

NHibernate is an object-relational mapping (ORM) solution for the Microsoft .NET platform. It provides a Framework for mapping an object-oriented domain model to a traditional relational database.

### Populate Grid with data by using NHibernate

You can populate the Grid with data obtained by using NHibernate. The UrlAdaptor can be used for data binding and to handle the request and response from the server. You can use the CRUD URL mappers (InsertUrl/UpdateUrl/RemoveUrl/CrudUrl) to provide the action/method to be called while editing.

The Grid initialization is as follows.

{% tabs %}

 {% highlight html %}


<ej:Grid ID="Grid" runat="server" AllowPaging="true">

        <DataManager URL="Default.aspx/GetData" InsertURL="Default.aspx/PerformInsert" UpdateURL="Default.aspx/PerformUpdate" RemoveURL="Default.aspx/PerformDelete" Adaptor="UrlAdaptor" />

        <EditSettings AllowAdding="true" AllowEditing="true" AllowDeleting="true" EditMode="Normal" />

        <ToolbarSettings ShowToolbar="true" ToolbarItems="add,edit,delete,update,cancel" />

        <Columns>

            <ej:Column Field="EmployeeID" HeaderText="Employee ID" IsPrimaryKey="true" TextAlign="Right" />

            <ej:Column Field="FirstName" HeaderText="First Name" />

            <ej:Column Field="LastName" HeaderText="Last Name" />

            <ej:Column Field="Designation" HeaderText="Designation" />

        </Columns>

</ej:Grid>

 {% endhighlight %}


 {% highlight c# %}






public partial class _Default : Page

{



        protected void Page_Load(object sender, EventArgs e)

        {



        }

        [WebMethod]

        [ScriptMethod(ResponseFormat=ResponseFormat.Json)]

        public static object GetData() { 



          ISession session = AppSession.OpenSession();



          list = session.Query<EmployeeMap>().ToList();



          return new DTO(){ result = list, count = list.Count }

        }



        [WebMethod]

        [ScriptMethod(ResponseFormat=ResponseFormat.Json)]

       public static object PerformInsert(string action, EmployeeMap value) { 



         ISession session = AppSession.OpenSession();



         ITransaction transaction = session.BeginTransaction();



         session.Save(value);

         transaction.Commit();



           list = session.Query<EmployeeMap>().ToList();



           return new DTO(){ result = list, count = list.Count }



       }



       [WebMethod]

       [ScriptMethod(ResponseFormat=ResponseFormat.Json)]

       public static object PerformUpdate(int key, EmployeeMap value) { 



          ISession session = AppSession.OpenSession();



          var employeeToUpdate = session.Get<EmployeeMap>(key);



            employeeToUpdate.Designation = value.Designation;

            employeeToUpdate.FirstName = value.FirstName;

            employeeToUpdate.LastName = value.LastName;



             ITransaction transaction = session.BeginTransaction();              

             session.Save(employeeToUpdate);

             transaction.Commit();               



             list = session.Query<EmployeeMap>().ToList();            



           return new DTO(){ result = list, count = list.Count }



       }



       [WebMethod]

       [ScriptMethod(ResponseFormat=ResponseFormat.Json)]

       public static object PerformDelete(int key, EmployeeMap value) { 



         ISession session = AppSession.OpenSession();

         ITransaction transaction = session.BeginTransaction();

         session.Delete(session.Get<EmployeeMap>(key));

         transaction.Commit();                



         list = session.Query<EmployeeMap>().ToList();



         return new DTO(){ result = list, count = list.Count }



        }



public class DTO

{

        public List<EmployeeMap> result { get; set; }

        public int count { get; set; }

 }


 {% endhighlight %}
 
 {% endtabs %}


The SessionFactory used by the application is as follows.

{% highlight c# %}

public static class AppSession

    {

        public static ISession OpenSession()

        {

            var configuration = new Configuration();

            var configurationPath = HttpContext.Current.Server.MapPath(@"~\Models\nHibernateConfig\Employee.cfg.xml");

            configuration.Configure(configurationPath);

            var employeeConfigurationFile = HttpContext.Current.Server.MapPath(@"~\Models\nHibernateConfig\EmployeeMap.hbm.xml");

            configuration.AddFile(employeeConfigurationFile);

            ISessionFactory sessionFactory = configuration.BuildSessionFactory();

            return sessionFactory.OpenSession();

        }

    }

 {% endhighlight %}


N> In the above code example, the ORM mapping is performed by using the XML-documents and the mapping files are Employee.cfg.xml and EmployeeMap.hbm.xml





