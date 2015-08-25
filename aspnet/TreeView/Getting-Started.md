---
layout: post
title: Getting-Started
description: getting started
platform: aspnet
control: TreeView
documentation: ug
---

# Getting Started

The Essential ASP.NET WebForms TreeView property represents hierarchical data in a tree-like structure. TreeView allows you to edit, drag items to other TreeView, add check boxes, etc. Refer to the following section, to customize TreeView in a real time Mail Box Scenario that helps you to show items in a Mailbox with necessary features of TreeView property. The following screenshot demonstrates the functions of TreeView property with Drag and Drop option.

![http://help.syncfusion.com/ug/js/ImagesExt/image30_17.png](Getting-Started_images/Getting-Started_img1.png) 

In the above screenshot, you can select the mailbox items and you can write the corresponding functions of the selected item. You can drag and drop the item from one group to another group by using the Drag and Drop option. You can use the Splitter control to split the mail options and its corresponding functions.

## Create the Splitter 

The Essential ASP.NET WebForms Splitter is a layout control that allows you to divide a web page into distinct areas by using the resizable panes. ManySplitter panes are created and placed inside the Splitter control and the split bars are inserted automatically between the adjacent panes. For more information about the splitter refer to the Splitter-Getting Started documentation.

Create a WebForms Project and add necessary Dll’s and scripts with the help of the given [WebForms-Getting Started](http://help.syncfusion.com/ug/js/Documents/gettingstartedwithmv.htm) Documentation.

Add the following code to the corresponding design page for rendering the Splitter window. 

{% highlight html %}

<div>

    <ej:splitter height="251" width="601" id="outersplitter" runat="server">

            <ej:SplitPane >

                <div class="splitdiv"> </div >

            </ej:SplitPane >

            <ej:SplitPane >

                <div> </div >

            </ej:SplitPane >

 </ej:splitter>

</div>

{% endhighlight %}

![http://help.syncfusion.com/ug/js/ImagesExt/image30_12.png](Getting-Started_images/Getting-Started_img2.png) 



### Configure TreeView inside the Splitter widget

Essential ASP.NET WebForms TreeView widget basically renders with built-in features like keyboard navigation with animations and flexible API’s.Essential ASP.NET WebForms can be generated from UL LI elements, JSON data source or by using OData service.

In this application, you can create the TreeView with the JSON data source.

You can style the right pane and render TreeView by adding <div> element in the splitter <div> elements for the Mailbox application.

Add the following style section to render the Splitter layout.

{% highlight css %}

<style type="text/css">

     #<%=outersplitter.ClientID%>

    {

        margin: 50px 0 0 50px;

    }

    .splitdiv

    {

        font-size: 14px;

        font-family: sans-serif;

    }

    .mailHead

    {

        font-weight: bold;

        text-align: center;

    }

    .cont

    {

        padding: 40px 0 0 10px;

        text-align: center;

    }

</style>

{% endhighlight %}

Add TreeView initialization inside the Splitter section.

{% highlight html %}

<ej:Splitter Height="250" Width="601" ID="outersplitter" runat="server">

            <ej:SplitPane>

                <div class="splitdiv">

                    <div>

< ej:TreeView ID="Mailbox" runat="server">

                        </ ej:TreeView>

                    </div>

                </div>

            </ej:SplitPane>

            <ej:SplitPane>

                <div>

                    <div class="cont">

                        <!-- Div elements for displaying the messages-->

                        <div class="mailHead">

                            My Mail Box</div>

                        <div class="mailCont">

                        </div>

                    </div>

                </div>

            </ej:SplitPane>

</ej:Splitter>

{% endhighlight %}

![http://help.syncfusion.com/ug/js/ImagesExt/image30_18.png](Getting-Started_images/Getting-Started_img3.png) 



### Configure Data Source

Create the JSON Data Source for TreeView and initialize as follows.

Add the following data list in the code behind and bind it to the treeview object by using DataSource property. Map the corresponding fields to TreeView element by using datafields.

{% highlight c# %}

//Define a class in code behind page

public class TreeIconsDataSource

{

    public TreeIconsDataSource()    { }

    public TreeIconsDataSource(int _id, int _parentid, string _text, string_hasChild, string _expanded, string _spriteCssClass)

    {

        this.ID = _id;

        this.ParentID = _parentid;

        this.Text = _text;

        this.HasChild = _hasChild;

        this.Expanded = _expanded;

        this.SpriteCssClass = _spriteCssClass;

    }

//Treeview data source should have Id, ParentId and Text as mandatory

    public int ID { get; set; }

// ParentId takes the value of the parent nodes I

    public int ParentID { get; set; }

//Text to be displayed in the treeview node

    public string Text { get; set; }

//Set to true if node has children

    public string HasChild { get; set; }

//Set to true if node to be expanded initially

    public string Expanded { get; set; }

//Image icon for nodes taken from the sprite css classes

    public string SpriteCssClass { get; set; }

    public List<TreeIconsDataSource> GetTreeIconItems()

    {

        List<TreeIconsDataSource> data = new List<TreeIconsDataSource>();

        data.Add(new TreeIconsDataSource(1, 0, "MailBox", "true", "true", "mailicon sprite-root"));

        data.Add(new TreeIconsDataSource(2, 1, "Calendar", "", "", "mailicon sprite-calendar"));

        data.Add(new TreeIconsDataSource(3, 1, "Contacts", "", "", "mailicon sprite-contacts"));

        data.Add(new TreeIconsDataSource(4, 1, "Deleted Items", "", "", "mailicon sprite-deleted"));

        data.Add(new TreeIconsDataSource(5, 1, "Drafts", "", "", "mailicon sprite-drafts"));

        data.Add(new TreeIconsDataSource(6, 1, "Inbox", "true", "", "mailicon sprite-inbox"));

        data.Add(new TreeIconsDataSource(7, 6, "Incidents", "", "", "mailicon sprite-folder"));

        data.Add(new TreeIconsDataSource(8, 6, "Forums", "", "", "mailicon sprite-folder"));

        data.Add(new TreeIconsDataSource(9, 6, "Issues", "", "", "mailicon sprite-folder"));

        data.Add(new TreeIconsDataSource(10, 1, "Junk E-mail", "", "", "mailicon sprite-junk"));

         data.Add(new TreeIconsDataSource(12, 10, "Forums", "", "", "mailicon sprite-folder"));

        data.Add(new TreeIconsDataSource(11, 1, "Sent items", "", "", "mailicon sprite-sentitems"));

        return data;

    }

}

//Map the created list data to DataSource property of TreeView

protected void Page_Load(object sender, EventArgs e)

 {

   this.Mailbox.DataSource = new TreeIconsDataSource().GetTreeIconItems().ToList();

 }



{% endhighlight %}



Add the following code in the Splitter section to render the TreeView in the right side pane.

{% highlight html %}

<%--TreeView code inside splitter--%>

<div class="splitdiv">

<%--Map the corresponding TreeView Fields to DataSource items--%>                 

<ej:TreeView ID="Mailbox" runat="server" DataSourceID="ObjectDataSource1"DataTextField="Text" DataIdField="ID"

        DataParentIdField="ParentID" DataHasChildField="HasChild"DataExpandedField="Expanded">

</ej:TreeView>

</div> 



{% endhighlight %}


![http://help.syncfusion.com/ug/js/ImagesExt/image30_19.png](Getting-Started_images/Getting-Started_img4.png) 



### Configure TreeView with Sprite Icons

To design the TreeView look like Mail options application, you can create the Sprite CSS styles for using Mail Icons from the following image source. The source image is taken from the following installed location.

[Installed Drive]:\Users\[user name]\AppData\Local\Syncfusion\EssentialStudio\{{site.releaseversion}}\Web \Samples\web\Content\images\mail\ mailicons.png

Copy the “mailicons.png” from the above location and paste it in the folder location of the HTML sample page.

You can show the Sprite image icons in TreeView loaded inside the <styles> tag, by using the styles shown in the following code sample.

{% highlight css %}

<style type="text/css">

        .mailicon

        {

            background-image: url("/Images/mailicons.png");

            display: inline-block;

            overflow: hidden;

            background-repeat: no-repeat;

            text-align: center;

            vertical-align: middle;

            width: 20px;

            height: 18px;

        }

        .sprite-calendar

        {

            background-position: -25px -255px;

        }

        .sprite-contacts

        {

            background-position: -26px -429px;

        }

        .sprite-deleted

        {

            background-position: -24px -152px;

        }

        .sprite-drafts

        {

            background-position:-24px -83px;

        }

        .sprite-folder

        {

            background-position: -24px -464px;

        }

        .sprite-folders

        {

            background-position: -24px -222px;

        }



        .sprite-inbox

        {

            background-position: -25px -13px;

        }

        .sprite-junk

        {

            background-position: -23px -187px;

        }

        .sprite-notes

        {

            background-position: -26px -394px;

        }

        .sprite-outbox

        {

            background-position: 0 -414px;

            width: 16px;

            height: 16px;

        }

        .sprite-root

        {

            background-position: -25px -49px;

        }

        .sprite-sentitems

        {

            background-position: -26px -118px;

        }

</style>



{% endhighlight %}

Add the following code in the Splitter section to render the TreeView in the right side pane.

{% highlight html %}

<%-- TreeView code inside splitter--%>

<div class="splitdiv">                            

     <ej:TreeView ID="Mailbox" runat="server" DataSourceID="ObjectDataSource1"DataTextField="Text" DataIdField="ID"

        DataParentIdField="ParentID" DataHasChildField="HasChild"DataExpandedField="Expanded" DataSpriteCssField="SpriteCssClass">

     </ej:TreeView>

  </div>                    



{% endhighlight %}

Execute the above code to render the TreeView with Mail Icons.

![http://help.syncfusion.com/ug/js/ImagesExt/image30_20.png](Getting-Started_images/Getting-Started_img5.png) 



### Set the Node Editing Option 

To rename the mail folders, set AllowEditing property to “true”. You can also use F2 key or double-click the node to rename the node.

{% highlight html %}

<%--TreeView code inside splitter--%>

<div class="splitdiv">                             

<ej:TreeView ID="Mailbox" runat="server" DataSourceID="ObjectDataSource1"DataTextField="Text" DataIdField="ID"

        DataParentIdField="ParentID" DataHasChildField="HasChild"DataExpandedField="Expanded" DataSpriteCssField="SpriteCssClass"AllowEditing="true">

</ej:TreeView>

</div>



{% endhighlight %}

Execute the above code example to render node editing.           

![http://help.syncfusion.com/ug/js/ImagesExt/image30_21.png](Getting-Started_images/Getting-Started_img6.png) 



### Set the Drag and Drop Option 

In this application you can Drag and Drop the folders anywhere inside the mailbox by setting the AllowDragAndDrop option to True.

Execute the following code example to Drag and Drop the nodes anywhere within the TreeView.

{% highlight html %}

<%--TreeView code inside splitter--%>

<div class="splitdiv">

    <div>                            

       <ej:TreeView ID="Mailbox" runat="server" DataSourceID="ObjectDataSource1"DataTextField="Text" DataIdField="ID"

        DataParentIdField="ParentID" DataHasChildField="HasChild"DataExpandedField="Expanded" DataSpriteCssField="SpriteCssClass" Width="400px"AllowEditing="true" AllowDragAndDrop="true">

       </ej:TreeView>

     </div>

</div> 



{% endhighlight %}

### Configure Events for the TreeView

When you click on the Mailbox folder item, the corresponding navigation action is performed in the ClientSideOnNodeSelected event and this is achieved by declaring the ClientSideOnNodeSelected event with the corresponding call back function.  You can rename the folder names and it is not renamed as empty. This validation process is done manually in the ClientSideOnInlineEditValidation event.

{% highlight html %}

<%--TreeView code inside splitter--%>

<div class="splitdiv">

    <div>                              

        <ej:TreeView ID="Mailbox" runat="server" DataSourceID="ObjectDataSource1"DataTextField="Text" DataIdField="ID"

        DataParentIdField="ParentID" DataHasChildField="HasChild"DataExpandedField="Expanded" DataSpriteCssField="SpriteCssClass" Width="400px"AllowEditing="true" AllowDragAndDrop="true" ClientSideOnNodeSelected="treeClicked"ClientSideOnInlineEditValidation="validateFolder">

       </ej:TreeView>

    </div>

</div>



{% endhighlight %}

Initialize the script section to validate editing and select operation.

{% highlight js %}

<script type="text/javascript">

        function validateFolder(args) {

<%--write your code here for other folder creation process.--%>

            if (args.newText === "") <%--Validate the modified text of mailfolder.-- %>

            {

             args.cancel = true;

             alert("Folder name cannot be renamed to empty. So provide some name.");

            }

        } 

        function treeClicked(args) {

<%--write your code here for other process on selecting tree nodes.-- %>

            $(".mailHead").html(args.value);

            $(".mailCont").html("The Contents of <b>" + args.value + "</b> will be displayed here");

        }

</script>



{% endhighlight %}



Execute the above code example to render TreeView. When you select the mail folder in the TreeView, the corresponding action takes place by raising the ClientSideOnNodeSelected event.

![http://help.syncfusion.com/ug/js/ImagesExt/image30_17.png](Getting-Started_images/Getting-Started_img7.png) 



N> The inline edit validation is done when “ClientSideOnInlineEditValidation” event occurs, as in the screenshot as follows. The “ClientSideOnInlineEditValidation” event rises only when the “AllowEditing” property is set to True.



![http://help.syncfusion.com/ug/js/ImagesExt/image30_22.png](Getting-Started_images/Getting-Started_img8.png) 



### Add or Delete the Folders by using Context Menu

You can add or remove the nodes dynamically during runtime. It is achieved by adding the Context Menu option to the TreeView. In the Context Menu, you can configure add or remove the node functions to the TreeView. The following code example illustrates how to configure the Context Menuelements for the TreeView.

Initialize the Context Menu in the Splitter section as follows.

{% highlight html %}

<%--TreeView code inside splitter--%>                     

<div class="splitdiv">

    <div>

        <ej:treeview id="Mailbox" runat="server" datasourceid="ObjectDataSource1" datatextfield="Text"

            dataidfield="ID" dataparentidfield="ParentID" datahaschildfield="HasChild" dataexpandedfield="Expanded"

            dataspritecssfield="SpriteCssClass" width="400px" allowediting="true" allowdraganddrop="true"

            clientsideonnodeselected="treeClicked" clientsideoninlineeditvalidation="validateFolder">

         </ej:treeview>

    </div>

    <!-- Initialize Elements for the context menu -->

    <div>

        <ej:menu id="treeviewMenu" runat="server" menutype="ContextMenu" contextmenutarget="#LayoutSection_ControlsSection_outersplitter_ctl00_Mailbox"

            openonclick="false" showsublevelarrows="true" clientsideonbeforecontextopen="beforeOpen"

            clientsideonclick="menuClick">

            <Items><ej:MenuItem Id="New" Text="New Folder"></ej:MenuItem> </Items>

            <Items><ej:MenuItem Id="Delete" Text="Delete Folder"></ej:MenuItem></Items>

        </ej:menu>

    </div>

</div>

{% endhighlight %}


Initialize the Context Menu in the script section to create new folder and delete folder.


{% highlight js %}

<script type="text/javascript">

        var nodeIndex = 1, treeviewObj, selectedNode;

<%--Refer to the code for Tree click event and node editing validation--%>

        function beforeOpen(args) {

<%--creating the treeview object before the context menu opens with the selected node--%>

        treeviewObj =$("#LayoutSection_ControlsSection_outersplitter_ctl00_Mailbox").data("ejTreeView");<%--Creating the treeview object--%>

            if (!$(args.target).hasClass("e-text"))

                args.cancel = true; <%--write your code here for other process.--%>



            else {

                selectedNode = args.target;

                treeviewObj.selectNode(selectedNode); <%--selectNode method for treeview.--%>

            }

        }

        function menuClick(args) {

        treeviewObj =$("#LayoutSection_ControlsSection_outersplitter_ctl00_Mailbox").data("ejTreeView");<%--Creating the treeview object--%>

            if (args.events.ID == "New") {

<%--creating the new node in the treeview by using addNode method--%>



                treeviewObj.addNode("New Folder" + nodeIndex, selectedNode);

                nodeIndex++;

            }

            else if (args.events.ID == "Delete") {

<%--Deleting the existing node in the treeview--%>

                treeviewObj.removeNode(selectedNode);

                $(".mailHead").html("My Mail Box");

                $(".mailCont").html("");

            }

        }

</script>

{% endhighlight %}

The following screenshot illustrates adding of new folder in the TreeView by using the Context Menu. You can right-click on the TreeView Node and select the new folder option in the Context Menu for the selected folder.

 ![http://help.syncfusion.com/ug/js/ImagesExt/image30_23.png](Getting-Started_images/Getting-Started_img9.png)


![http://help.syncfusion.com/ug/js/ImagesExt/image30_24.png](Getting-Started_images/Getting-Started_img10.png)


The following screenshot illustrates the deleting of new folder that is created as a child of the “Drafts” folder. You can right-click on the New Folder1 and select the Delete Folder option in the Context Menu.

 ![http://help.syncfusion.com/ug/js/ImagesExt/image30_25.png](Getting-Started_images/Getting-Started_img11.png)
 

![http://help.syncfusion.com/ug/js/ImagesExt/image30_17.png](Getting-Started_images/Getting-Started_img12.png)