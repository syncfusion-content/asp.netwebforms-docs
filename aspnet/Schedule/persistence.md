---
title: State persistence
description: Persisting Schedule Properties
platform: aspnet
control: schedule
documentation: ug
keywords: persist, state persist, persistence, state persistence 
---
# Persistence

State persistence allows the Scheduler to retain the current model value in the browser cookies for state maintenance. This action is handled through the property `EnablePersistence` which is set to false by default.

When it is set to **true**, some of the Schedule control model values will be retained even after refreshing the page which are listed below.

<table>
<tr>
<td>
CurrentView</td><td>
TimeMode</td></tr>
<tr>
<td>
FirstDayOfWeek</td><td>
DateFormat</td></tr>
<tr>
<td>
IsDST</td><td>
TimeZone</td></tr>
<tr>
<td>
TimeScale</td><td>
StartHour</td></tr>
<tr>
<td>
EndHour</td><td>
WorkHours</td></tr>
<tr>
<td>
Height</td><td>
Width</td></tr>
<tr>
<td>
CellHeight</td><td>
CellWidth</td></tr>
<tr>
<td>
currentDate</td><td>
MinDate</td></tr>
<tr>
<td>
MaxDate</td><td>
RenderDates</td></tr>
<tr>
<td>
Orientation</td><td>
Views</td></tr>
<tr>
<td>
WorkWeek</td><td>
AgendaViewSettings.daysInAgenda</td></tr>
<tr>
<td>
EnableLoadOnDemand</td><td>
ShowLocationField</td></tr>
<tr>
<td>
ShowAllDayRow</td><td>
IsResponsive</td></tr>
<tr>
<td>
EnableRecurrenceValidation</td><td>
ShowOverflowButton</td></tr>
<tr>
<td>
AllowDragDrop</td></tr>
ShowDeleteConfirmationDialog</td></tr>
<tr>
<td>
ShowNextPrevMonth</td></tr>
AppointmentDragArea</td></tr>
</table>

The Schedule properties that are not retained while maintaining state persistence are included within the **ignoreOnPersist** list, which makes it not to persist by default.

