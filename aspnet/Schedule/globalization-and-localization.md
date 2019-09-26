---
title: Globalization & Localization in ASP.NET Scheduler |Syncfusion
description: This section explains how to provide support for localization in the Syncfusion ASP.NET Web Forms Schedule component.
platform: aspnet
control: schedule
documentation: ug
keywords: globalize, localize, localization, globalization 
---
# Globalization and Localization

## Globalization

The Scheduler control is built with default **globalization** support as it format the dates according to the user’s locale automatically and processes it internally without any need for manual conversions. This kind of default handling of Scheduler dates is achieved through the reference of **ej.globalize** library which globalize the date, day and month names accordingly. 

## Localization

Scheduler also comes with default localization support which allows it to customize the display of text within the Scheduler in a user-specific culture and locale. The Schedule control can be localized in specific culture using the common API `Locale` along with the collection of localized words defined for that culture using the ej.Schedule.Locale [**culture-code**].

N> By default, the Schedule control is localized in **en-US** culture.

To localize Scheduler into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.                                      

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the Schedule control in **fr-FR** culture.

{% highlight html %}

<!--Container for ejScheduler widget-->
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Locale="fr-FR" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
            ej.Schedule.Locale["fr-FR"] = {
                ReminderWindowTitle: "Fenêtre de rappel",
                CreateAppointmentTitle: "créer un rendez-",
                RecurrenceEditTitle: "Modifier répétition nomination",
                RecurrenceEditMessage: "Comment voulez-vous changer le cas dans la série?",
                RecurrenceEditOnly: "Seulement cette nomination",
                RecurrenceEditSeries: "La série entière",
                PreviousAppointment: "Nomination précédente",
                NextAppointment: "prochain rendez-vous",
                AppointmentSubject: "sujet",
                StartTime: "Heure de début",
                EndTime: "Heure de fin",
                AllDay: "toute la journée",
                Today: "aujourd'hui",
                Recurrence: "répétition",
                Done: "Terminé",
                Cancel: "annuler",
                Ok: "Ok",
                RepeatBy: "Répétez par",
                RepeatEvery: "répéter chaque",
                RepeatOn: "répéter l'opération sur",
                StartsOn: "démarre sur",
                Ends: "extrémités",
                Summary: "résumé",
                Daily: "quotidien",
                Weekly: "hebdomadaire",
                Monthly: "mensuel",
                Yearly: "annuel",
                Every: "tous",
                EveryWeekDay: "chaque jour de la semaine",
                Never: "jamais",
                After: "après",
                Occurrence: "apparition",
                On: "sur",
                Edit: "Modifier",
                RecurrenceDay: "Jour (s)",
                RecurrenceWeek: "Semaine (s)",
                RecurrenceMonth: "Mois (s)",
                RecurrenceYear: "Année (s)",
                The: "la",
                OfEvery: "de chaque",
                First: "première",
                Second: "deuxième",
                Third: "troisième",
                Fourth: "quatrième",
                Last: "dernier",
                WeekDay: "jour de la semaine",
                WeekEndDay: "Jour de week-end",
                Subject: "sujet",
                Categorize: "Catégories",
                DueIn: "En raison",
                DismissAll: "rejeter tout",
                Dismiss: "rejeter",
                OpenItem: "Ouvrir l'élément",
                Snooze: "répétition",
                Day: "jour",
                Week: "semaine",
                WorkWeek: "Semaine de travail",
                Month: "mois",
                AddEvent: "Ajouter événement",
                CustomView: "Vue personnalisée",
                Agenda: "ordre du jour",
                Detailed: "détaillé",
                EventBeginsin: "Nomination commence dans",
                Editevent: "Modifier nomination",
                Editseries: "Modifier série",
                Times: "fois",
                Until: "jusqu'à",
                Eventwas: "rendez-vous était",
                Hours: "hrs",
                Minutes: "minutes",
                Overdue: "en retard",
                Days: "jour (s)",
                Event: "sujet",
                Select: "sélectionner",
                Previous: "prev",
                Next: "suivant",
                Close: "proche",
                Delete: "effacer",
                Date: "date",
                Showin: "montrer en",
                Gotodate: "Aller à la date",
                Resources: "RESSOURCES",
                RecurrenceDeleteTitle: "Supprimer répétition rendez-",
                Location: "emplacement",
                Priority: "priorité",
                RecurrenceAlert: "alerte",
                WrongPattern: "Le modèle de récurrence est pas valable",
                CreateError: "La durée de la nomination doit être plus courte que la façon dont elle se produit fréquemment. Raccourcir la durée ou changer le modèle de récurrence dans la boîte de dialogue Récurrence de rendez.",
                DragResizeError: "Impossible de replanifier une occurrence du rendez-vous récurrent. si elle saute sur une occurrence ultérieure du même rendez-vous.",
                StartEndError: "L'heure de fin doit être supérieur à l'heure de début",
                MouseOverDeleteTitle: "supprimer un rendez-",
                DeleteConfirmation: "Êtes-vous sûr de vouloir supprimer ce rendez-vous?",
                Time: "Temps"
            }         
        </script>
</asp:Content>

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **Locale** property for the Schedule control with the appropriate **culture-code** [**fr-FR**].


### Localizing Specific Words

To customize or localize only some specific words in the default `Locale["en-US"]` collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

{% highlight html %}
<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Locale="en-US" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

 <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>
 
<asp:Content ID="ScriptContent" runat="server" ContentPlaceHolderID="ScriptSection">
    <script type="text/javascript">
        var customizationMessage = {
            // customize the appointment window title
            CreateAppointmentTitle: "Create Event",
            // customize the view options text in the Schedule header
            Day: "1 Day",
            Week: "7 Days",
            WorkWeek: "5 Days",
            Month: "Month"
        };

        // Extend only the required changes to the original locale collection
        $.extend(ej.Schedule.Locale["en-US"], customizationMessage);

        </script>
