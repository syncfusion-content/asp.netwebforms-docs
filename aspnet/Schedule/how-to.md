---
title: How-to
description: Custom Configuration with Schedule control
platform: aspnet
control: Schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# How To

## Validate the Custom Appointment Window Fields

The client-side validation of the fields present within the custom appointment window can be handled before submitting it, by adding appropriate validation classes to each field.

Refer the steps [here](/asp/schedule/customization#appointment-window-customization) and create a sample for Custom Appointment window, before proceeding with the following validations.

In the custom appointment window sample, create an additional css class **validation** as mentioned below to add it to the appropriate fields, if the validation of such fields fails.

{% highlight html %}

<asp:Content runat="server" ID="Style" ContentPlaceHolderID="StyleSection">
    <style type="text/css">
        .error {
            background-color: #FF8A8A;
        }
        </style>
</asp:Content>

{% endhighlight %}

The sample contains the fields like Subject, Description, StartTime and EndTime which needs to be validated at client-side. To do so, add the required validation code within the script section as follows.

{% highlight html %}

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
            // To Validate the Subject field.
            $("#subject").focusout(function () {
                if ($.trim($("#subject").val()) == "") {
                    $("#subject").addClass("validation");
                    return false;
                }
            })

            // To Validate the Description field.
            $("#customdescription").focusout(function () {
                if ($.trim($("#customdescription").val()) == "") {
                    $("#customdescription").addClass("validation");
                    return false;
                }
            })

            // To Validate the Time duration of the appointments
            $("#EndTime").focusout(function () {
                if (new Date($("#EndTime").val()).getDate() >= new Date($("#StartTime").val()).getDate()) {
                    if (new Date($("#StartTime").val()).getTime() >= new Date($("#EndTime").val()).getTime())
                        alert("EndTime value is lesser than the StartTime value");
                }
            })
    </script>
</asp:Content>
    
{% endhighlight %}

Now, after adding the above validations – whenever the fields within the custom appointment window are skipped without filling any information, it will be notified to the users appropriately.

## Highlight Different Work Hours for Each Resources

By default, the work hours of the Scheduler is highlighted based on the start and end values provided within the `WorkHours` object. It remains same for all the resources, when the Scheduler is rendered with multiple resources. To customize this behaviour so as to highlight different workhour range for each of the resources, the following workaround can be utilised by making use of the Scheduler events **Create** and `ActionComplete`.

Initially, set the **Highlight** as false for the **WorkHours**, so as to disable the highlighting of default work hour range.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/5/2014" Create="onCreate" ActionComplete="onCreate">
    <Group Resources="Owners"/>
    <Resources>
        <ej:Resources Field="OwnerId" Name="Owners" Title="Owner" AllowMultiple="true">
            <ResourceSettings Color="color" Id="id" Text="text">
                
            </ResourceSettings>
        </ej:Resources>
    </Resources>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" ResourceFields="OwnerId"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [MultipleResource]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        // This function executes during the initial control creation and also on completion of each action like date/view navigation.
        function onCreate(args) {
            if (args.requestType == "viewNavigate" || args.requestType == "dateNavigate" || args.type == "create") {

                // declare different start and end work hour values for each resources
                var resourceOneStart = 9,
                    resourceOneEnd = 18;

                var resourceTwoStart = 13,
                    resourceTwoEnd = 18;

                var resourceThreeStart = 10,
                    resourceThreeEnd = 18;

                this.option("workHours.highlight", (this.currentView() != "month") ? false : true);

                // Get the Scheduler workcell rows
                var trElements = this.$WorkCellDiv.find("tr");

                for (var i = 0; i < trElements.length; i++) {

                    // Get the Scheduler workcell columns
                    var tdElements = $(trElements[i]).find("td");

                    for (var j = 0; j < tdElements.length; j++) {
                        switch (this.currentView()) {
                            case "day":
                                switch (j) {
                                    case 0: // column index 0 represents first resource in day view
                                        $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 1: // column index 1 represents second resource in day view
                                        $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 2: // column index 2 represents third resource in day view
                                        $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                }
                                break;
                            case "week":
                                switch (j) {
                                    case 0:
                                    case 1:
                                    case 2:
                                    case 3:
                                    case 4:
                                    case 5:
                                    case 6: // column indexes 0 to 6 belongs to first resource in week view (7 days)
                                        $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 7:
                                    case 8:
                                    case 9:
                                    case 10:
                                    case 11:
                                    case 12:
                                    case 13: // column indexes 7 to 13 belongs to second resource in week view (7 days)
                                        $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 14:
                                    case 15:
                                    case 16:
                                    case 17:
                                    case 18:
                                    case 19:
                                    case 20: // column indexes 14 to 20 belongs to third resource in week view (7 days)
                                        $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                }
                                break;
                            case "workweek":
                                switch (j) {
                                    case 0:
                                    case 1:
                                    case 2:
                                    case 3:
                                    case 4: // column indexes 0 to 4 belongs to first resource in workweek view (5 days)
                                        $(tdElements[j]).addClass(((i > (resourceOneStart * 2) - 1) && (i <= (resourceOneEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 5:
                                    case 6:
                                    case 7:
                                    case 8:
                                    case 9:
                                        // column indexes 5 to 9 belongs to second resource in workweek view (5 days)
                                        $(tdElements[j]).addClass(((i > (resourceTwoStart * 2) - 1) && (i <= (resourceTwoEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                    case 10:
                                    case 11:
                                    case 12:
                                    case 13:
                                    case 14:
                                        // column indexes 10 to 14 belongs to third resource in workweek view (5 days)
                                        $(tdElements[j]).addClass(((i > (resourceThreeStart * 2) - 1) && (i <= (resourceThreeEnd * 2) - 1)) ? "e-businesshighlightworkcells" : "");
                                        break;
                                }
                                break;
                        }
                    }
                }
            }
        }
    </script>
</asp:Content>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class multipleresource : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<Rooms> owners = new List<Rooms>();
            owners.Add(new Rooms { text = "Nancy", id = "1", color = "#f8a398" });
            owners.Add(new Rooms { text = "Steven", id = "3", color = "#56ca85" });
            owners.Add(new Rooms { text = "Michael", id = "5", color = "#51a0ed" });
            Schedule1.Resources[0].ResourceSettings.DataSource = owners;
        }
        public class Rooms
        {
            public string text { set; get; }
            public string id { set; get; }
            public string groupId { set; get; }
            public string color { set; get; }
        }
    }
}

{% endhighlight %}

## Display Scheduler with Appointments Filtered by Subject

It is possible to display the Scheduler with the appointments, which is filtered based on the Subject. For example, if we keep a text box and start typing a character – the appointment’s subject that matches the typed character alone will be shown on the Scheduler. The following code example depicts the way to achieve this.

{% highlight html %}

<!--textbox for entering search character-->
<input id='txtSearch' type='text' onkeyup='searchKeyUp()' />

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        // This function executes when a character is entered in the textbox
        function searchKeyUp() {
            var searchString = $("#txtSearch").val();
            var schObj = $("#Schedule1").data("ejSchedule");
            var result = schObj.searchAppointments(searchString);
            var appointments = schObj._processed;
            schObj.option("appointmentSettings", { dataSource: [] });
            if (!ej.isNullOrUndefined(result) && result.length != 0 && searchString != "")
                schObj.option("appointmentSettings", { dataSource: result });
            else
                schObj.option("appointmentSettings", { dataSource: appointments });
        }
    </script>
</asp:Content>

{% endhighlight %}

## Customize the Default Appointment Window

Apart from the custom appointment window, it is possible to customize the default appointment window by adding/removing the required number of fields into it. This can be achieved through the **create** event of the scheduler.

The following code example depicts the way to achieve the customization of default appointment window.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" ShowLocationField="true" Create="onCreate" AppointmentWindowOpen="onAppointmentOpen">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" Location="Location" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
      
        // This function executes when the checkboxes are checked/unchecked
        function onCreate(args) {
            var customDesign = "<tr class='customfields'><td class='e-textlabel'>Event Type</td><td><input class='apptype' type='text'/></td><td class='e-textlabel'>Event Status </td><td><input class='status' type='text'/></td></tr>";
            $("." + this._id + "parrow").after(customDesign);
        }

        // This function executes before the appointment window gets opened.
        function onAppointmentOpen(args) {
            if (!ej.isNullOrUndefined(args.appointment)) {
                // if double clicked on the appointments, retrieve the custom field values from the appointment object and fills it in the appropriate fields.               this._appointmentAddWindow.find(".apptype").val(args.appointment.AppointmentType);
                this._appointmentAddWindow.find(".status").val(args.appointment.Status);
            } else {
                // if double clicked on the cells, clears the field values.               
                this._appointmentAddWindow.find(".apptype").val("");
                this._appointmentAddWindow.find(".status").val("");
            }
        }

    </script>
</asp:Content>

{% endhighlight %}

## Signalr 

To implement SignalR concept in Scheduler, add and refer the appropriate SignalR scripts in your project and then create a hub for initiating the action. The SignalR implemantation can be achived with the following code example.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014" BeforeAppointmentRemove="actionComplete" BeforeAppointmentChange="actionComplete" BeforeAppointmentCreate="actionComplete" Navigation="actionComplete">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule" />
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
     <script src="../Scripts/jquery.signalR-1.1.4.min.js" type="text/javascript"></script>
    <script src='<%: ResolveClientUrl("~/signalr/hubs") %>' type="text/javascript"></script>
    <script type="text/javascript">
        $(function () {
            window.signal = $.connection.scheduleHub;
            window.signal.client.modify = function (action, data) {
                if (data != null) {
                    var id = data.Id != null ? data.Id : data[0].Id;
                    var subject = data.Subject;
                    var startTime = new Date(data.StartTime);
                    var endTime = new Date(data.EndTime);
                    var description = data.Description;
                    var allDay = data.AllDay;
                    var recurrence = data.Recurrence;
                    var recurrenceRule = data.RecurrenceRule;
                    var object = { Id: id, Subject: subject, StartTime: startTime, EndTime: endTime, Description: description, AllDay: allDay, Recurrence: recurrence, RecurrenceRule: recurrenceRule };
                    var schedule = $("#Schedule1").data("ejSchedule");
                    if (action == "appointmentSaved") {
                        new ej.DataManager(schedule._currentAppointmentData).insert(object);
                        schedule._appointmentProcessing(object);
                        schedule._renderAppointmentAll();
                    }
                    else if (action == "appointmentEdited") {
                        new ej.DataManager(schedule._currentAppointmentData).update("Id", object);
                        new ej.DataManager(schedule._processed).remove("Id", object.Id);
                        schedule._appointmentProcessing(object);
                        schedule._renderAppointmentAll();
                    }
                    else if (action == "appointmentDeleted") {
                        var appointment = new ej.DataManager(schedule._processed).executeLocal(new ej.Query().where("Id", ej.FilterOperators.equal, id));
                        new ej.DataManager(schedule._currentAppointmentData).remove("Id", appointment[0].Id);
                        new ej.DataManager(schedule._processed).remove("Id", appointment[0].Id);
                        schedule._renderAppointmentAll();
                    }
                }
            };
            $.connection.hub.start().done(function () {
                window.actionComplete = function (args) {
		   if(args.methodType == "public")
                    args.appointment=null;
                    var appointmentDetails = args.appointment;
                    if (args.type == "appointmentSaved" || args.type == "appointmentEdited" || args.type == "appointmentDeleted") {
                        window.signal.server.modify(args.type, appointmentDetails);
                    }
                };
            });
        });
    </script>
</asp:Content>

{% endhighlight %}
