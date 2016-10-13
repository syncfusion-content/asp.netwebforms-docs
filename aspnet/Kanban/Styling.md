---
layout: post
title: Style and Appearance with Kanban widget for Syncfusion Essential ASP.NET
description: How to apply styling and appearance
platform: aspnet
control: Kanban
documentation: ug
---

# Styling

## List of classes and its purposes

To modify Kanban appearance, you need to override default CSS of Kanban. Please find the list of CSS classes and its corresponding section in Kanban. Also you have an option to create your own custom theme for all JavaScript controls using our [`Theme Studio`](http://js.syncfusion.com/themestudio/).

<table>
        <tr>
            <th>
              Section  
            </th>
            <th>
              CSS class 
            </th>
            <th>
              Purpose of CSS class 
            </th>
        </tr>
        <tr>
            <td rowspan="2">
                Root  
            </td>
            <td>
                e-kanban 
            </td>
            <td rowspan="2">
              This classes are in this root element (`div`) of Kanban control. 
            </td>
        </tr>
        <tr>
            <td>
                e-js 
            </td>
        
        </tr>
      
        <tr>
            <td rowspan="6">
                Header 
            </td>
            <td>
               e-kanbantoolbar
            </td>
            <td>
               This class is added at `div` element of Kanban toolbar. 
            </td>
        </tr>
        <tr>
            <td>
               e-kanbanheader
            </td>
            <td>
                This is class is added in the root element of header element. In this class, You can override thin line between header and content of Kanban. 
            </td>
        </tr>
        <tr>
            <td>
                e-table 
            </td>
            <td>
               This class is added at 'table' of Kanban header. This CSS class makes table width as 100 %.  
            </td>
        </tr>
        <tr>
            <td>
              e-columnheader 
            </td>
            <td>
               This class is added at 'tr' of Kanban header. 
            </td>
        </tr>
        <tr>
            <td>
              e-headercell 
            </td>
            <td>
                This class is added in 'th' element of Kanban header. You can override background color of header and border color 
            </td>
        </tr>
        <tr>
            <td>
               e-headercelldiv 
            </td>
            <td>
              This class is add in div which present 'th' element in header. You recommend you to use e-headercelldiv to override skeleton of header. 
            </td>
        </tr>
    
       
        <tr>
            <td rowspan="7">
                Body  
            </td>
            <td>
              e-kanbancontent 
            </td>
            <td>
              This class is added at root of body content. This is to override background color of body.  
            </td>
        </tr>
        <tr>
            <td>
              e-table 
            </td>
            <td>
               This class is added to table of content. This CSS class makes table width as 100 %. 
            </td>
        </tr>
        <tr>
            <td>
                e-swimlanerow
            </td>
            <td>
               This class is added to all swim lane ‘tr’s in Kanban.   
            </td>
        </tr>
        <tr>
            <td>
              e-columnrow
            </td>
            <td>
              This class is added to all next row of swimlane ‘tr’s in Kanban
            </td>
        </tr>
        <tr>
            <td>
              e-rowcell  
            </td>
            <td>
                This class is added to all cells in Kanban. This is to override cells appearance and styling. 
            </td>
        </tr>
        <tr>
            <td>
               e-cardselection 
            </td>
            <td>
               This class is added to card div element of Kanban. This is override selection. 
            </td>
        </tr>
          <tr>
            <td>
               e-hover 
            </td>
            <td>
              This class adds to card of Kanban while hover cards.  
            </td>
        </tr>
    </table>