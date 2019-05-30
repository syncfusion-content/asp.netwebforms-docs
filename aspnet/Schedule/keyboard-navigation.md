---
title: Keyboard support with shortcut keys
description: This section explains how to enable keyboard navigation support on the ASP.NET Web Forms Schedule control. 
platform: aspnet
control: schedule
documentation: ug
keywords: keyboard, shortcuts 
---
# Keyboard Navigation

The shortcut keys for accessing the sub-elements of the scheduler and other Scheduler actions are tabulated in the following table.

<table>
<tr>
<th>
Keys</th><th>
Functionality description</th></tr>
<tr>
<td width="175">
<kbd>arrow keys</kbd></td><td>
To traverse through the Scheduler cells.</td></tr>
<tr>
<td>
<kbd>Shift</kbd>+<kbd>arrow keys</kbd></td><td>
Multiple cell selection</td></tr>
<tr>
<td>
<kbd>Enter</kbd></td><td>
Pressing enter key, after a single/multiple scheduler cell selection will make the quick appointment window to pop-up.<br/><br/>Also, when the focus is being moved on to the fields like checkbox or buttons of the appointment window, pressing enter will select that particular action. </td></tr>
<tr>
<td>
<kbd>Esc</kbd></td><td>
Closes any of the popup that displays on the Schedule control.</td></tr>
<tr>
<td>
<kbd>Alt</kbd>+<kbd>N</kbd></td><td>
Opens the Create Appointment window</td></tr>
<tr>
<td>
<kbd>Ctrl</kbd>+<kbd>E</kbd></td><td>
Opens the Edit Appointment window</td></tr>
<tr>
<td>
<kbd>Alt</kbd>+<kbd>C</kbd></td><td>
Opens the calendar popup within the Scheduler.</td></tr>
<tr>
<td>
<kbd>Ctrl</kbd>+<kbd>left arrow</kbd></td><td>
Previous date navigation</td></tr>
<tr>
<td>
<kbd>Ctrl</kbd>+<kbd>right arrow</kbd></td><td>
Next date navigation</td></tr>
<tr>
<td>
<kbd>Alt</kbd>+<kbd>+</kbd></td><td>
Forward traversing of view items in the toolbar</td></tr>
<tr>
<td>
<kbd>Alt</kbd>+<kbd>-</kbd></td><td>
Reverse traversing of view items in the toolbar</td></tr>
<tr>
<td>
<kbd>Space</kbd></td><td>
When the previous/next navigation icons are currently being focused, pressing space navigates through the corresponding dates.<br/><br/>Also, when the focus is being moved on to the fields like checkbox or buttons of the appointment window, pressing enter will select that particular action.</td></tr>
<tr>
<td>
<kbd>Del</kbd></td><td>
Deletes the currently selected appointment.</td></tr>
<tr>
<td>
<kbd>Tab</kbd></td><td>
Traversing through the appointments in a forward direction.</td></tr>
<tr>
<td>
<kbd>Shift</kbd>+<kbd>tab</kbd></td><td>
Traversal of appointments in a reverse order.</td></tr>
</table>

N> By default `AllowKeyboardNavigation` property is set to **true**, which allows the Scheduler to be accessed through the above specified keys.

