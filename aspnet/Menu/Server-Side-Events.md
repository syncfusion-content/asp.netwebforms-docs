---
layout: post
title: Server Side Events | Menu | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Menu
documentation: ug
---

# Server Side Events

<table>
<tr>
<th>
Event Name</th><th>
Description</th><th>
Parameters</th></tr>
<tr>
<td>
OnItemClick</td><td>
Event gets triggered when the menu item is clicked</td><td>
(Object Sender, MenuEventArgs e)Values passed in argument are as follows,ID - to get the ID of the current menu itemParentId - to get the ID of the parent menu itemSelectedItems - returns the selected menu itemText - to get the Text of the current menu itemEventType - returns the event name</td></tr>
</table>


The following steps explains you on how to define server side event for a Menu control.

In an ASPX page, define the Menu control and add the sub menu items correspondingly.

{% highlight html %}



    <ej:Menu ID="MenuControl" Width="500" runat="server" OnItemClick="MenuControl_ItemClick">

        <Items>

            <ej:MenuItem Id="Home" Text="Home">

                <Items>

                    <ej:MenuItem Text="Foundation"></ej:MenuItem>

                </Items>

                <Items>

                    <ej:MenuItem Text="Launch"></ej:MenuItem>

                </Items>

                <Items>

                    <ej:MenuItem Text="About">

                        <Items>

                            <ej:MenuItem Text="Company"></ej:MenuItem>

                        </Items>

                        <Items>

                            <ej:MenuItem Text="Location"></ej:MenuItem>

                        </Items>

                    </ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Id="Services" Text="Services">

                <Items>

                    <ej:MenuItem Text="Consulting"></ej:MenuItem>

                </Items>

                <Items>

                    <ej:MenuItem Text="Outsourcing"></ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Id="About" Text="About"></ej:MenuItem>

            <ej:MenuItem Id="Contact" Text="Contact us">

                <Items>

                    <ej:MenuItem Text="Contact Number"></ej:MenuItem>

                </Items>

                <Items>

                    <ej:MenuItem Text="Email"></ej:MenuItem>

                </Items>

            </ej:MenuItem>

            <ej:MenuItem Id="Careers" Text="Careers">

                <Items>

                    <ej:MenuItem Text="Position">

                        <Items>

                            <ej:MenuItem Text="Developer"></ej:MenuItem>

                        </Items>

                        <Items>

                            <ej:MenuItem Text="Manager"></ej:MenuItem>

                        </Items>

                    </ej:MenuItem>

                </Items>

                <Items>

                    <ej:MenuItem Text="Apply online"></ej:MenuItem>

                </Items>

            </ej:MenuItem>

        </Items>

    </ej:Menu>

</div>



{% endhighlight %}



In the code behind define the action to be performed on clicking the menu item.

{% highlight c# %}



protected void MenuControl_ItemClick(object sender, Syncfusion.JavaScript.Web.MenuEventArgs e)

{

    // e.ID - to get the ID of the current menu item

    // e.ParentId - to get the ID of the parent menu item

    // e.SelectedItems - returns the selected menu item

    // e.Text - to get the Text of the current menu item

    // e.EventType - returns the event name

}



{% endhighlight %}



