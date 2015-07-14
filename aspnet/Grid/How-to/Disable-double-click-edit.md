---
layout: post
title: Disable-double-click-edit
description: disable double-click edit
platform: aspnet
control: Grid
documentation: ug
---

### Disable double-click edit

The AllowEditOnDblClick property can be set as True to enable editing the record by double-clicking it. When it is set as False, it cannot be edited by double-clicking it. In that case, you can edit the record by using the Toolbar option only.

[ASP]

[aspx]

  &lt;ej:Grid ID="OrdersGrid" runat="server" AllowPaging="True" &gt;

&lt;DataManager URL="http://mvc.syncfusion.com/Services/Northwnd.svc/Orders/" Offline="true"&gt;&lt;/DataManager&gt;



            &lt;Columns&gt;

                &lt;ej:Column Field="OrderID" HeaderText="Order ID" IsPrimaryKey="true" TextAlign="Right" Width="75" /&gt;

                &lt;ej:Column Field="CustomerID" HeaderText="Customer ID" Width="80" /&gt;

                &lt;ej:Column Field="EmployeeID" HeaderText="Employee ID" TextAlign="Right" Width="70" EditType=" Numeric" /&gt;

                &lt;ej:Column Field="ShipCity" HeaderText="Ship City" Width="100" EditType="Dropdown" /&gt;



            &lt;/Columns&gt;

            &lt;EditSettings AllowEditing="True" AllowEditOnDblClick="False" AllowAdding="True" AllowDeleting="True" EditMode="Normal"&gt;&lt;/EditSettings&gt;

            &lt;ToolbarSettings ShowToolbar="True" ToolbarItems="add,edit,delete,update,cancel"&gt;&lt;/ToolbarSettings&gt;

        &lt;/ej:Grid&gt;







The following output is displayed as a result of the above code example.

{ ![](Disable-double-click-edit_images/Disable-double-click-edit_img1.png) | markdownify }
{:.image }


