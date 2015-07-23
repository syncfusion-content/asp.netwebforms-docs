---
layout: post
title: Use-NHibernate-with-Grid
description: use nhibernate with grid
platform: aspnet
control: Grid
documentation: ug
---

### Use NHibernate with Grid

NHibernate

NHibernate is an object-relational mapping (ORM) solution for the Microsoft .NET platform. It provides a framework for mapping an object-oriented domain model to a traditional relational database.

Populate Grid with data by using NHibernate

You can populate the Grid with data obtained by using NHibernate. The UrlAdaptor can be used for data binding and to handle the request and response from the server. You can use the CRUD URL mappers (InsertUrl/UpdateUrl/RemoveUrl/CrudUrl) to provide the action/method to be called while editing.

The Grid initialization is as follows.





[ASP]



[aspx]

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



[CS]



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

       public static object PerforUpdate(int key, EmployeeMap value) { 



          ISession session = AppSession.OpenSession();



          var employeetoUpdate = session.Get<EmployeeMap>(key);



            employeetoUpdate.Designation = value.Designation;

            employeetoUpdate.FirstName = value.FirstName;

            employeetoUpdate.LastName = value.LastName;



             ITransaction transaction = session.BeginTransaction();              

             session.Save(employeetoUpdate);

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





The SessionFactory used by the application is as follows.



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



> { ![C:/Users/ApoorvahR/Desktop/Note.png](Use-NHibernate-with-Grid_images/Use-NHibernate-with-Grid_img1.png) | markdownify }

_Note: In the above code example, the ORM mapping is performed by using the xml-documents and the mapping files are Employee.cfg.xml and EmployeeMap.hbm.xml_





