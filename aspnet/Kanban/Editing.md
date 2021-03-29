---
layout: post
title: Editing with Kanban widget for Syncfusion Essential ASP.NET
description:  How to perform editing and configure edit items functionalities like edit type, edit control etc
platform: aspnet
control: Kanban
documentation: ug
---
# Editing

The Kanban control has support for dynamic insertion, updating and deletion of cards.

Set `AllowEditing` and `AllowAdding` property as true to enable editing/inserting respectively. The primary key for the data source should be defined in `PrimaryKey`, for editing to work properly.
You can start the edit action by double clicking the particular card. Similarly, you can add new card to Kanban either by double clicking the particular cell or on an external button which is bound to call `addCard` method of Kanban.
Deletion of the card is possible by using `deleteCard` by passing primary key as attribute.

N> In Kanban, the `primary key` column will be automatically set to read only while editing the card which is to avoid duplicate entry in the cards. 

## Configuring Edit Items

You need to configure the list of data source fields that are allowable in editing state using `EditItems` property. The `KanbanEditItem` property of `EditItems` needs to be mapped with data source fields.

You can map the data source field as title to edit form using `Title` property of `Fields`. By default, it’s mapped with `PrimaryKey`.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

          <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true">
                    <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Assignee"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Numeric" Field="Estimate">
                            <NumericEditOptions DecimalPlaces="2" />
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="TextArea" Field="Summary">
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image1](Editing_images/Editing_img1.png)

## Edit modes

### Dialog

Set `EditMode` as `Dialog` to edit data using a dialog box, which displays the fields associated with the data card being edited. Default value is `Dialog`.

The following code example describes the above behavior 

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="Dialog">
                    <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Assignee"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Numeric" Field="Estimate">
                            <NumericEditOptions DecimalPlaces="2" />
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="TextArea" Field="Summary">
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}  

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image2](Editing_images/Editing_img1.png)


### Dialog Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later.
Using this template support, you can edit the fields that are not bound to `EditItems`.

To edit the cards using Dialog template form, set `EditMode` as `DialogTemplate` and specify the template id to `DialogTemplate` property of `EditSettings`.

N> 1.`value` attribute is used to bind the corresponding field value while editing.
N> 2.`name` attribute is used to get the changed field values while save the edited card.


The following code example describes the above behavior.

{% highlight html %}

     <script type="text/template" id="template">
                <table cellspacing="10">
                    <tr>
                        <td style="text-align: right;">Id
                        </td>
                        <td style="text-align: left">
                            <input id="Id" name="Id" value="{{: Id}}" class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                        </td>
                        <td style="text-align: right;">Status
                        </td>
                        <td style="text-align: left">
                            <select id="Status" name="Status">
                                <option value="Close">Close</option>
                                <option value="InProgress">InProgress</option>
                                <option value="Open">Open</option>
                                <option value="Testing">Testing</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td style="text-align: right;">Estimate
                        </td>
                        <td style="text-align: left">
                            <input type="text" id="Estimate" name="Estimate" value="{{:Estimate}}" />
                        </td>
                        <td style="text-align: right;">Assignee
                        </td>
                        <td style="text-align: left">
                            <select id="Assignee" name="Assignee">
                                <option value="Nancy">Nancy Davolio</option>
                                <option value="Andrew">Andrew Fuller</option>
                                <option value="Janet">Janet Leverling</option>
                                <option value="Margaret">Margaret Hamilton</option>
                                <option value="Steven">Steven walker</option>
                                <option value="Michael">Michael Suyama</option>
                                <option value="Robert">Robert King</option>
                                <option value="Laura">Laura Callahan</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td style="text-align: right;">Tags
                        </td>
                        <td style="text-align: left">
                            <input id="Tags" name="Tags" value="{{: Tags}}" class="e-field e-ejinputtext valid" style="width: 175px; height: 28px" />
                        </td>
                        <td style="text-align: right;">Priority
                        </td>
                        <td style="text-align: left">
                            <select id="Priority" name="Priority">
                                <option value="Low">Low</option>
                                <option value="High">High</option>
                                <option value="Critical">Critical</option>
                                <option value="Normal">Normal</option>
                                <option value="Release Breaker">Release Breaker</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td style="text-align: right;">Summary
                        </td>
                        <td style="text-align: left">
                            <textarea id="Summary" name="Summary" class="e-ejinputtext" value="{{: Summary}}" style="width: 270px; height: 95px">{{: Summary}}</textarea>
                        </td>
                    </tr>
                </table>
            </script>

