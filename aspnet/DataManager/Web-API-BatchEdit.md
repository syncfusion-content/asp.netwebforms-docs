---
layout: post
title: WebAPI Batch Edit | DataManager | ASP.NET Webforms | Syncfusion
description: WebAPI Batch Edit
platform: aspnet
control: DataManager
documentation: ug
keywords: Insert of Records, Delete, Update, Read, Remove, Add Fields

---

# WebAPI Batch Edit

WebAPI Batch Editing is a unique feature, where requests to add, remove and change are handled altogether at a time rather than passing the request separately for each operation.Use the Save changes button to process all changes at once and cancel button to discard the changes.


## Configuration
Below are listed the steps for you to follow when configuring the DataManager for ASP.NET MVC to do batch updates.

In order to using batch in Web API, you should register a route with a batch handler or create an OWIN server. The below code creates the server and configures a web API route and a batch route.

{% highlight C# %}

using Microsoft.Owin;
using Owin;
using System.Web.Http;
using System.Web.Http.Batch;


[assembly: OwinStartupAttribute(typeof(Sample.Startup))]
namespace Sample
{
    public partial class Startup
    {
        public void Configuration(IAppBuilder app)
        {
            ConfigureAuth(app);

            HttpConfiguration config = new HttpConfiguration();

            config.MapHttpAttributeRoutes();


            HttpServer server = new HttpServer(config);
            config.Routes.MapHttpBatchRoute(
              routeName: "batch",
              routeTemplate: "api/batch",
              batchHandler: new DefaultHttpBatchHandler(server));

            app.UseWebApi(config);

            app.UseStaticFiles();
        }
    }
}


{% endhighlight %}

Web API uses route templates to determine which controller and action method to execute. At least one route template must be added into route table in order to handle various HTTP requests.

Route (WebApiConfig.cs):

{% highlight C# %}


config.Routes.MapHttpRoute(
                name: "api",
                routeTemplate: "api/{controller}/{id}",
                defaults: new { id = RouteParameter.Optional }
            );


{% endhighlight %}

Add a new class to the ~/Models folder. Name it Employee.

{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;

namespace Sample.Models
{
    interface IEmployeeRepository
    {
        IEnumerable<Employee> GetAll();
        Employee Get(int EmployeeID);
        Employee Add(Employee emp);
        void Remove(int EmployeeID);
        bool Update(Employee emp);
    }
    public class Employee
    {
        public int EmployeeID { get; set; }
        public string FirstName { get; set; }
        public string LastName { get; set; }

        public Employee()
        {

        }
        public Employee(int id, string LN, string FN)
        {
            this.EmployeeID = id;
            this.LastName = LN;
            this.FirstName = FN;

        }
    }
}

{% endhighlight %}

Add a new Repository Data Model class. Name it EmployeeRepository.

{% highlight C# %}


using System;
using System.Collections.Generic;
using System.Linq;
using System.Web;

namespace Sample.Models
{
    public class EmployeeRepository : IEmployeeRepository
    {
        private List<Employee> emp = new List<Employee>();
       
        public EmployeeRepository()
        {
            emp.Add(new Employee(1, "Davolio", "Nancy"));
            emp.Add(new Employee(2, "Fuller", "Andrew"));
            emp.Add(new Employee(3, "Leverling", "Janet"));
            emp.Add(new Employee(4, "Peacock", "Margaret"));
            emp.Add(new Employee(5, "Buchanan", "Steven"));
        }

        public IEnumerable<Employee> GetAll()
        {
            return emp;
        }

        public Employee Get(int id)
        {
            return emp.Find(p => p.EmployeeID == id);
        }

        public Employee Add(Employee eObj)
        {
            if (eObj == null)
            {
                throw new ArgumentNullException("eObj");
            }
            emp.Add(eObj);
            return eObj;
        }

        public void Remove(int id)
        {
            emp.RemoveAll(p => p.EmployeeID == id);
        }

        public bool Update(Employee eObj)
        {
            if (eObj == null)
            {
                throw new ArgumentNullException("eObj");
            }
            int index = emp.FindIndex(p => p.EmployeeID == eObj.EmployeeID);
            if (index == -1)
            {
                return false;
            }
            emp.RemoveAt(index);
            emp.Add(eObj);
            return true;
        }
    }
}


{% endhighlight %}

Add a new ApiController name it as EmployeeController.cs and add a new Post/Put/Delete method which will return the Employee as JSON. The DataManager will make requests to this action based on route name.


{% highlight C# %}

using System;
using System.Collections.Generic;
using System.Linq;
using System.Net;
using System.Net.Http;
using System.Web.Http;
using Sample.Models;
using System.Web;
using System.Threading.Tasks;

namespace Sample.Controllers
{
    public class EmployeeController : ApiController
    {
        static readonly IEmployeeRepository repository = new EmployeeRepository();
        [Route("get")]
        public async Task<object> Get()
        {
            await Task.Delay(1000);

            var queryString = HttpContext.Current.Request.QueryString;
            var data = repository.GetAll().ToList();
            return new { Items = data, Count = data.Count() };
        }
       

        public Employee GetEmployee(int id)
        {
            Employee emp = repository.Get(id);
            if (emp == null)
            {
                throw new HttpResponseException(HttpStatusCode.NotFound);
            }
            return emp;
        }

        [Route("post")]
        public async Task<IHttpActionResult> Post([FromBody] Employee emp)
        {

            if (emp == null)
            {
                return BadRequest(ModelState);
            }
            emp = repository.Add(emp);
            return Content(HttpStatusCode.OK, emp);
        }

        [Route("put")]
        public async Task<IHttpActionResult> Put([FromBody] Employee emp)
        {

            await Task.Delay(1000);
            if (emp == null)
            {
                return BadRequest(ModelState);
            }
            else 
            {

                if (!repository.Update(emp))
                {
                    throw new HttpResponseException(HttpStatusCode.NotFound);
                }
                return Content(HttpStatusCode.OK, emp);
            }
            
        }

        [Route("delete/{id}")]
        public async Task<IHttpActionResult> Delete(int id)
        {

            Employee emp = repository.Get(id);
            await Task.Delay(1000);
            if (emp == null)
            {
                return NotFound();
            }
            else
            {
                repository.Remove(id);
                return StatusCode(HttpStatusCode.OK);
            }
        }

    }
}


{% endhighlight %}

In the view, configure the DataManager to use the Post/Put/Delete methods created in the previous steps.

{% highlight C# %}

<ej:DataManager ID="FlatData" runat="server" CrossDomain="true" BatchURL="/api/batch" URL="/api/Employee" InsertURL="/post" UpdateURL="/put" RemoveURL="/delete" Adaptor="WebApiAdaptor" />
    <ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True"
        DataManagerID="FlatData"
        Query="new ej.Query().select(['EmployeeID', 'FirstName', 'LastName']).take(5)">
        <Columns>
            <ej:Column Field="EmployeeID" HeaderText="Employee ID" Width="80" />
            <ej:Column Field="FirstName" HeaderText="FirstName" Width="130" />
            <ej:Column Field="LastName" HeaderText="LastName" Width="80" />
        </Columns>
        <EditSettings AllowEditing="True" AllowAdding="True" AllowDeleting="True" EditMode="Batch"></EditSettings>
        <ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"></ToolbarSettings>
    </ej:Grid>

{% endhighlight %}

Run the sample and perform batch operation. You can notice that the changes are reflected in the Database Table too.