</asp:Content>

{% endhighlight %}

## Time Zone

The Scheduler makes use of the System time zone by default. If it needs to follow some other user-specific time zone, then the API `TimeZone` can be used. Also, the Scheduler can be set to observe the Daylight Saving Time (DST) with its **isDST** property which is set to **false** by default.  

When `IsDST` property is set to **true**, the Scheduler internally processes the time difference values (for the Start and end time of the appointments) related to the Scheduler time zone that observes daylight savings time. 

The following code example shows the way to set the specific time zone value with the daylight savings time observed in the Scheduler.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" TimeZone="UTC +05:30" IsDST="true" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

### TimeZone for Scheduler Appointments

Apart from the default action of applying specific timezone to the entire Scheduler, it is also possible to set different time zone values for each appointments through the properties **StartTimeZone** and **EndTimeZone** which can be defined as separate fields within the appointment dataSource. When these properties are not explicitly defined for appointments, the appointments Start and End time will be processed based on the Scheduler time zone.

N> The **isDST** property closely relies on the appointment fields like `StartTimeZone` and `EndTimeZone` for appropriate time difference calculations. If these two fields are not defined for appointments, then **IsDST** depends on the System **TimeZone** value.

The following code snippet shows how to define isDST and the time zones for specific appointments.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" IsDST="true" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" StartTimeZone="StartTimeZone" EndTimeZone="EndTimeZone" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

### Customizing the TimeZone Collection

It is also possible to define or customize the default time zone collection of the Scheduler, by using the `TimeZoneCollection` API as follows.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" CurrentDate="5/2/2014">
    <TimeZoneCollection Id="id" Text="text" Value="value"></TimeZoneCollection>
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

 <asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

{% highlight c# %}

namespace WebSampleBrowser.Schedule
{
    public partial class Default : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {
            List<TimeZoneCollections> timeZoneCollection = new List<TimeZoneCollections>();
            timeZoneCollection.Add(new TimeZoneCollections { text="UTC -04:00", id= "10", value = "UTC -04:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC -03:30", id = "11", value = "UTC -03:30" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC -03:00", id = "12", value = "UTC -03:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC -02:30", id = "13", value = "UTC -02:30" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC -01:00", id = "14", value = "UTC -01:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +00:00", id = "15", value = "UTC +00:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +01:00", id = "16", value = "UTC +01:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +02:00", id = "17", value = "UTC +02:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +03:00", id = "18", value = "UTC +03:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +03:30", id = "19", value = "UTC +03:30" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +04:00", id = "20", value = "UTC +04:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +04:30", id = "22", value = "UTC +04:30" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +05:00", id = "23", value = "UTC +05:00" });
            timeZoneCollection.Add(new TimeZoneCollections { text = "UTC +05:30", id = "24", value = "UTC +05:30" });

            Schedule1.TimeZoneCollection.DataSource = timeZoneCollection;
        }
            public class TimeZoneCollections
            {
                public string text { get; set; }
                public string id { get; set; }
                public string value { get; set; }
            }
    }
}

{% endhighlight %}

N> The values defined within the **TimeZoneCollection** dataSource are usually the options displayed at the start and end time zone dropdown fields of the appointment window.

## Time Mode

The time mode of the Scheduler can be either **12** or **24 hours** format which is based on the `Locale` set to the Scheduler. Since the default locale value of the Scheduler is **en-US**, therefore the time mode will be set to **12 hours** format (by default) automatically based on the culture. 

The user can also set specific time mode for the Scheduler using `TimeMode` property which accepts either **String** or **enum** value.

The following code snippet shows the way to set specific **24 hour format** time mode for the Scheduler.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" TimeMode="Hour24" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> If the **TimeMode** property is not set with specific value, then the value will be taken based on the locale assigned for the Scheduler.

## Date Format

Scheduler can be used with all valid date formats. The default date format used in Scheduler is "MM/dd/yyyy". 

If the `DateFormat` property is not specified particularly, then it will be taken based on the locale that is assigned to the Scheduler. The default locale applied on the Scheduler is "en-US", which makes it to follow the "MM/dd/yyyy" pattern by default.

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" DateFormat="yyyy/MM/dd" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

## First Day of Week

The `FirstDayOfWeek` property allows to set any of the week days as start of the week/workweek/month view in Scheduler. It accepts either the `integer` (Sunday=0, Monday=1, Tuesday=2, etc) or `string` (“Sunday”, “Monday”, etc). The default value of this `FirstDayOfWeek` depends on the current culture (language) assigned to the Scheduler.

To set different first day of week in Scheduler,

{% highlight html %}

<ej:Schedule ClientIDMode="Static" runat="server" ID="Schedule1" DataSourceID="SqlData" Width="100%" Height="525px" FirstDayOfWeek="Tuesday" CurrentDate="5/2/2014">
    <AppointmentSettings Id="Id" Subject="Subject" AllDay="AllDay" StartTime="StartTime" EndTime="EndTime" Description="Description" Recurrence="Recurrence" RecurrenceRule="RecurrenceRule"/>
</ej:Schedule>

<asp:SqlDataSource ID="SqlData" runat="server" ConnectionString="<%$ ConnectionStrings:ScheduleConnectionString %>"
            SelectCommand="SELECT * FROM [DefaultSchedule]"></asp:SqlDataSource>

{% endhighlight %}

N> The sub-control datepicker which is used within Scheduler for start/end time fields in appointment window and for date navigation purposes will also follow the same first day of week. 