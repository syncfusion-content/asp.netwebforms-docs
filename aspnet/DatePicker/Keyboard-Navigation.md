---
layout: post
title: Keyboard-Navigation
description: keyboard navigation
platform: aspnet
control: DatePicker
documentation: ug
---

# Keyboard Navigation

With the Keyboard Navigation enabled in the DatePicker control, it is possible to control the actions of the DatePicker with the provided shortcut keys. Almost all the DatePicker actions that are done through mouse are controlled with shortcut keys. By default, the keyboard navigation is set to true for the control and it is controlled with the property AllowKeyboardNavigation.

The various keyboard shortcuts available within the DatePicker control are discussed in the following table.

<table>
<tr>
<th>
Keys</th><th>
Function</th></tr>
<tr>
<td>
Alt +j</td><td>
Focuses the control.</td></tr>
<tr>
<td>
Alt + Down</td><td>
Opens the popup.</td></tr>
<tr>
<td>
LeftRight</td><td>
Moves to previous date.Moves to next date.</td></tr>
<tr>
<td>
Up</td><td>
Moves one week upward.</td></tr>
<tr>
<td>
Down</td><td>
Moves one week downward.</td></tr>
<tr>
<td>
Enter</td><td>
Selects the focused date.</td></tr>
<tr>
<td>
Esc</td><td>
Closes the popup.</td></tr>
<tr>
<td>
Ctrl + Up</td><td>
Navigates to top view.</td></tr>
<tr>
<td>
Ctrl + Down</td><td>
Navigates to lower view.</td></tr>
<tr>
<td>
Ctrl + Left</td><td>
Navigates to previous month.</td></tr>
<tr>
<td>
Ctrl + Right</td><td>
Navigates to next month.</td></tr>
</table>


In the ASPX page, add the DatePicker control to enable keyboard interaction by setting the accesskey property.



{% highlight html %}



   <ej:DatePicker ID="datepicker" runat="server"> </ej:DatePicker>





{% endhighlight %}





{% highlight js %}



          $(function () {



              $(document).on("keydown", function (e) {

                  if (e.altKey && e.keyCode === 74) { // j- key code.

                      $("#<%=datepicker.ClientID %>").focus();

                  }

              });

          });



{% endhighlight %}





Run the sample, press Alt + J to focus in the DatePicker control that enables it and you can navigate by using arrow keys and Esc key to close the popup.

![](Keyboard-Navigation_images/Keyboard-Navigation_img1.png) 



