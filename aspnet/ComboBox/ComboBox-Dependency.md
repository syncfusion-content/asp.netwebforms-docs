---
layout: post
title: Dependencies of ASP.NET WebForm ComboBox Control | Syncfusion
description: Learn here all about dependancy of Syncfusion Essential ASP.NET WebForm ComboBox control, its elements, and more.
platform: aspnet
control: ComboBox
documentation: ug
---

# Dependencies of ASP.NET WebForm ComboBox

The external script dependencies of the ComboBox control are,

* [jQuery 1.7.1](http://jquery.com/) and later versions.

The internal script dependency ej.web.all.js is a bundle of all Syncfusion ASP.NET controls. If you use ej.web.all.js in your application, you can leave this section or else you can try to render ComboBox in your application using ej.combobox.min.js file. You can refer the following frameworks and controls in your project.

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
		<td>ej.combobox.min.js</td>
		<td>The ComboBox's main file</td>
	</tr>
	<tr>
		<td>ej.globalize.min.js</td>
		<td>processing specific source-side actions globally.</td>
	</tr>
    <tr>
		<td>ej.webform.min.js</td>
		<td>Should be referred when using server side events functionalities with all EJ controls.</td>
	</tr>
</table>
