---
layout: post
title: Grid Dependencies | Grid | ASP.NET Webforms | Syncfusion
description: grid dependencies
platform: aspnet
control: Grid
documentation: ug
---

# Grid Dependencies

It is necessary to refer Grid dependent scripts and CSS files in your application, if you have not configured [Embedded Resources](https://help.syncfusion.com/aspnet/embeded-resources) in your application. You may ignore this section if you embed the resources from assembly.

Adding the required JavaScript and CSS files into your application plays an important role, without which the Syncfusion controls cannot be created. It requires the following mandatory common script files.

*	jquery-1.10.2.min.js
* jquery.easing.1.3.min.js
*	jsrender.min.js

Apart from the above common scripts, it is also necessary to refer to the ej.web.all.min.js file in your application that plays a major role in control creation. It also requires reference to the ej.webform.min.js file in your application, as it is responsible for the server-side event functionalities of the ASP.NET controls.

The dependencies are available in the following locations of your machine. Please copy these files from the location given.

<table>
<tr>
<th>Files</th>
<th>Location</th>
</tr>
<tr>
<td>jquery-1.10.2.min.js<br/>jsrender.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\external</td>
</tr>
<tr>
<td>ej.web.all.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\scripts\web</td>
</tr>
<tr>
<td>ej.webform.min.js</td>
<td>&lt;Syncfusion Installed Location&gt;\Essential Studio\13.1.0.21\JavaScript\assets\scripts\common</td>
</tr>
</table>

N> Example for "Syncfusion Installed location" is "C:\Program Files (x86)\Syncfusion"

ej.web.all.min.js is a bundle of all ASP.NET controls. If you use ej.web.all.js in your application, you can ignore below table section or else you can try to render grid in your application using ej.grid.min.js file. You can refer the following frameworks and controls in your project.

Grid Dependency

<table>
<tr>
<th>
File                          </th><th>
Description/Usage</th></tr>
<tr>
<td>
ej.core.min.js</td><td>
Must be referred always before using all the JS controls.</td></tr>
<tr>
<td>
ej.data.min.js</td><td>
Used to handle data manager operation and should be used while binding data to JS controls.</td></tr>
<tr>
<td>
ej.grid.min.js</td><td>
Should be referred when using grid control.</td></tr>
<tr>
<td>
ej.pager.min.js</td><td>
Should be referred when using paging in grid.  </td></tr>
<tr>
<td>
ej.scroller.min.js</td><td>
Should be referred when using scrolling in grid.  </td></tr>
<tr>
<td>
ej.waitingpopup.min.js</td><td>
Should be referred when using the remote data binding in grid. The waiting popup will show while requesting the server for data.</td></tr>
<tr>
<td>
ej.gridresize.min.js</td><td>
Need to refer when using the resizing feature in grid.</td></tr>
<tr>
<td>
ej.dropdownlist.min.js</td><td rowspan = "8">
  These files are used while enable Editing and Filtering feature in grid.</td></tr>
<tr>
<td>
ej.dialog.min.js</td></tr>
<tr>
<td>
ej.button.min.js</td></tr>
<tr>
<td>
ej.autocomplete.min.js</td></tr>
<tr>
<td>
ej.datepicker.min.js</td></tr>
<tr>
<td>
ej.timepicker.min.js</td></tr>
<tr>
<td>
ej.datetimepicker.min.js</td></tr>
<tr>
<td>
ej.checkbox.min.js</td></tr>
<tr>
<td>
ej.editor.min.js</td></tr>
</table>


To render the Syncfusion ASP.NET controls with its unique style and theme, it is necessary to refer to the required CSS files into your application. You need to copy all the required CSS files into your application from the following location.

N> <installed location>\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web
N> For example, If you have installed the Essential Studio within C:\Program Files (x86), navigate to the following location.
N> C:\Program Files (x86)\Syncfusion\Essential Studio\13.1.0.21\JavaScript\assets\css\web

Once the CSS files are added in your application, include the reference to "ej.web.all.min.css" file in the Site.Master page, within the head section.

{% highlight html %}

<link href="Content/ej/web/default-theme/ej.web.all.min.css" rel="stylesheet" />

{% endhighlight %}

