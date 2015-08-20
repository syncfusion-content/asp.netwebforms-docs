---
layout: post
title: Ribbon-Dependencies
description: ribbon dependencies
platform: aspnet
control: Ribbon
documentation: ug
---

# Ribbon Dependencies

_ej.web.all.js_ is a bundle of all ASP.NET controls. When you use _ej.web.all.js_ in your application, you can leave this section or else you can try to render _Ribbon_ in your application by using _ej.ribbon_ file. You can refer to the following frameworks and controls in your project.

Table 1: Ribbon Dependency

<table>
<tr>
<th>
Files                          </th><th>
Description/Usage </th></tr>
<tr>
<td>
ej.core.min.js</td><td>
Must always be referred to before using all the ASP.NET controls.</td></tr>
<tr>
<td>
ej.data.min.js</td><td>
Used to handle datamanger operation and should be used while binding data to ASP.NET controls.</td></tr>
<tr>
<td>
ej.ribbon.min.js</td><td>
Should be referred when using Ribbon control.</td></tr>
<tr>
<td>
ej.menu.min.js</td><td>
This file is used to render menu in the application tab.</td></tr>
<tr>
<td>
ej.scroller.min.js</td><td>
This file is used to render scroller in the Ribbon control.</td></tr>
<tr>
<td>
ej.checkbox.min.js</td><td>
This file is used to render checkboxes in the Ribbon control.</td></tr>
<tr>
<td>
ej.tab.min.js</td><td>
This file is used to render tabs into the Ribbon control.</td></tr>
<tr>
<td>
ej.dropdownlist.min.js</td><td rowspan = "4">
  These files are used to render button,split button,toggle button, and dropdownlist controls in the ribbon groups.</td></tr>
<tr>
<td>
ej.splitbutton.min.js</td></tr>
<tr>
<td>
ej.button.min.js</td></tr>
<tr>
<td>
ej.togglebutton.min.js</td></tr>
</table>

