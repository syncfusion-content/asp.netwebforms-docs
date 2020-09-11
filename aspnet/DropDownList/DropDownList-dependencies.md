---
layout: post
title: Dependencies of the DropDownList control for Syncfusion ASP.NET WebForm
description: Dependencies of the DropDownList control for Syncfusion ASP.NET WebForm 
platform: aspnet
control: DropDownList
documentation: ug
---

# DropDownList Dependencies

The external script dependencies of the DropDownList control are,

* [jQuery 1.7.1](http://jquery.com/) and later versions.
* [jQuery.easing](http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.min.js) - to support the animation effects.

The internal script dependency ej.web.all.js is a bundle of all Syncfusion ASP.NET controls. If you use ej.web.all.js in your application, you can leave this section or else you can try to render DropDownList in your application using ej.dropdownlist.min.js file. You can refer the following frameworks and controls in your project.

<table>
	<tr>
		<th>File </th>
		<th>Description / Usage </th>
	</tr>
	<tr>
		<td>ej.core.min.js</td>
		<td>Must be referred always before using all the EJ controls.</td>
	</tr>
	<tr>
		<td>ej.data.min.js</td>
		<td>Used to handle data operation and should be used while binding data to EJ controls.</td>
	</tr>
	<tr>
		<td>ej.dropdownlist.min.js</td>
		<td>The dropdownlist’s main file</td>
	</tr>
	<tr>
		<td>ej.scroller.min.js</td>
		<td>Should be referred when using scrolling in DropDownList.</td>
	</tr>
	<tr>
		<td>ej.draggable.min.js</td>
		<td>Should be referred when using popup resize functionality in DropDownList.</td>
	</tr>
    <tr>
		<td>ej.webform.min.js</td>
		<td>Should be referred when using server side events functionalities with all EJ controls.</td>
	</tr>
</table>
