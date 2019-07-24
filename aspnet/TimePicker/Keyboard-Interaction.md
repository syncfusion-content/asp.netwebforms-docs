---
layout: post
title: Keyboard Interaction | TimePicker | ASP.NET | Syncfusion
description: keyboard interaction
platform: aspnet
control: TimePicker
documentation: ug
---

# Keyboard Interaction

You can use Keyboard shortcut keys as an alternative to the mouse on using TimePicker control. TimePicker control allows you to perform all kinds of actions by using keyboard shortcuts.

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
{{'[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j</td><td>
Focuses onto the Timepicker control.</td></tr>
<tr>
<td>
Alt + Down</td><td>
Opens/Hides the pop up.</td></tr>
<tr>
<td>
Right/Left</td><td>
Moves to adjacent part.</td></tr>
<tr>
<td>
Up</td><td>
Increments the value.</td></tr>
<tr>
<td>
Down</td><td>
Decrements the value.</td></tr>
</table>


### When popup is open

<table>
<tr>
<th>
Shortcut Key</th><th>
Description</th></tr>
<tr>
<td>
Up</td><td>
Selects the previous time. </td></tr>
<tr>
<td>
Down </td><td>
Selects the next time.</td></tr>
<tr>
<td>
Home/End</td><td>
Moves to the first / last item.</td></tr>
<tr>
<td>
Esc</td><td>
Closes the pop up.</td></tr>
</table>

## Configure Keyboard Interaction

In the ASPX page, include the following TimePicker control and enable keyboard interaction by setting the access key property.



{% highlight html %}

<ej:TimePicker ID="time" runat="server"></ej:TimePicker>

{% endhighlight %}



{% highlight js %}

<script type="text/javascript">
    $(function () {
         $(document).on("keydown", function (e) {
               if (e.altKey && e.keyCode === 74) { // j- key code.
                     $("#<%= time.ClientID %>").focus();
          }
       });
    });
</script>

{% endhighlight %}



Run the code example, press Alt + J to focus on the TimePicker control that enables it and you can navigate by using arrow keys and Esc key to close the pop up.



![Keyboard Interaction](Keyboard-Interaction_images/Keyboard-Interaction_img1.png) 



