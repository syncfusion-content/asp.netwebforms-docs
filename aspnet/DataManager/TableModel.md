---
layout: post
title: Table-Model | DataManager | ASP.NET | Syncfusion
description: table model
platform: aspnet
control: DataManager
documentation: ug
keywords : Table Model, getTableModel

---

# Table Model

The **DataManager** contains a default support to bind a TableModel to the element. You can make the data observable using the **getTableModel** method. The **getTableModel** method also accept extra properties or properties with computed value that can be added to the TableModel. In the view, you can create a simple view by using the bindings **getTableModel**

Then the model is bound with the element using the **bindTo.** 

{% highlight C# %}

    public partial class DataManager : System.Web.UI.Page
    {
        List<Employee> emp = new List<Employee>();
        protected void Page_Load(object sender, EventArgs e)
        {
            BindDataSource();
        }
        private void BindDataSource()
        {
            emp.Add(new Employee(1, "Davolio", "Nancy"));
            emp.Add(new Employee(2, "Fuller", "Andrew"));
            emp.Add(new Employee(3, "Leverling", "Janet"));
            emp.Add(new Employee(4, "Peacock", "Margaret"));
            emp.Add(new Employee(5, "Buchanan", "Steven"));
            
            this.FlatData.Json = emp;
        }

        [Serializable]
        public class Employee
        {
            public Employee()
            {

            }
            public Employee(int EmployeeId, string FirstName, string LastName)
            {
                this.EmployeeID = EmployeeId;
                this.FirstName = FirstName;
                this.LastName = LastName;
            }
            public int EmployeeID { get; set; }
            public string FirstName { get; set; }
            public string LastName { get; set; }
        }

    }

{% endhighlight %}

{% highlight CSHTML %}

    <div class="datatable" style="padding:10px">
        <div class="row">
            <div class="col-md-7">
                <table id="table1" class="table table-striped table-bordered" style="width:700px">
                    <thead>
                        <tr>
                            <th>EmployeeID</th>
                            <th>Full Name</th>
                        </tr>
                    </thead>
                    <tbody id="tbody1">
                        <tr>
                            <td ej-observe="EmployeeID" ej-computed="EmployeeIndex"></td>
                            <td ej-computed="FullName"></td>
                        </tr>
                    </tbody>
                </table>
            </div>
            <div class="col-md-5">
                <form class="form-horizontal" role="form">
                    <div class="form-group">
                        <label class="col-sm-4 control-label">EmployeeID</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="empId">
                        </div>
                    </div>
                    <div class="form-group">
                        <label class="col-sm-4 control-label">FirstName</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="first">
                        </div>
                    </div>
                    <div class="form-group">
                        <label class="col-sm-4 control-label">LastName</label>
                        <div class="col-sm-8">
                            <input type="text" class="form-control" id="last">
                        </div>
                    </div>
                    <div class="form-group">
                        <div class="col-sm-offset-4 col-sm-4">
                            <button type="button" id="formSubmit" class="btn btn-default">Change</button>
                        </div>
                    </div>
                </form>
            </div>  
        </div>
    </div>

   <ej:DataManager ID="FlatData" runat="server" Adaptor="JsonAdaptor"/>

    <script type="text/javascript">

        setTimeout(function () {
            window.employees = [];
            var query = ej.Query();
            var promise = window.FlatData.executeQuery(query);
            promise.done(function (e) {
                    employees = e.getTableModel({
                        FullName: {
                            value: function () {
                                return this.FirstName + ' ' + this.LastName;
                            },
                            deps: ["FirstName", "LastName"]
                        },
                        EmployeeIndex: {
                            value: function () {
                                return this.EmployeeID;
                            },
                            deps: ["EmployeeID"]
                        }
                });
                employees.bindTo($("#tbody1"));
            });
        }, 1000);
          
        $("#formSubmit").click(function (e) {
            var empId = parseInt($("#empId").val(), 10);
            var fName = $("#first").val();
            var lName = $("#last").val();
            emp = employees.get(empId - 1);
            emp.set("FirstName",fName);
            emp.set("LastName",lName);
        });

    </script>

{% endhighlight %}

The result for the above code example is illustrated as follows.

![](Table-Model_images/Table-Model_img1.png) 

[Sample Link](http://www.syncfusion.com/downloads/support/directtrac/general/7z/DMtableModel618709880)

