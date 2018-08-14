---
title: How To | TreeView | ASP.NET | Syncfusion
description: How to do - section for TreeView
platform: aspnet
control: TreeView
documentation: UG
keywords: TreeView,  Syncfusion, ASP Web TreeView UG Doc, How To
---

# How To

## Update the modified data from tree to database.

TreeView allows us to get the updated tree data after performing such operation like node editing, drag and drop, add and remove node. Using [getTreeData](http://help.syncfusion.com/js/api/ejtreeview#methods:gettreedata) method you can get the updated tree data.

Refer the following code block to know how to get updated data from TreeView.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView with that also specify the method to store modified data.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<loadData> treeData = new List<loadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                var storedData = System.Web.HttpContext.Current.Session["modifiedData"];
                if (storedData == null)
                {
                    treeData.Add(new loadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                    treeData.Add(new loadData { Id = 2, Parent = 0, Text = "Item 2" });
                    treeData.Add(new loadData { Id = 3, Parent = 0, Text = "Item 3" });
                    treeData.Add(new loadData { Id = 4, Parent = 0, Text = "Item 4" });
                    treeData.Add(new loadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                    treeData.Add(new loadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                    treeData.Add(new loadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                    treeData.Add(new loadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                    treeData.Add(new loadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                    treeData.Add(new loadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                    this.treeView.DataSource = treeData;
                }
                else
                    this.treeView.DataSource = storedData;
    
            }
            [System.Web.Services.WebMethod]
            public static void StoreData(List<loadData> data)
            {
                System.Web.HttpContext.Current.Session["modifiedData"] = (data.Count > 0 ? data : null);
            }
    
        }
        public class loadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and specify the scripts for sending modified data through AJAX action with that also specify clear cache option.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            ClientSideOnCreated="onCreate">
        </ej:TreeView>
        <ej:Button
            ID="move"
            Text="Move"
            Type="Button"
            runat="server"
            ClientSideOnClick="onMove">
        </ej:Button>
        <ej:Button
            ID="clear"
            Text="Clear"
            Type="Button"
            runat="server"
            ClientSideOnClick="onClear">
        </ej:Button>
        <script type="text/javascript">
            var treeObj;
            function onCreate() {
                treeObj = $("#<%= treeView.ClientID %>").data('ejTreeView');
            }
            function onMove() {
                treeObj.moveNode(treeObj.element.find("#4"), treeObj.element.find("#1"), 11);
                var updatedData = treeObj.getTreeData();
                ajaxRequest(updatedData);
            }
            function ajaxRequest(updatedData) {
                $.ajax({
                    url: "TreeViewFeatures.aspx/StoreData",
                    data: JSON.stringify({ data: updatedData }),
                    type: "POST",
                    contentType: "application/json",
                    dataType: "JSON"
                });
            }
            function onClear() {
                treeObj.destroy();
                ajaxRequest({});
            }
        </script>
        
    {% endhighlight %}

You can also get the updated data source for remote data binding after performing the operation like editing, selecting/unselecting, expanding/collapsing, checking/unchecking and removing node. You cannot get the updated data source when you perform operation like drag and drop, adding node for remote data binding.

The updated data source also contains custom attributes ("ContactTitle", "OrderID", "EmployeeID", "Freight") if you return these from server.

Refer the following code block to know more about how to get updated data with custom attributes from TreeView for remote data binding.

In the view page, add TreeView element and specify the scripts for getting updated data source.

{% highlight html %}
<button id="btn1" onclick="getSelectedNodeObject()" type="button">GetSelectedNodeObject</button>

<ej:TreeView runat="server" ID="tree1" DataIdField="CustomerID" DataTextField="CustomerID" Query="ej.Query().from('Orders').select('CustomerID,OrderID,EmployeeID,Freight').take(3)">
    <DataManager URL="//js.syncfusion.com/ejServices/Wcf/Northwind.svc/" CrossDomain="true"></DataManager>
    <Child Id="Country" ParentId="CustomerID" Text="ContactName" Query="ej.Query().from('Customers').select('CustomerID,ContactTitle,ContactName,Country')">
        <DataManager URL="//js.syncfusion.com/ejServices/Wcf/Northwind.svc/" CrossDomain="true"></DataManager>
    </Child>
</ej:TreeView>

<script>
    function getSelectedNodeObject() {
        var treeObj = $("#<%=tree1.ClientID%>").data("ejTreeView");
        var nodeId = treeObj.getSelectedNode().attr("id"); //get selected node id
        if (nodeId != null) {
            var node = treeObj.getTreeData(nodeId); //get the given node object
            if (node[0].OrderID != null)
                alert("The OrderID of node '" + node[0].CustomerID + "' is: '" + node[0].OrderID + "'");
            else
                alert("The ContactTitle of node '" + node[0].ContactName + "' is: '" + node[0].ContactTitle + "'");
        } else
            alert("Select any node");
    }
</script>
{% endhighlight %}
    
## TreeView context menu to process node operations.

TreeView control is availed with the context menu options that open on right-click, over the node. Other than the default menu items available, you can add the new node dynamically in TreeView and also delete the item, enable and disable the item in TreeView. It is achieved by adding the context menu option to the TreeView.

**Menu Item**

By default, the context menu options are provided with four items namely: Add New Item, Delete Item, Enable Item and Disable Item. When you want to customize and use your own custom menu items, then you can customize the TreeView with the desired collections.

The following code example illustrates how to configure the context menu elements for the TreeView and in the following example, you have to specify the menu type as ej.MenuType.ContextMenu and in the menuClick function, you can check the cases with add, delete, remove or enable item in TreeView.
And each functionality in the context menu option is done by specific methods. For example, you have added the new item in TreeView by using the addNode() method, delete the item using removeNode() method, disable the item using disableNode() method and enable the item enableNode() method respectively.

The following steps explain how you can enable the ShowCheckbox property for TreeView.

In the view page, add TreeView element and specify context menu items.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            Height="300px"
            Width="400px">
            <Nodes>
                <ej:TreeViewNode Expanded="True" Text="ASP.NET Web Team">
                    <Nodes>
                        <ej:TreeViewNode Text="Smith">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Johnson">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Anderson">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Text="Windows Team">
                    <Nodes>
                        <ej:TreeViewNode Text="Clark">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Wright">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Lopez">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Text="Web Team">
                    <Nodes>
                        <ej:TreeViewNode Text="Joshua">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Matthew">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="David">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Text="Build Team">
                    <Nodes>
                        <ej:TreeViewNode Text="Ryan">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Justin">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Robert">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
                <ej:TreeViewNode Text="WPF Team">
                    <Nodes>
                        <ej:TreeViewNode Text="Brown">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Johnson">
                        </ej:TreeViewNode>
                        <ej:TreeViewNode Text="Miller">
                        </ej:TreeViewNode>
                    </Nodes>
                </ej:TreeViewNode>
            </Nodes>
        </ej:TreeView>
    
        <div>
            <ej:Menu
                ID="Menu1"
                MenuType="ContextMenu"
                ClientSideOnClick="menuClick"
                ClientSideOnBeforeContextOpen="beforeOpen"
                OpenOnClick="false"
                runat="server"
                ContextMenuTarget="#LayoutSection_ControlsSection_treeView">
                <Items>
                    <ej:MenuItem Text="Add New Item">
                    </ej:MenuItem>
                </Items>
                <Items>
                    <ej:MenuItem Text="Remove Item">
                    </ej:MenuItem>
                </Items>
                <Items>
                    <ej:MenuItem Text="Disable Item">
                    </ej:MenuItem>
                </Items>
                <Items>
                    <ej:MenuItem Text="Enable Item">
                    </ej:MenuItem>
                </Items>
            </ej:Menu>
        </div>
        
    {% endhighlight %}
    
Define menu events in the script as follows,

    {% highlight html %}
    
    <script type="text/javascript" class="jsScript">
            var tabIndex = 1, treeviewObj, selectedNode;
            $(function () {
                treeviewObj = $("#<%=treeView.ClientID%>").data("ejTreeView");
            });
            function beforeOpen(args) {
                if (!$(args.target).hasClass("e-text"))
                    args.cancel = true;
                else {
                    selectedNode = args.target;
                    treeviewObj.selectNode(selectedNode);
                }
            }
            function menuClick(args) {
                if (args.events.text == "Add New Item") {
                    treeviewObj.addNode("Item" + tabIndex, null, selectedNode);
                    tabIndex++;
                }
                else if (args.events.text == "Remove Item") {
                    treeviewObj.removeNode(selectedNode);
                }
                else if (args.events.text == "Disable Item") {
                    treeviewObj.disableNode(selectedNode);
                }
                else if (args.events.text == "Enable Item") {
                    treeviewObj.enableNode(selectedNode);
                }
            }
        </script>
        
    {% endhighlight %}

The output for the context menu for TreeView control is as follows.

![http://help.syncfusion.com/aspnet/treeview/How-To_images/How-To_img1.png](How-To_images/How-To_img1.jpeg)


## Sorted data using refresh method

TreeView allows you to refresh the entire tree data using [refresh](http://help.syncfusion.com/js/api/ejtreeview#methods:refresh) method. Refer the below code block to know how to sort entire tree data using refresh method.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 4" });
                treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 2" });
                treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                this.treeview.DataSource = treeData;
            }
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source with that specify the scripts for sorting and refreshing tree data.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeview"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded">
        </ej:TreeView>
        <ej:Button
            ID="sortButton"
            Text="Sort Countries"
            Type="Button"
            runat="server"
            ClientSideOnClick="sortCountries">
        </ej:Button>
        <script type="text/javascript">
            function sortCountries() {
                var tree = $("#<%= treeview.ClientID %>").data("ejTreeView");
                TreeNodeData = sortResults(tree.model.fields.dataSource, "Text", true);
                tree.model.fields.dataSource = TreeNodeData;
                tree.refresh();
            }
            //Sorting the tree data based on ascending order
            function sortResults(data, fieldName, ascOrder) {
                return data.sort(function (a, b) {
                    if (ascOrder) return (a[fieldName] > b[fieldName]);
                    else return (b[fieldName] > a[fieldName]);
                });
            }
        </script>
        
    {% endhighlight %}
    
## Persist updated data after edit, add and remove node

TreeView allow us to persist the updated data after performing some tree operations like node add and delete. Refer the following code block to know how to persist updated tree data after refresh.

The [nodeAdd](https://help.syncfusion.com/api/js/ejtreeview#events:nodeadd), [nodeCut](https://help.syncfusion.com/api/js/ejtreeview#events:nodecut), [nodeDelete](https://help.syncfusion.com/api/js/ejtreeview#events:nodedelete) and [nodePaste](https://help.syncfusion.com/api/js/ejtreeview#events:nodepaste) events occurs based on Treeview node manipulation. The [beforeAdd](https://help.syncfusion.com/api/js/ejtreeview#events:beforeadd), 
[beforeCut](https://help.syncfusion.com/api/js/ejtreeview#events:beforecut), [beforeDelete](https://help.syncfusion.com/api/js/ejtreeview#events:beforedelete) and [beforePaste](https://help.syncfusion.com/api/js/ejtreeview#events:beforepaste) events are triggered before the TreeView component node manipulation.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView with that specify the method to store modified data.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                var storedData = System.Web.HttpContext.Current.Session["modifiedData"];
                if (storedData == null)
                {
                    treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                    treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 2" });
                    treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                    treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 4" });
                    treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                    treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                    treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                    treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                    treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                    treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                    this.treeView.DataSource = treeData;
                }
                else
                    this.treeView.DataSource = storedData;
    
            }
            [System.Web.Services.WebMethod]
            public static void StoreData(List<LoadData> data)
            {
                System.Web.HttpContext.Current.Session["modifiedData"] = (data.Count > 0 ? data : null);
            }
    
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and specify the scripts for sending modified data through AJAX action.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            ClientSideOnCreated="onCreate"
            ClientSideOnNodeAdd="updateData"
            ClientSideOnNodeDelete="updateData"
            ClientSideOnNodeEdit="updateData">
        </ej:TreeView>
        <ej:Button
            ID="clear"
            Text="Clear Cache"
            Type="Button"
            runat="server"
            ClientSideOnClick="clearCache">
        </ej:Button>
        <ej:Button
            ID="add"
            Text="Add Node"
            Type="Button"
            runat="server"
            ClientSideOnClick="addNode">
        </ej:Button>
        <ej:Button
            ID="remove"
            Text="Remove Node"
            Type="Button"
            runat="server"
            ClientSideOnClick="removeNode">
        </ej:Button>
    
        <script type="text/javascript">
            var treeObj;
            function onCreate() {
                treeObj = $("#<%= treeView.ClientID %>").data('ejTreeView');
            }
            function updateData() {
                var updatedData = treeObj.getTreeData();
                ajaxRequest(updatedData);
            }
            function addNode() {
                treeObj.addNode({ Id: 11, Text: "NewNode1" });
            }
            function removeNode() {
                treeObj.removeNode();
            }
            function ajaxRequest(updatedData) {
                $.ajax({
                    url: "TreeViewFeatures.aspx/StoreData",
                    data: JSON.stringify({ data: updatedData }),
                    type: "POST",
                    contentType: "application/json",
                    dataType: "JSON"
                });
            }
            function clearCache() {
                treeObj.destroy();
                ajaxRequest({});
            }
        </script>
        
    {% endhighlight %}
    
## Filtering nodes in TreeView

You can able to filter TreeView nodes based on node text. Refer the below code blocks to filter tree nodes based on the node text.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 4" });
                treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 2" });
                treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                this.treeview.DataSource = treeData;
            }
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source with that specify the script for filtering tree nodes.
    
    {% highlight html %}
    
        <div style="margin: 20px; padding: 20px; height: 2000px;">
            <div class="heading">
                Treeview with Filtering Nodes
            </div>
            <div class="treeviewfilter">
                <!-- TextBox Element -->
                <ej:MaskEdit
                    runat="server"
                    ID="inputBox"
                    Width="100%"
                    InputMode="Text"
                    MaskFormat=""
                    ClientSideOnChange="searchNodes">
                </ej:MaskEdit>
                <!-- TreeView Element -->
                <ej:TreeView
                    ID="treeview"
                    runat="server"
                    DataTextField="Text"
                    DataIdField="Id"
                    DataParentIdField="Parent"
                    DataExpandedField="Expanded"
                    ClientSideOnCreated="onCreate">
                </ej:TreeView>
            </div>
        </div>
        <script type="text/javascript">
            var treeObj, inputObj, count = 0;
            var onFirstCheck = true;
            window._temp = [];
            function onCreate(args) {
                // Creating Objects for TreeView & MaskEdit TextBox
                treeObj = $("#<%= treeview.ClientID %>").data("ejTreeView");
                inputObj = $("#<%= inputBox.ClientID %>").data("ejMaskEdit");
            }
            //Function triggers while change the TextBox input value and start new search
            function searchNodes(args) {
                var treeElement = treeObj.element;
                // Getting the Input String
                var searchVal = inputObj.get_StrippedValue() ? inputObj.get_StrippedValue().toLowerCase() : "";
                // If the string length is greater than 0 then Do searching.
                if (searchVal.length > 0) {
                    var matchedNode = [], otherNodes = [];
                    // Searching Anchor nodes
                    var linkNodes = treeElement.find('ul>li>div>a');
                    for (var p = 0; p < linkNodes.length; p++) {
                        if ($(linkNodes[p]).text().toLowerCase().indexOf(searchVal) != -1)
                            //  Stores the Matched nodes
                            matchedNode.push(linkNodes[p]);
                        else
                            // Stores the unMatched nodes
                            otherNodes.push(linkNodes[p]);
                    }
                    // Find the matched nodes parent Li element and set Display "block"
                    var resultNodes = treeElement.find(matchedNode).closest("li").css("display", "block");
                    // Find the unmatched nodes parent Li element and set Display "none"
                    treeElement.find(otherNodes).closest("li").css("display", "none");
                    for (var i = 0; i < resultNodes.length; i++) {
                        var currentNode = $(resultNodes[i]);
                        // Get the Parent Li element of current li element and Set Display "block"
                        var parentNode = currentNode.parents('ul').closest('li').css("display", "block");
                        if (parentNode.length > 0) {
                            // Call expandNode function If a parentNode has children
                            treeObj.expandNode(parentNode);
                            if (treeObj.model.expandedNodes.indexOf($(treeObj._liList).index(parentNode)) == -1)
                                window._temp.push(parentNode);
                        }
                        var childrenUl = currentNode.children('ul');
                        if (childrenUl.length > 0 && childrenUl.children('li:visible').length == 0) {
                            currentNode.children('ul').children('li').css("display", "block");
                            // Call expandNode function If a resultNodes[i] has children
                            treeObj.expandNode(resultNodes[i]);
                            if (treeObj.model.expandedNodes.indexOf($(treeObj._liList).index(resultNodes[i])) == -1)
                                window._temp.push(resultNodes[i]);
                        }
                    }
                }
                else {
    
                    // window._temp contains Li elements, which is expanded while searching.
                    treeElement.find('ul>li').css("display", "block");
                    for (var i = 0; i < window._temp.length; i++) {
                        treeObj._collpaseNode(window._temp[i]);
                    }
                    window._temp = [];
                }
            }
        </script>
        <style type="text/css">
            .treeviewfilter {
                width: 200px;
                min-height: 300px;
                max-height: auto;
                border: 1px solid #bbbbbb;
                margin: 0 auto;
            }
    
            .e-mask .e-in-wrap {
                border: none;
                border-bottom: 1px solid #bbbbbb;
            }
    
            .heading {
                font-size: 22px;
                margin: 0 auto;
                width: 300px;
                margin-bottom: 10px;
            }
        </style>
        
    {% endhighlight %}
    
## AngularJS data binding to update data while add and remove node

TreeView allows us to bind and update tree data in mapped data component while adding and removing node using AngularJS binding. Refer the below code block to know how to update data using AngularJS binding.
    
    {% highlight html %}
    
    <div class="content-container-fluid" ng-controller="TreeCtrl">
        <div class="row">
            <div class="cols-sample-area">
                <div style="width: 400px; float:left">
                    <button type="button" ng-click="add()">Add</button>
                    <button type="button" ng-click="remove()">Remove</button>
                    <div id="treeView" e-allowediting="true" ej-treeview e-fields-datasource="dataList" e-fields-id="fieldsId" e-fields-parentid="parentId" e-fields-text="name" e-fields-haschild="hasChild" e-fields-expanded="expanded" e-showcheckbox="true" e-allowediting="true"></div>
                </div>
                <div style="width: 400px; float:left">
                    <table>
                        <tr>
                            <td>
                                <p>direct to $scope.dataList</p>
                                <div ng-repeat="icon in dataList">
                                    <input type="text" ng-model="icon.name" class="sampleText" /><button type="button" ng-click="delete(icon.fieldsId)">Delete</button><br />
                                </div>
                            </td>
                        </tr>
                    </table>
                </div>
            </div>
        </div>
    </div>
    
    <script>
    
        var phones = [
                { fieldsId: 1, name: "Fiction Book Lists", hasChild: true, expanded: true },
                { fieldsId: 2, parentId: 1, name: "To Kill a Mockingbird " },
                { fieldsId: 3, parentId: 1, name: "Pride and Prejudice " },
                { fieldsId: 4, parentId: 1, name: "Harry Potter and the Sorcerer's Stone" },
                { fieldsId: 5, parentId: 1, name: "The Hobbit " },
                { fieldsId: 6, name: "Mystery Book Lists", hasChild: true, expanded: true },
                { fieldsId: 7, parentId: 6, name: "And Then There Were None " },
                { fieldsId: 8, parentId: 6, name: "Angels & Demons" },
                { fieldsId: 9, parentId: 6, name: "In Cold Blood " },
                { fieldsId: 10, parentId: 6, name: "The Name of the Rose " },
                { fieldsId: 11, name: "Horror Novels", hasChild: true },
                { fieldsId: 12, parentId: 11, name: "The Shining (The Shining, #1) " },
                { fieldsId: 13, parentId: 11, name: "The Haunting of Hill House " },
                { fieldsId: 14, parentId: 11, name: "The Silence of the Lambs (Hannibal Lecter, #2) " },
                { fieldsId: 15, name: "Novel Lists", hasChild: true },
                { fieldsId: 16, parentId: 15, name: "Shadow Hills (Shadow Hills, #1) " },
                { fieldsId: 17, parentId: 15, name: "After Forever Ends " },
                { fieldsId: 18, parentId: 15, name: "Angel Star" },
                { fieldsId: 19, parentId: 15, name: "Raised by Wolves" },
                { fieldsId: 20, parentId: 15, name: "Falling From Grace" }];
        var Nodes = ["1", "2"];
        angular.module('treeApp', ['ejangular']).controller('TreeCtrl', function ($scope) {
            $scope.dataList = phones;
    
            $scope.add = function () {
                var treeObj = $("#<%= treeView.ClientID %>").data("ejTreeView"), obj;
                //obj = [{ fieldsId: 21, parentId: 1, name: "Newnode" }];
                obj = "New TextNode";
                treeObj.addNode(obj);    // Two way binding when add node
            };
    
            $scope.remove = function () {
                var treeObj = $("#<%= treeView.ClientID %>").data("ejTreeView");
                var id = treeObj.getSelectedNode()[0].id;
                treeObj.removeNode(treeObj.getSelectedNode());  // Two way binding when remove node
            };
    
            // Delete from outside Tree
            $scope.delete = function (fieldsId) {
                for (var i = $scope.dataList.length - 1; i > -1; i--) {
                    if ($scope.dataList[i].fieldsId === fieldsId)
                        $scope.dataList.splice(i, 1); // Delete parent node
                }
                for (var i = $scope.dataList.length - 1; i > -1; i--) {
                    if ($scope.dataList[i].parentId === fieldsId)
                        $scope.dataList.splice(i, 1); // Delete child nodes
                }
            };
    
        });
    
    </script>
    
    {% endhighlight %}
    
## Set tooltip for TreeView nodes

TreeView allows you to set tooltip option to TreeView nodes using [fields.linkAttribute](http://help.syncfusion.com/js/api/ejtreeview#members:fields-linkattribute) property of TreeView. Refer the below code block to know how to set tooltip for TreeView nodes.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData.Add(new LoadData
                {
                    Id = 1,
                    Parent = 0,
                    Text = "Item 1",
                    Expanded = true,
                    LinkAttribute = new LinkAttribute()
                    {
                        Title = "First Item"
                    }
                });
                treeData.Add(new LoadData
                {
                    Id = 2,
                    Parent = 0,
                    Text = "Item 2",
                    LinkAttribute = new LinkAttribute()
                    {
                        Title = "Second Item"
                    }
                });
                treeData.Add(new LoadData
                {
                    Id = 3,
                    Parent = 0,
                    Text = "Item 3"
                });
                treeData.Add(new LoadData
                {
                    Id = 4,
                    Parent = 0,
                    Text = "Item 4"
                });
                treeData.Add(new LoadData
                {
                    Id = 5,
                    Parent = 1,
                    Text = "Item 1.1"
                });
                treeData.Add(new LoadData
                {
                    Id = 6,
                    Parent = 1,
                    Text = "Item 1.2"
                });
                treeData.Add(new LoadData
                {
                    Id = 7,
                    Parent = 1,
                    Text = "Item 1.3"
                });
                treeData.Add(new LoadData
                {
                    Id = 8,
                    Parent = 3,
                    Text = "Item 3.1"
                });
                treeData.Add(new LoadData
                {
                    Id = 9,
                    Parent = 3,
                    Text = "Item 3.2"
                });
                treeData.Add(new LoadData
                {
                    Id = 10,
                    Parent = 5,
                    Text = "Item 1.1.1"
                });
                this.treeView.DataSource = treeData;
            }
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
            public object LinkAttribute { get; set; }
        }
        public class LinkAttribute
        {
            public string Title { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source.
    
    {% highlight html %}
    
        <ej:TreeView
            ID="treeView"
            runat="server"
            DataTextField="Text"
            DataIdField="Id"
            DataParentIdField="Parent"
            DataExpandedField="Expanded"
            DataLinkAttributeField="LinkAttribute">
        </ej:TreeView>
        
    {% endhighlight %}
    
## Auto hide/ show the expand/ collapse icon of TreeView

You can able to display expand icon on mouse entering into TreeView and hide while leaving from the TreeView. Refer the below code blocks to know how to hide/ show the expand/collapse icons automatically based on mouse position.

In the code behind page, create a data list which contains the details about tree nodes and map the list data to DataSource property of TreeView.
    
    {% highlight c# %}
    
        public partial class TreeViewFeatures : System.Web.UI.Page
        {
            List<LoadData> treeData = new List<LoadData>();
            protected void Page_Load(object sender, EventArgs e)
            {
                treeData.Add(new LoadData { Id = 1, Parent = 0, Text = "Item 1", Expanded = true });
                treeData.Add(new LoadData { Id = 2, Parent = 0, Text = "Item 4" });
                treeData.Add(new LoadData { Id = 3, Parent = 0, Text = "Item 3" });
                treeData.Add(new LoadData { Id = 4, Parent = 0, Text = "Item 2" });
                treeData.Add(new LoadData { Id = 5, Parent = 1, Text = "Item 1.1" });
                treeData.Add(new LoadData { Id = 6, Parent = 1, Text = "Item 1.2" });
                treeData.Add(new LoadData { Id = 7, Parent = 1, Text = "Item 1.3" });
                treeData.Add(new LoadData { Id = 8, Parent = 3, Text = "Item 3.1" });
                treeData.Add(new LoadData { Id = 9, Parent = 3, Text = "Item 3.2" });
                treeData.Add(new LoadData { Id = 10, Parent = 5, Text = "Item 1.1.1" });
                this.treeView.DataSource = treeData;
            }
        }
        public class LoadData
        {
            public int Id { get; set; }
            public int Parent { get; set; }
            public string Text { get; set; }
            public bool Expanded { get; set; }
        }
        
    {% endhighlight %}
    
In the view page, add TreeView element and map the properties defined into the corresponding fields in data source with that specify the scripts to hide and show the icon for Tree nodes.
    
    {% highlight html %}
    
        <div style="width: 150px">
            <ej:TreeView
                ID="treeView"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                ClientSideOnCreated="onCreate">
            </ej:TreeView>
        </div>
        <script type="text/javascript">
            function onCreate(args) {
                this.element.find(".e-item > div > .e-plus, .e-minus").css("visibility", "hidden");
                var treeObj = $("#<%= treeView.ClientID %>").data("ejTreeView");
                $("#<%= treeView.ClientID %>").on("mouseenter", function () {
                    treeObj.element.find(".e-item > div > .e-plus, .e-minus").css("visibility", "");
                });
                $("#<%= treeView.ClientID %>").on("mouseleave", function () {
                    treeObj.element.find(".e-item > div > .e-plus, .e-minus").css("visibility", "hidden");
                });
            }
        </script>
        
    {% endhighlight %}
    
## Customize the expand/ collapse icons of TreeView

You can able to customize the TreeView expand and collapse icon by using “**CssClass**” property of TreeView. Refer the below code block to know how to customize the expand/ collapse icons.

In the view page, add TreeView element and map the properties defined in to the corresponding fields in data source with that specify the styles for customizing expand/ collapse icons of TreeView.
    
    {% highlight html %}
    
        <div style="width: 150px">
            <ej:TreeView
                ID="treeView"
                runat="server"
                DataTextField="Text"
                DataIdField="Id"
                DataParentIdField="Parent"
                DataExpandedField="Expanded"
                CssClass="customize">
            </ej:TreeView>
        </div>
    
        <style type="text/css">
            .customize .e-icon {
                width: 16px;
                height: 16px;
                background-repeat: no-repeat;
                background-image: url("http://jsplayground.syncfusion.com/13.3.0.7/themes/web/images/ui-icons/ui-icons-default.png");
            }
    
            .customize .e-icon.e-plus:before, .customize .e-icon.e-minus:before {
            content: "";
            }
    
            .customize .e-icon.e-plus {
            background-position: -80px -46px;
            }
    
            .customize .e-icon.e-minus {
            background-position: -132px -46px;
            }
        </style>
        
    {% endhighlight %}
    
## How to get all checked nodes details of TreeView in server end

In button click, you need to get all checked node details of TreeView and send it to server using AJAX. 

Refer the following code block to know how to get checked nodes details in server end.

In the view page, add TreeView element and specify the scripts for sending checked node details in button click.
    
    {% highlight html %}
    
        <div style="width: 250px">
            <ej:TreeView
                ID="tree"
                runat="server"
                Width="400px"
                ShowCheckbox="true">
                <Nodes>
                    <ej:TreeViewNode Expanded="True" Text="Item 1">
                        <Nodes>
                            <ej:TreeViewNode Text="Item 1.1">
                                <Nodes>
                                    <ej:TreeViewNode Text="Item 1.1.1"></ej:TreeViewNode>
                                    <ej:TreeViewNode Text="Item 1.1.2"></ej:TreeViewNode>
                                </Nodes>
                            </ej:TreeViewNode>
                            <ej:TreeViewNode Text="Item 1.2">
                            </ej:TreeViewNode>
                        </Nodes>
                    </ej:TreeViewNode>
                    <ej:TreeViewNode Text="Item 2"></ej:TreeViewNode>
                    <ej:TreeViewNode Text="Item 3"></ej:TreeViewNode>
                </Nodes>
            </ej:TreeView>
            <input type="button" id="getNodes" value="GetCheckedNodes" />
        </div>
        <script>
            $('#getNodes').click(function () {
                tree = $("#<%= tree.ClientID %>").data("ejTreeView");
                var data = [];
                nodeLength = tree.getCheckedNodes().length;
                for (i = 0; i < nodeLength ; i++) {
                    var nodeId = tree.getCheckedNodes()[i];
                    var nodeData = tree.getNode(nodeId);
                    data.push(nodeData);
                }
                $.ajax({
                    type: 'POST',
                    url: "TreeViewFeatures.aspx/CheckedNodes",
                    data: JSON.stringify({ nodeData: data }),
                    dataType: "json",
                    contentType: "application/json; charset=utf-8",
                    async: false
                });
            });
        </script>
        
    {% endhighlight %}
    
In the code behind page, configure following settings to get all the checked node details.
    
    {% highlight c# %}
    
            // In nodeData all checkedNodes are received
            [System.Web.Services.WebMethod]
            public static void CheckedNodes(List<TreeViewItems> nodeData)
            {
                for (var i = 0; i < nodeData.Count; i++)
                {
                    Console.WriteLine(nodeData[i].Text);
                }            
            }
            
    {% endhighlight %}
    
	