{% endhighlight  %}

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="DialogTemplate" DialogTemplate="#template">
                </EditSettings>
                <ClientSideEvents ActionComplete="complete" />
     </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

While using template, you can change the elements that are defined in the `template`, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using `ActionComplete` event of Kanban. Please refer to following code snippets.

{% highlight html %}

      <script type="text/javascript">
                function complete(args) {
                    if (args.requestType == "refresh" || args.requestType == "save") {
                        $('#<%= Kanban.ClientID %>').ejWaitingPopup("hide");
                   }
                   if ((args.requestType == "beginedit" || args.requestType == "add") && args.model.editSettings.editMode == "dialogtemplate") {
                       $("#Estimate").ejNumericTextbox({ value: parseFloat($("#Estimate").val()), width: "175px", height: "34px", decimalPlaces: 2 });
                       $("#Assignee").ejDropDownList({ width: '175px' });
                       $("#Status").ejDropDownList({ width: '175px' });
                       $("#Priority").ejDropDownList({ width: '175px' });
                       if (args.requestType == "beginedit" || args.requestType == "add") {
                           $("#Assignee").ejDropDownList("setSelectedValue", args.data['Assignee']);
                           $("#Priority").ejDropDownList("setSelectedValue", args.data['Priority']);
                           $("#Status").ejDropDownList("setSelectedValue", args.data['Status']);
                       }
                       $(".e-field").css({ 'width': '175px', 'text-align': 'left' });
                   }
               }
        </script>

{% endhighlight  %}

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image3](Editing_images/Editing_img2.png)

### External Form

Set the `EditMode` as `ExternalForm` to open the edit form in outside kanban content.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="ExternalForm">
                    <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="TextArea" Field="Summary">
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}  

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image11](Editing_images/editing_img11.png)

Form Position:

Form Position can be customized by setting the `FormPosition` as "right" or "bottom".

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="ExternalForm" FormPosition="Right">
                     <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Assignee"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Numeric" Field="Estimate">
                            <NumericEditOptions DecimalPlaces="2" />
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="TextArea" Field="Summary">
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}  

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image12](Editing_images/editing_img12.png)

### External Template Form

You can edit any of the fields pertaining to a single card of data and apply it to a template so that the same format is applied to all the other cards that you may edit later. 

Using this template support, you can edit the fields that are not bound to Kanban Edit Items.

To edit the cards using External template form, set `EditMode` as `ExternalFormTemplate` and specify the template id to `ExternalFormTemplate` property of `EditSettings`.

While using template, you can change the elements that are defined in the template, to appropriate Syncfusion JS controls based on the column type. This can be achieved by using `ActionComplete` event of Kanban.

N> 1. `value` attribute is used to bind the corresponding field value while editing. 
N> 2. `name` attribute is used to get the changed field values while save the edited card. 
N> 3. For `EditMode` property you can assign `enum` value (`ExternalFormTemplate`).

The following code example describes the above behavior.

{% highlight html %}

     <script type="text/template" id="template">
                <table cellspacing="10">
                    <tr>
                        <td style="text-align: right;">Id
                        </td>
                        <td style="text-align: left">
                            <input id="Id" name="Id" value="{{: Id}}" class="e-field e-ejinputtext valid e-disable" style="text-align: right; width: 175px; height: 28px" disabled="disabled" />
                        </td>
                        <td style="text-align: right;">Status
                        </td>
                        <td style="text-align: left">
                            <select id="Status" name="Status">
                                <option value="Close">Close</option>
                                <option value="InProgress">InProgress</option>
                                <option value="Open">Open</option>
                                <option value="Testing">Testing</option>
                            </select>
                        </td>
                    </tr>
                    <tr>
                        <td style="text-align: right;">Assignee
                        </td>
                        <td style="text-align: left">
                            <select id="Assignee" name="Assignee">
                                <option value="Nancy">Nancy Davolio</option>
                                <option value="Andrew">Andrew Fuller</option>
                                <option value="Janet">Janet Leverling</option>
                                <option value="Margaret">Margaret Hamilton</option>
                                <option value="Steven">Steven walker</option>
                                <option value="Michael">Michael Suyama</option>
                                <option value="Robert">Robert King</option>
                                <option value="Laura">Laura Callahan</option>
                            </select>
                        </td>
                    </tr>
                </table>
            </script>

