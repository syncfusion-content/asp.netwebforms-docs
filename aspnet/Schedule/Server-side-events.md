---
layout: post
title: Server-side events of ASP.NET Web Forms Scheduler
description: Complete server-side events available in Scheduler along with its accessible argument details on the Syncfusion ASP.NET Web Forms Schedule control.
platform: aspnet
control: Schedule
documentation: ug
---

## Server-side events

This section explains in detail about the various server-side events available in the ASP.NET Web Forms Scheduler control and the arguments that are available on those events. 

The **sender** parameter of all the server-side events returns the scheduler model details. The **Syncfusion.JavaScript.Web.ScheduleEventArgs** arguments provide information specific to each event.

The various server-side events and the corresponding arguments of it are as follows.

## OnServerBeforeAppointmentCreate

The **OnServerBeforeAppointmentCreate** event is triggered before the new appointment gets saved. The details of the created appointment can be obtained server-side, as explained in the following table.

_Table 1: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerBeforeAppointmentCreate event_

<table class="params">
        <thead>
            <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="name">EventArgs</td>
                <td class="type">ScheduleEventArgs</td>
                <td class="description">Returns the details of newly created appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                            <thead>
                                                <tr>
                                                    <th>Name</th>
                                                    <th>Type</th>
                                                    <th>Description</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td class="name">appointment</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the newly added appointment details.</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="name">EventType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the Event type detail - 'beforeAppointmentCreate".</td>
                                    </tr>
                                </tbody>
                            </table>
                </td>
            </tr>
        </tbody>
    </table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerBeforeAppointmentCreate="Schedule1_ServerBeforeAppointmentCreate" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerBeforeAppointmentCreate(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the newly creating appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerBeforeAppointmentCreate(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the newly creating appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
	
## OnServerBeforeAppointmentChange

The **OnServerBeforeAppointmentChange** event is triggered before the edited appointment is being saved. The details of the edited appointment can be obtained server-side, as explained in the following table.

_Table 2: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerBeforeAppointmentChange event_

<table class="params">
        <thead>
            <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="name">EventArgs</td>
                <td class="type">ScheduleEventArgs</td>
                <td class="description">Returns the details of created appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                            <thead>
                                                <tr>
                                                    <th>Name</th>
                                                    <th>Type</th>
                                                    <th>Description</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td class="name">appointment</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the edited appointment details.</td>
                                                </tr>
                                                <tr>
                                                    <td class="name">currentAction</td>
                                                    <td class="type">string</td>
                                                    <td class="description">Returns the current action detail.Please find the possible current action values are as follows.
                                                        <table class="params">
                                                            <thead>
                                                                <tr>
                                                                    <td>Name</td>
                                                                    <td>Description</td>
                                                                </tr>
                                                            </thead>
                                                            <tbody>
                                                                <tr>
                                                                    <td>edit</td>
                                                                    <td>Returns when updating normal appointment.</td>
                                                                <tr>
                                                                <tr>
                                                                    <td>editOccurrence</td>
                                                                    <td>Returns when updating single occurrence from Recurrence series.</td>
                                                                <tr>
                                                                <tr>
                                                                    <td>editSeries</td>
                                                                    <td>Returns when updating entire series.</td>
                                                                <tr>
                                                            </tbody>
                                                        </table>
                                                    </td>
                                                </tr>
                                                <tr>
                                                    <td class="name">recurrenceCollection</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the recurrence appointment details.
                                                        <table class="params">
                                                            <thead>
                                                                <tr>
                                                                    <td>Name</td>
                                                                    <td>Type</td>
                                                                    <td>Description</td>
                                                                </tr>
                                                            </thead>
                                                            <tbody>
                                                                <tr>
                                                                    <td>occurrences</td>
                                                                    <td>object</td>
                                                                    <td>Returns the edited occurrence appointment detail.</td>
                                                                <tr>
                                                                <tr>
                                                                    <td>parentData</td>
                                                                    <td>object</td>
                                                                    <td>Returns the edited occurrence parent appointment detail.</td>
                                                                <tr>
                                                            </tbody>
                                                        </table>
                                                    </td>
                                                </tr>
                                                <tr>
                                                    <td class="name">ignoreEditedOccurrences</td>
                                                    <td class="type">boolean</td>
                                                    <td class="description">Returns the value to decide the edited occurrence to be ignored or not while updating the appointment.
                                                    </td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="name">EventType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the Event type detail - 'beforeAppointmentChange".</td>
                                    </tr>
                                </tbody>
                            </table>
                </td>
            </tr>
        </tbody>
    </table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerBeforeAppointmentChange="Schedule1_ServerBeforeAppointmentChange" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerBeforeAppointmentChange(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the editing appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerBeforeAppointmentChange(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the editing appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerBeforeAppointmentRemove

The **OnServerBeforeAppointmentRemove** event is triggered before the appointment is being removed from the Scheduler. The details of the deleted appointment can be obtained server-side, as explained in the following table.

_Table 3: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerBeforeAppointmentRemove event_

<table class="params">
        <thead>
            <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="name">EventArgs</td>
                <td class="type">ScheduleEventArgs</td>
                <td class="description">Returns the details of deleted appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                            <thead>
                                                <tr>
                                                    <th>Name</th>
                                                    <th>Type</th>
                                                    <th>Description</th>
                                                </tr>
                                            </thead>
                                            <tbody>
                                                <tr>
                                                    <td class="name">appointment</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the deleted appointment details.</td>
                                                </tr>
                                                <tr>
                                                    <td class="name">currentAction</td>
                                                    <td class="type">string</td>
                                                    <td class="description">Returns the current action detail.</td>
                                                </tr>
                                            </tbody>
                                        </table>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="name">EventType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the Event type detail - 'beforeAppointmentRemove".</td>
                                    </tr>
                                </tbody>
                            </table>
                </td>
            </tr>
        </tbody>
    </table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerBeforeAppointmentRemove="Schedule1_ServerBeforeAppointmentRemove" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

       protected void Schedule1_ServerBeforeAppointmentRemove(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the deleting appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerBeforeAppointmentRemove(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the deleting appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerAppointmentCreated

The **OnServerAppointmentCreated** event is triggered after the new appointment is saved. The details of the new appointment can be obtained server-side, as explained in the following table.

_Table 4: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerAppointmentCreated event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of created appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the newly added appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">requestType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the request type detail - 'appointmentSaved".</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'appointmentCreated".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>



{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerAppointmentCreated="Schedule1_ServerAppointmentCreated" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerAppointmentCreated(object Sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the created appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic EventDetails = Arguments as Dictionary<string, object>;
            string RequestType = e.Arguments["requestType"] as string;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerAppointmentCreated(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the created appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim RequestType = e.Arguments("requestType")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerAppointmentChanged

The **OnServerAppointmentChanged** event is triggered after an existing appointment is edited. The details of the edited appointment can be obtained server-side, as explained in the following table.

_Table 5: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerAppointmentChanged event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of edited appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the edited appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">requestType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the request type detail - 'appointmentChanged".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentAction</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the current action detail - 'edit".</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'appointmentChanged".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>


{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerAppointmentChanged="Schedule1_ServerAppointmentChanged" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerAppointmentChanged(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the changed appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic EventDetail = Arguments as Dictionary<string, object>;
            string RequestType = e.Arguments["requestType"] as string;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerAppointmentChanged(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the changed appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim RequestType = e.Arguments("requestType")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerAppointmentRemoved

The **OnServerAppointmentRemoved** event is triggered after the appointment is deleted. The details of the deleted appointment can be obtained server-side, as explained in the following table.

_Table 6: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerAppointmentRemoved event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of edited appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the deleted appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">requestType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the request type detail - 'appointmentRemoved".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentAction</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the current action detail - 'delete".</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'appointmentRemoved".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerAppointmentRemoved="Schedule1_ServerAppointmentRemoved" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerAppointmentRemoved(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the deleted appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic EventDetail = Arguments as Dictionary<string, object>;
            string RequestType = e.Arguments["requestType"] as string;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerAppointmentRemoved(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the deleted appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim RequestType = e.Arguments("requestType")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerCellClick

The **OnServerCellClick** event is triggered when a cell is single clicked. The details of the clicked cell can be obtained server-side, as explained in the following table.

_Table 7: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerCellClick event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of clicked cell and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked cell details.
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">cellIndex</td>
                                        <td class="type">integer</td>
                                        <td class="description">Returns the selected cell index value - ex: 2.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">startTime</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the selected cell StartTime value - ex: 2018-09-25T05:30:00.000Z.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">endTime</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the selected cell EndTime value - ex: 2018-09-25T06:00:00.000Z.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">resources</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the selected cell resource details -ex:
                                            <table>
                                                <thead>
                                                    <tr>
                                                        <th>Name</th>
                                                        <th>Type</th>
                                                        <th>Description</th>
                                                    </tr>
                                                </thead>
                                                <tbody>
                                                    <tr>
                                                        <th>text</th>
                                                        <th>string</th>
                                                        <th>Returns the resource name of the clicked cell - ex: Nancy</th>
                                                    </tr>
                                                    <tr>
                                                        <th>id</th>
                                                        <th>int</th>
                                                        <th>Returns the resource id of the clicked cell - ex: 1</th>
                                                    </tr>
                                                    <tr>
                                                        <th>groupId</th>
                                                        <th>int</th>
                                                        <th>Returns the resource groupId of the clicked cell - ex: 1</th>
                                                    </tr>
                                                    <tr>
                                                        <th>color</th>
                                                        <th>string</th>
                                                        <th>Returns the resource color of the clicked cell - ex: #ffaa00</th>
                                                    </tr>
                                                    <tr>
                                                        <th>classname</th>
                                                        <th>string</th>
                                                        <th>Returns the resource classname of the clicked cell - ex: e-childnode</th>
                                                    </tr>
                                                </tbody>
                                            </table>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="name">quickString</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the selected cell quick window display string detail - ex: "Tuesday, September 25, 11:00 AM - 11:30 AM".</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'cellClick".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerCellClick="Schedule1_ServerCellClick" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerCellClick(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the clicked cell details
            var CellIndex  = e.Arguments["cellIndex"];
            var StartTime = e.Arguments["startTime"];
            var EndTime = e.Arguments["endTime"];
            var Resources = e.Arguments["resources"];
            var QuickString = e.Arguments["quickString"];
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerCellClick(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the clicked cell details
            Dim CellIndex = e.Arguments("cellIndex")
            Dim StartTime = e.Arguments("startTime")
            Dim EndTime = e.Arguments("endTime")
            Dim Resources = e.Arguments("resources")
            Dim QuickString = e.Arguments("quickString")
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerAppointmentClick

The **OnServerAppointmentClick** event is triggered when an appointment is single clicked. The details of the clicked appointment can be obtained server-side, as explained in the following table.

_Table 8: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerAppointmentClick event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of clicked appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked appointment details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'appointmentClick".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerAppointmentClick="Schedule1_ServerAppointmentClick" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerAppointmentClick(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the clicked appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerAppointmentClick(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the clicked appointment details
            Dim Arguments = e.Arguments("appointment")
            Dim EventType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerMenuItemClick

The **OnServerMenuItemClick** event is triggered when the context menu item or its sub-menu item is clicked. The details of the clicked cell/appointment and selected menu item details can be obtained server-side, as explained in the following table.

_Table 10: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerMenuItemClick event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of clicked menu item details and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked menu item and its target details.
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">events</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked menu item details like text, ID.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">targetInfo</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked menu item details like appointment start and end time details, when clicking on the new appointment option.
                                            <table>
                                                <thead>
                                                    <tr>Target</tr>
                                                    <tr>Description</tr>
                                                </thead>
                                                <thead>
                                                    <tr>Cell</tr>
                                                    <tr>Returns the details of the cell, where the context menu is opened. For example, start and end time and resource (contains the id value of the resources) details.
                                                        startTime - 2018-09-27T08:00:00.000Z
                                                        endTime - 2018-09-27T08:30:00.000Z
                                                    </tr>
                                                </thead>
                                                <thead>
                                                    <tr>Appointment</tr>
                                                    <tr>Returns the details of the appointment, where the context menu is opened. For example, appointment Id, StartTime, EndTime, Subject and so on.
                                                        Id: 1,
                                                        StartTime: 2018-09-27T07:30:00.000Z,
                                                        EndTime: 2018-09-27T09:30:00.000Z,
                                                        Subject: "New Test Event".
                                                    </tr>
                                                </thead>
                                            </table>
                                        </td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'menuItemClick".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerMenuItemClick="Schedule1_ServerMenuItemClick" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

       protected void Schedule1_ServerMenuItemClick(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the clicked menu item details
            var Arguments1 = e.Arguments["events"] as Dictionary<string, object>;
            dynamic eventlist = Arguments1 as Dictionary<string, object>;
            if (eventlist["ID"] == "new" || eventlist["ID"] == "recurrence" || eventlist["ID"] == "today" || eventlist["ID"] == "gotodate")
            {
                Arguments = e.Arguments["targetInfo"] as Dictionary<string, object>;
                dynamic list = Arguments as Dictionary<string, object>;
                var startTime = list["startTime"];
                var endTime = list["endTime"];
            }
            if (eventlist["ID"] == "open" || eventlist["ID"] == "delete")
            {
                Arguments = e.Arguments["targetInfo"] as Dictionary<string, object>;
                // Here list will hold the clicked appointment details
                dynamic list = Arguments as Dictionary<string, object>;                
            }
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerMenuItemClick(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the clicked menu item details
            Dim eventlist = e.Arguments("events")
            If eventlist("ID") = "new" OrElse eventlist("ID") = "recurrence" OrElse eventlist("ID") = "today" OrElse eventlist("ID") = "gotodate" Then
                Dim list = e.Arguments("targetInfo")
                Dim startTime = list("startTime")
                Dim endTime = list("endTime")
            End If
            If eventlist("ID") = "open" OrElse eventlist("ID") = "delete" Then
                ' Here list will hold the clicked appointment details
                Dim list = e.Arguments("targetInfo")
            End If
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerNavigation

The **OnServerNavigation** event is triggered after the schedule view or date is navigated. The details of the navigation can be obtained server-side, as explained in the following table.

_Table 11: Syncfusion.JavaScript.Web.ScheduleEventArgs arguments of OnServerNavigation event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the detail of the Schedule navigation and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the Schedule view navigation details.
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">previousView</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the previous view name".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentView</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the current view name".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentDate</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the current date value.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">requestType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the request type details - viewNavigate.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                Returns the Schedule date navigation details.          
                                <tbody>
                                    <tr>
                                        <td class="name">previousDate</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the previous date value".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentDate</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the current date value".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentView</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the current view value.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">requestType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the request type details - dateNavigate.</td>
                                    </tr>
                                </tbody>
                            </table>
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                Returns the Schedule navigation details through previous and next appointment navigator button.          
                                <tbody>
                                    <tr>
                                        <td class="name">currentDate</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the current date value".</td>
                                    </tr>
                                    <tr>
                                        <td class="name">currentView</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the current view value.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">It indicates the action (navigation) performed in the Schedule.</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerNavigation="Schedule1_ServerNavigation" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerNavigation(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the details about the navigation
            if (e.Arguments["requestType"] != null && e.Arguments["requestType"].ToString() == "viewNavigate")
            {
                var PreviousView = e.Arguments["previousView"];
                var CurrentView = e.Arguments["currentView"];
                var CurrentDate = e.Arguments["currentDate"];
            }
            if (e.Arguments["requestType"] != null && e.Arguments["requestType"].ToString() == "dateNavigate")
            {
                var PreviousDate = e.Arguments["previousDate"];
                var CurrentDate = e.Arguments["currentDate"];
                var CurrentView = e.Arguments["currentView"];
            }
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerNavigation(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the details about the navigation
            If e.Arguments("requestType") IsNot Nothing AndAlso e.Arguments("requestType").ToString() = "viewNavigate" Then
                Dim PreviousView = e.Arguments("previousView")
                Dim CurrentView = e.Arguments("currentView")
                Dim CurrentDate = e.Arguments("currentDate")
            End If
            If e.Arguments("requestType") IsNot Nothing AndAlso e.Arguments("requestType").ToString() = "dateNavigate" Then
                Dim PreviousDate = e.Arguments("previousDate")
                Dim CurrentDate = e.Arguments("currentDate")
                Dim CurrentView = e.Arguments("currentView")
            End If
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}   

    
## OnServerAppointmentWindowOpen

The **OnServerAppointmentWindowOpen** event is triggered before the appointment window opens. The details of the clicked cells can be obtained server-side, as explained in the following table.

_Table 13: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerAppointmentWindowOpen event_

<table class="params">
        <thead>
            <tr>
                <th>Name</th>
                <th>Type</th>
                <th>Description</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td class="name">EventArgs</td>
                <td class="type">ScheduleEventArgs</td>
                <td class="description">Returns the details of clicked cell or appointment details and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td>
                                            <table class="params">
                                            </table>
                                            <table class="params">
                                                <thead>
                                                    <tr>
                                                        <th>Name</th>
                                                        <th>Type</th>
                                                        <th>Description</th>
                                                    </tr>
                                                </thead>
                                                Returns the clicked cell details.          
                                            <tbody>
                                                <tr>
                                                    <td class="name">startTime</td>
                                                    <td class="type">string</td>
                                                    <td class="description">Returns the clicked cell start time value.</td>
                                                </tr>
                                                <tr>
                                                    <td class="name">endTime</td>
                                                    <td class="type">string</td>
                                                    <td class="description">Returns the clicked cell end time value.</td>
                                                </tr>
                                                <tr>
                                                    <td class="name">resource</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the clicked cell resource details.</td>
                                                </tr>
                                            </tbody>
                                            </table>
                                            <table class="params">
                                                <thead>
                                                    <tr>
                                                        <th>Name</th>
                                                        <th>Type</th>
                                                        <th>Description</th>
                                                    </tr>
                                                </thead>
                                            <tbody>
                                                <tr>
                                                    <td class="name">appointment</td>
                                                    <td class="type">object</td>
                                                    <td class="description">Returns the clicked appointment details.</td>
                                                </tr>
                                                <tr>
                                                    <td class="name">edit</td>
                                                    <td class="type">string</td>
                                                    <td class="description">Returns the edit action status (i.e. when opening the appointment window by clicking on the appointment mark the status as true) - ex: true.</td>
                                                </tr>
                                            </tbody>
                                            </table>
                                        </td>
                                    </tr>
                                    <tr>
                                        <td class="name">EventType</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the Event type detail - 'appointmentWindowOpen".</td>
                                    </tr>
                                </tbody>
                            </table>
                </td>
            </tr>
        </tbody>
    </table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerAppointmentWindowOpen="Schedule1_ServerAppointmentWindowOpen" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerAppointmentWindowOpen(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the current clicked cell details
            var resource = e.Arguments["resources"];
            var startTime = e.Arguments["startTime"];
            var endTime = e.Arguments["endTime"];

            // The following code will be used to get the current clicked appointment details
            var appointment = e.Arguments["appointment"];
            var isCurrentActionEdit = e.Arguments["edit"];
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerAppointmentWindowOpen(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the current clicked cell details
            Dim resource = e.Arguments("resources")
            Dim startTime = e.Arguments("startTime")
            Dim endTime = e.Arguments("endTime")

            ' The following code will be used to get the current clicked appointment details
            Dim appointment = e.Arguments("appointment")
            Dim isCurrentActionEdit = e.Arguments("edit")
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerResizeStart

The **OnServerResizeStart** event is triggered when the appointment resizing begins. The details of the resizing appointment can be obtained server-side, as explained in the following table.

_Table 14: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerResizeStart event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of resizing appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the resizing appointment details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'resizeStart".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerResizeStart="Schedule1_ServerResizeStart" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerResizeStart(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the resizing appointment details
            var appointment = e.Arguments["appointment"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerResizeStart(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the resizing appointment details
            Dim appointment = e.Arguments("appointment")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
    
## OnServerResizeStop

The **OnServerResizeStop** event is triggered when an appointment resizing stops. The details of the resized appointment can be obtained server-side, as explained in the following table.

_Table 16: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerResizeStop event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of resized appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the resized appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">target</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the target details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'resizeStop".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerResizeStop="Schedule1_ServerResizeStop" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerResizeStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the resized appointment details
            Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerResizeStop(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the resized appointment details
            Dim appointment = e.Arguments("appointment")
            Dim target = e.Arguments("target")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}
    
## OnServerDragStart

The **OnServerDragStart** event is triggered when the appointment dragging begins. The details of the dragging appointment can be obtained server-side, as explained in the following table.

_Table 17: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerDragStart event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of dragging appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the dragging appointment details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'dragStart".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerDragStart="Schedule1_ServerDragStart" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

       protected void Schedule1_ServerDragStart(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the resizing appointment details
            var appointment = e.Arguments["appointment"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerDragStart(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the resizing appointment details
            Dim appointment = e.Arguments("appointment")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}

## OnServerDragStop

The **OnServerDragStop** event is triggered when the appointment is dropped. The details of the dropped appointment can be obtained server-side, as explained in the following table.

_Table 19: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerDragStop event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of drag and dropped appointment and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appointment</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the drag and dropped appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">event</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the event details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'dragStop".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerDragStop="Schedule1_ServerDragStop" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerDragStop(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the resized appointment details
            var Arguments = e.Arguments["appointment"] as Dictionary<string, object>;
            dynamic list = Arguments as Dictionary<string, object>;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerDragStop(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the resized appointment details
            Dim appointment = e.Arguments("appointment")
            Dim target = e.Arguments("event")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}

## OnServerOverflowButtonClick

The **OnServerOverflowButtonClick** event is triggered when the overflow button is clicked. The details of the appointments that lies under the clicked date can be obtained server-side, as explained in the following table.

_Table 20: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerOverflowButtonClick event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of clicked day Datas (ex: date) and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Datas</td>
                                        <td class="type">object</td>
                                        <td class="description">Returns the clicked day date details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'overflowButtonClick".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerOverflowButtonClick="Schedule1_ServerOverflowButtonClick" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerOverflowButtonClick(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the current day date details
            var appointment = e.Arguments["Datas"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerOverflowButtonClick(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the current day date details
            Dim appointment = e.Arguments("Datas")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}

## OnServerExportICS

The **OnServerExportICS** event is triggered when the schedule appointments are exported into ICS file format. The details of the schedule model, blocked and all other appointments can be obtained server-side, as explained in the following table.

_Table 21: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerExportICS event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of ICS file export related required details like appointment settings and processed, block appointment details and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appSetting</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the appointment settings details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">appId</td>
                                        <td class="type">number</td>
                                        <td class="description">Returns the exported appointment ID value.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">processedApp</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the processed appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">blockedApp</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the block out appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">model</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the schedule model details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">locale</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the localized text details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'exportICS".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerExportICS="Schedule1_ExportICS" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ExportICS(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the details of the ics file export related appointment details and its settings and so on
            var appointmentSetting = e.Arguments["appSetting"];
            var appointmentId = e.Arguments["appId"];
            var processedAppointments = e.Arguments["processedApp"];
            var blockAppointments = e.Arguments["blockedApp"];
            var scheduleModel = e.Arguments["model"];
            var localeText = e.Arguments["locale"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ExportICS(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            'The following code will be used to get the details of the ics file export related appointment details And its settings And so on
            Dim appointmentSetting = e.Arguments("appSetting")
            Dim appointmentId = e.Arguments("appId")
            Dim processedAppointments = e.Arguments("processedApp")
            Dim blockAppointments = e.Arguments("blockedApp")
            Dim scheduleModel = e.Arguments("model")
            Dim localeText = e.Arguments("locale")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}

## OnServerExportPDF

The **OnServerExportPDF** event is triggered when the scheduler along with appointments is exported in PDF file format. The details of the schedule model, blocked and all other appointments can be obtained server-side, as explained in the following table.

_Table 22: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnServerExportPDF event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the details of PDF file export related required details like appointment settings and processed, block appointment details and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">appSetting</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the appointment settings details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">appId</td>
                                        <td class="type">number</td>
                                        <td class="description">Returns the exported appointment ID value.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">processedApp</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the processed appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">blockedApp</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the block out appointment details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">model</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the schedule model details.</td>
                                    </tr>
                                    <tr>
                                        <td class="name">locale</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the localized text details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'exportPDF".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnServerExportPDF="Schedule1_ServerExportPDF" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ServerExportPDF(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the details of the pdf file export related appointment details and its settings and so on
            var appointmentSetting = e.Arguments["appSetting"];
            var appointmentId = e.Arguments["appId"];
            var processedAppointments = e.Arguments["processedApp"];
            var blockAppointments = e.Arguments["blockedApp"];
            var scheduleModel = e.Arguments["model"];
            var localeText = e.Arguments["locale"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ServerExportPDF(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            'The following code will be used to get the details of the PDF file export related appointment details And its settings And so on
            Dim appointmentSetting = e.Arguments("appSetting")
            Dim appointmentId = e.Arguments("appId")
            Dim processedAppointments = e.Arguments("processedApp")
            Dim blockAppointments = e.Arguments("blockedApp")
            Dim scheduleModel = e.Arguments("model")
            Dim localeText = e.Arguments("locale")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}

## OnExportToExcel

The **OnExportToExcel** event is triggered when the scheduler appointments is exported in Excel file format. The details of the schedule appointments can be obtained server-side, as explained in the following table.

_Table 23: Syncfusion.JavaScript.Web.ScheduleEventArgs argument of OnExportToExcel event_

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">EventArgs</td>
            <td class="type">ScheduleEventArgs</td>
            <td class="description">Returns the appointment details to export it to Excel file and its type.
                            <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">Arguments</td>
                                        <td class="type">object</td>
                                        <td class="description">
                                        <table class="params">
                                <thead>
                                    <tr>
                                        <th>Name</th>
                                        <th>Type</th>
                                        <th>Description</th>
                                    </tr>
                                </thead>
                                <tbody>
                                    <tr>
                                        <td class="name">ScheduleAppointment</td>
                                        <td class="type">string</td>
                                        <td class="description">Returns the exporting appointment details.</td>
                                    </tr>
                                </tbody>
                            </table>
                        </td>
                    </tr>
                    <tr>
                        <td class="name">EventType</td>
                        <td class="type">string</td>
                        <td class="description">Returns the Event type detail - 'exportToExcel".</td>
                    </tr>
                   </tbody>
                </table>
            </td>
        </tr>
    </tbody>
</table>

{% tabs %}

{% highlight html %}

<ej:Schedule ID="Schedule1" ClientIDMode="Static" Height="525px" Width="100%" OnExportToExcel="Schedule1_ExportToExcel" runat="server">
</ej:Schedule> 

{% endhighlight %}

{% highlight c# %}

    public partial class _Default : System.Web.UI.Page
    {

        protected void Page_Load(object sender, EventArgs e)
        {
        }

        protected void Schedule1_ExportToExcel(object sender, Syncfusion.JavaScript.Web.ScheduleEventArgs e)
        {
            // The following code will be used to get the details of the excel file export related appointment details
            var scheduleAppointment = e.Arguments["ScheduleAppointment"];
            var evenType = e.EventType;
        }

    }
    
{% endhighlight %}

{% highlight VB %}

    Public Class _Default
    Inherits Page
        
        Protected Sub Page_Load(ByVal sender As Object, ByVal e As EventArgs) Handles Me.Load
            
        End Sub    
        Protected Sub Schedule1_ExportToExcel(sender As Object, e As Syncfusion.JavaScript.Web.ScheduleEventArgs)
            ' The following code will be used to get the details of the excel file export related appointment details
            Dim scheduleAppointment = e.Arguments("ScheduleAppointment")
            Dim evenType = e.EventType
        End Sub
    End Class
    
{% endhighlight %}
    
{% endtabs %}