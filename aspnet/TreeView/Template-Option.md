---
title: Template Option| TreeView | ASP.NET | Syncfusion
description: Rendering TreeView using Template option
platform: aspnet
control: TreeView
documentation: UG
keywords: TreeView,  Syncfusion, ASP Web TreeView UG Doc, Template Option
---


# Template Option

Tree nodes can be customized by using '**Template**' property. Treeview template option requires addition JS library called '**JsRender**', which helps to create the structured way of tree nodes with simple codes and increased performance. To know more about JsRender - [http://www.jsviews.com/](http://www.jsviews.com/#).  

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            protected void Page_Load(object sender, EventArgs e)
            {
                List<Template> templateData = new List<Template>();
                templateData.Add(new Template {
                    Id = 1,
                    Name = "UK",
                    HasChild = true,
                    Expanded = true,
                    ClassName = "UK-style"
                });
                templateData.Add(new Template {
                    Id = 2,
                    PId = 1,
                    ImageId = 1,
                    Name = "Steven John",
                    City = "London",
                    Phone = "555-5665-2323"
                });
                templateData.Add(new Template {
                    Id = 3,
                    Name = "USA",
                    HasChild = true,
                    Expanded = true,
                    ClassName = "USA-style"
                });
                templateData.Add(new Template {
                    Id = 5,
                    PId = 3,
                    ImageId = 2,
                    Name = "Andrew",
                    City = "Capital way",
                    Phone = "934-8374-2455"
                });
                templateData.Add(new Template {
                    Id = 4,
                    PId = 3,
                    ImageId = 3,
                    Name = "Angelica",
                    City = "Dayton",
                    Phone = "988-4243-0806"
                });
                treeview.DataSource = templateData;
            }        
        }
        public class Template
        {
            public int Id { get; set; }
            public int PId { get; set; }
            public int ImageId { get; set; }
            public string Name { get; set; }
            public bool HasChild { get; set; }
            public bool Expanded { get; set; }
            public string City { get; set; }
            public string Phone { get; set; }
            public string ClassName { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, specify template format and add TreeView element
    
    {% highlight html %}
    
        <script id="treeTemplate" type="text/x-jsrender">
            {{"{{"}}if HasChild{{}}}}
                <div class={{"{{"}}>ClassName}}>{{"{{"}}>Name{{}}}}</div>
            {{"{{"}}else{{}}}}
                <div class="cont-list">
                    <img class="con-img"
                        src="http://asp.syncfusion.com/demos/web/Content/images/treeview/template-image-{{"{{"}}>ImageId{{}}}}.png" />
                    <div class="cont-delete"></div>
                    <div class="cont-details">
                        <b>{{"{{"}}>Name{{}}}}</b><br />
                        <span>{{"{{"}}>City{{}}}}</span>
                        <br />
                        <span>{{"{{"}}>Phone{{}}}}</span>
                    </div>
                    <div class="treeFooter"></div>
                </div>
            {{"{{"}}/if{{}}}}
    
        </script>
    
        <script type="text/javascript">
            $(function () {
                var treeObj = $("#<%=treeview.ClientID%>").data("ejTreeView");
                $("#<%=treeview.ClientID%>").find(".cont-delete").bind("click", function (e) {
                    treeObj.removeNode($(e.target).parents("li").first());
                });
            });
        </script>
    
        <ej:TreeView
            ID="treeview"
            runat="server"
            Template="#treeTemplate"
            DataTextField="Name"
            DataIdField="Id"
            DataParentIdField="PId"
            DataHasChildField="HasChild"
            DataExpandedField="Expanded" />
    
        <style type="text/css">
            .e-treeview .e-node-hover, .e-treeview .e-active {
                background: transparent;
                border-color: transparent;
            }
    
            .e-treeview .e-node-hover {
                opacity: 0.8;
            }
    
            .con-img {
                float: left;
            }
    
            .cont-list {
                background: none repeat scroll 0 0 white;
                border: 1px solid #BBBCBB;
                height: 85px;
                width: 200px;
                color: #5c5c5c;
                line-height: 17px;
            }
    
            .cont-details {
                margin-top: 12px;
                font-size: 13px;
            }
    
            .UK-style {
                background-color: #74A247 !important;
                color: #FFFFFF !important;
            }
    
            .USA-style {
                background-color: #12A99A !important;
                color: #FFFFFF !important;
            }
    
            .cont-delete {
                background-image: url("http://asp.syncfusion.com/demos/web/Content/images/treeview/remove-icon.png");
                background-position: -6px -10px;
                background-repeat: no-repeat;
                float: right;
                height: 16px;
                width: 16px;
                cursor: pointer;
            }
    
            .cont-list .treeFooter {
                height: 5px;
                width: 100%;
                background-color: gray;
                margin-top: 17px;
            }
        </style>
        
    {% endhighlight %}
    
**Custom action in nodes**

You can able to perform custom action in TreeView template node. You can able to perform node delete operation while clicking delete icon by using [removeNode](http://help.syncfusion.com/js/api/ejtreeview#methods:removenode) method of TreeView as shown in below code example.
    
    {% highlight html %}
    
    <script type="text/javascript">
        function onCreate(args) {
            var treeObj = $("#<%= treeView.ClientID %>").data("ejTreeView");
            $("#<%= treeView.ClientID %>").find(".cont-delete").bind("click", function (e) {
                e.preventDefault();
                treeObj.removeNode($(e.target).parents("li").first());
            });
        }
    </script>
    
    {% endhighlight %}
 
 