{% endhighlight  %}

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="ExternalFormTemplate" ExternalFormTemplate="#template">
                </EditSettings>
                <ClientSideEvents ActionComplete="complete" />
     </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

{% highlight html %}

      <script type="text/javascript">
                function complete(args) {
                    if (args.requestType == "refresh" || args.requestType == "save") {
                        $('#<%= Kanban.ClientID %>').ejWaitingPopup("hide");
                   }
                   if ((args.requestType == "beginedit" || args.requestType == "add") && args.model.editSettings.editMode == "externalformtemplate") {
                       $("#Assignee").ejDropDownList({ width: '175px' });
                       $("#Status").ejDropDownList({ width: '175px' });
                       if (args.requestType == "beginedit" || args.requestType == "add") {
                           $("#Assignee").ejDropDownList("setSelectedValue", args.data['Assignee']);
                           $("#Status").ejDropDownList("setSelectedValue", args.data['Status']);
                       }
                       $(".e-field").css({ 'width': '175px', 'text-align': 'left' });
                   }
               }
        </script>

{% endhighlight  %}

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image13](Editing_images/editing_img13.png)

## Cell edit type and its params

The edit type of bound column can be customized using `EditType` property of `Columns`. The following Essential JavaScript controls are supported built-in by `EditType`. You can set the `EditType` based on specific data type of the column.

<table>
<tr>
<th>
EditType </th><th>
EditParams</th><th>
Description </th><th>
Example</th></tr>
<tr>
<td>
Numeric</td><td>
TextBoxes</td><td>
control for integers, double and decimal data’s</td><td>
<NumericEditOptions DecimalPlaces="2" /></td></tr>
<tr>
<td>
String</td><td>
HTML Textbox</td><td>
HTML Textbox</td><td>
-</td></tr>
<tr>
<td>
DatePicker</td><td>
DatePicker</td><td>
control for date data</td><td>
<DateEditOptions ButtonText="Now" /></td></tr>
<tr>
<td>
DateTimePicker</td><td>
DateTimePicker</td><td>
control for date data-time data</td><td>
<DateTimeEditOptions Enabled="true"/></td></tr>
<tr>
<td>
DropDown</td><td>
DropDownList</td><td>
control for list of data</td><td>
<DropdownEditOptions AllowGrouping="true"/></td></tr>
<tr>
<td>
RTE</td><td>
RTE</td><td>
control for customizing text in RTE format</td><td>
<RTEEditOptions EnableResize="true"></RTEEditOptions></td></tr>
<tr>
<td>
TextArea</td><td>
HTML TextArea</td><td>
Control for multi-line plain-text editing</td><td>
-</td></tr>
</table>

N> If `EditType` is not set, then by default it will display HTML `textbox` while editing a card.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="Dialog">
                    <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Numeric" Field="Estimate">
                            <NumericEditOptions DecimalPlaces="2" />
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="RTE" Field="Summary">
                            <RTEEditOptions Height="150" MinHeight="100">
                            </RTEEditOptions>
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image4](Editing_images/Editing_img3.png)


## Column Validation

We can validate the value of the added or edited card cell before saving. The below validation script files are needed when editing is enabled with validation.

  1. jquery.validate.min.js
  2. jquery.validate.unobtrusive.min.js

N> If you enabled the unobtrusive option, then need to refer the jquery.validate.unobtrusive.min.js

file in your application along with the other script.

### jQuery Validation

You can set validation rules using `ValidationRules` property of `Columns`. The following are jQuery validation methods.

__List__ __of__ __Jquery__ __validation__ __methods__

<table>
<tr>
<th>
Rules</th><th>
Description</th></tr>
<tr>
<td>
required</td><td>
Requires an element.</td></tr>
<tr>
<td>
remote</td><td>
Requests a resource to check the element for validity.</td></tr>
<tr>
<td>
minlength</td><td>
Requires the element to be of given minimum length.</td></tr>
<tr>
<td>
maxlength</td><td>
Requires the element to be of given maximum length.</td></tr>
<tr>
<td>
rangelength</td><td>
Requires the element to be in given value range.</td></tr>
<tr>
<td>
min</td><td>
The element requires a given minimum.</td></tr>
<tr>
<td>
max</td><td>
The element requires a given maximum.</td></tr>
<tr>
<td>
range</td><td>
Requires the element to be in a given value range.</td></tr>
<tr>
<td>
email</td><td>
The element requires a valid email.</td></tr>
<tr>
<td>
url</td><td>
The element requires a valid URL</td></tr>
<tr>
<td>
date</td><td>
Requires the element to be a date.</td></tr>
<tr>
<td>
dateISO</td><td>
The element requires an ISO date.</td></tr>
<tr>
<td>
number</td><td>
The element requires a decimal number.</td></tr>
<tr>
<td>
digits</td><td>
The element requires digits only.</td></tr>
<tr>
<td>
creditcard</td><td>
Requires the element to be a credit card number.</td></tr>
<tr>
<td>
equalTo</td><td>
Requires the element to be the same as another.</td></tr>
</table>

Kanban supports all the standard validation methods of jQuery, please refer the jQuery validation documentation [link](http://jqueryvalidation.org/documentation/# "link") for more information.

The following code example describes the above behavior.

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="Dialog">
                    <EditItems>
                        <ej:KanbanEditItem EditType="String" Field="Id">
                            <ValidationRules>
                                <ej:KeyValue Key="required" Value="true" />
                            </ValidationRules>
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Dropdown" Field="Assignee"></ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="Numeric" Field="Estimate">
                            <NumericEditOptions DecimalPlaces="2" />
                            <ValidationRules>
                                <ej:KeyValue Key="range" Value="[0, 1000]" />
                            </ValidationRules>
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem EditType="TextArea" Field="Summary">
                            <ValidationRules>
                                <ej:KeyValue Key="required" Value="true" />
                            </ValidationRules>
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
            </ej:Kanban>

{% endhighlight  %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}  

The following output is displayed as a result of the above code example.

![ASPNET Kanban Editing image5](Editing_images/Editing_img4.png)

## Persisting data in server

Edited data can be persisted in database using RESTful web services.

All the CRUD operations in Kanban are done through DataManager. DataManager have an option to bind all the CRUD related data in server side. Please refer the [link](https://help.syncfusion.com/aspnet/datamanager/overview) to know about the DataManager.

### WebMethod Adaptor

You can use the `WebMethodAdaptor` of `DataManager` when binding `DataSource` from remote data. At initial load of Kanban, using URL property of DataManager, data are fetched from remote data and bound to Kanban. You can map CRUD operation in Kanban to Server-Side Controller action using the property `CrudURL`.

The following code example describes the above behavior.

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status">
                <DataManager URL="KanbanFeatures.aspx/GetData" CrudURL="KanbanFeatures.aspx/Crud" Adaptor="WebMethodAdaptor" />
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress" />
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <Fields Content="Summary" PrimaryKey="Id" />
                <EditSettings AllowAdding="true" AllowEditing="true" EditMode="Dialog">
                    <EditItems>
                        <ej:KanbanEditItem Field="Id">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem Field="Status"></ej:KanbanEditItem>
                        <ej:KanbanEditItem Field="Assignee"></ej:KanbanEditItem>
                        <ej:KanbanEditItem Field="Estimate">
                        </ej:KanbanEditItem>
                        <ej:KanbanEditItem Field="Summary">
                        </ej:KanbanEditItem>
                    </EditItems>
                </EditSettings>
                <ClientSideEvents ToolbarClick="toolbarClick" />
                <CustomToolBarItems>
                    <ej:KanbanCustomToolBarItems Template="#Delete" />
                </CustomToolBarItems>
            </ej:Kanban>
            
            <script id="Delete" type="text/x-jsrender">
                <a class="e-customdelete  e-icon" />
            </script>
            
            <script type="text/javascript">
                function toolbarClick(args) {
                    if (args.itemName == "Delete" && this.element.find(".e-kanbancard").hasClass("e-cardselection")) {
                        var selected= this.element.find(".e-cardselection");
                        this.KanbanEdit.deleteCard(selected.attr("id"));
                    }
                }
            </script>
            
            <style type="text/css">
                .e-customdelete:before {
                    content: "\e800";
                    line-height: 26px;
                    min-height: 26px;
                    min-width: 14px;
                    display: inline-block;
                }
            </style>

{% endhighlight  %}

Also when you use `WebMethodAdaptor`, you need to return the data as JSON and the JSON object must contain a properties result & count. The `result` holds the `dataSource` as its value and `count` holds the total cards count as its value.

The following code example describes the above behavior.

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object GetData(Syncfusion.JavaScript.DataManager value)
        {
            NORTHWNDEntities1 db = new NORTHWNDEntities1();
            IEnumerable Data = db.Tasks.ToList();
            int count = Data.AsQueryable().Count();
            Syncfusion.JavaScript.DataSources.DataOperations operation = new Syncfusion.JavaScript.DataSources.DataOperations();
            Data = operation.Execute(Data, value);
            return new { result = Data, count = count };
        } 

{% endhighlight  %}

Please refer to the below screenshot.

![ASPNET Kanban Editing image6](Editing_images/Editing_img5.png)

Using `DataOperations` helper class you can perform Kanban action at server side. The in-built methods that we have provided in the `DataOperations` class are listed below.

1.	PerformTake
2.	PerformSelect
3.	Execute

### Accessing CRUD action request details in server side

The Server-Side function must be declared with the following parameter name for each editing functionality.

#### Parameters Table

<table>
<tr>
<th>Action</th>
<th>Parameter Name</th>
<th>Example</th>
</tr>
<tr>
<td>
Update, Insert, Remove, Crud Update(Multiple cards data will be passed to the server when drag and drop enabled with priority.)
</td>
<td>
Changed values,
Added values,
Deleted value
</td>
<td>
public static object Crud(List<Task> `changed`, List<Task> `added`, List<Task> `deleted`)
</td>
</tr>
</table>

### Insert Card

Using `CrudURL` property, you can specify the controller action mapping URL to perform `insert` operation at server side.

The following code example describes the above behavior.

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object Crud(List<Task> changed, List<Task> `added`, List<Task> deleted)
        {
            NORTHWNDEntities1 db = new NORTHWNDEntities1();

            // Insert card in the database.
            if (added != null && added.Count() > 0)
            {
                foreach (var temp in added)
                {
                    db.Tasks.Add(temp);
                }
            }
            db.SaveChanges();
            var dataSource = db.Tasks.ToList();
            return dataSource;

{% endhighlight  %}

The newly added card details are bound to the `added` parameter. Please refer the below image.

![ASPNET Kanban Editing image7](Editing_images/Editing_img6.png)

### Update Card

Using `CrudURL` property, you can specify the controller action mapping URL to perform `save/update` operation at server side. 

The following code example describes the above behavior.

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object Crud(List<Task> `changed`, List<Task> added, List<Task> deleted)
        {
            NORTHWNDEntities1 db = new NORTHWNDEntities1();
            //Update card in the database.

            if (changed != null && changed.Count() > 0)
            {
                foreach (var temp in changed)
                {
                    Task old = db.Tasks.Where(o => o.Id == temp.Id).SingleOrDefault();
                    if (old != null)
                    {
                        db.Entry(old).CurrentValues.SetValues(temp);
                    }
                }
            }
            db.SaveChanges();
            var dataSource = db.Tasks.ToList();
            return dataSource;
        }

{% endhighlight  %}

The updated card details are bound to the `changed` parameter. Please refer the below image.

![ASPNET Kanban Editing image8](Editing_images/Editing_img7.png)

### Delete Card

Using `CrudURL` property, you can specify the controller action mapping URL to perform `delete`  operation at server side.

The following code example describes the above behavior.

{% highlight c# %}

        [WebMethod]
        [ScriptMethod(ResponseFormat = ResponseFormat.Json)]
        public static object Crud(List<Task> changed, List<Task> added, List<Task> `deleted`)
        {
            NORTHWNDEntities1 db = new NORTHWNDEntities1();

            //Delete card in the database.
            if (deleted != null && deleted.Count() > 0)
            {
                foreach (var temp in deleted)
                {
                    db.Tasks.Remove(db.Tasks.Where(o => o.Id == temp.Id).SingleOrDefault());
                }
            }
            db.SaveChanges();
            var dataSource = db.Tasks.ToList();
            return dataSource;
        } 
        
{% endhighlight  %}

The deleted card details are bound to the `deleted` parameter. Please refer the below image.

![ASPNET Kanban Editing image9](Editing_images/Editing_img8.png)