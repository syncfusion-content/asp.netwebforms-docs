---
layout: post
title: Style and Appearance with Grid widget for Syncfusion Essential ASP.NET
description: How to apply styling and appearance
platform: aspnet
control: Grid
documentation: ug
---

# Style and Appearance

## List of classes and its purposes

To modify Grid appearance, you need to override default CSS of Grid. Please find the list of CSS classes and its corresponding section in Grid. Also you have an option to create your own custom theme for all ASP.NET controls using our `Theme Studio`. 

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
                e-grid 
            </td>
            <td rowspan="2">
                This classes are in this root element (div) of grid control. 
            </td>
        </tr>
        <tr>          
            <td>
                e-js
            </td>
        </tr>
        <tr>
            <td rowspan="5">
                Header
            </td>
            <td>
                e-gridheader
            </td>
            <td>
                This is class is added in the root element of header element. In this class, You can override thin line between header and content of grid.
            </td>
        </tr>
        <tr> 
            <td>
                e-table
            </td>
            <td>
                This class is added at 'table' of grid header. This CSS class makes table width as 100 %.
            </td>
        </tr>
        <tr>   
            <td>
                e-columnheader
            </td>
            <td>
                This class is added at 'tr' of grid header. 
            </td>
        </tr>
        <tr>
            <td>
                e-headercell
            </td>
            <td>
                This class is added in 'th' element of grid header. You can override background color of header and border color
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
                e-gridcontent
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
                e-alt_row
            </td>
            <td>
                This class is added to alternate rows of grid. This is to override alternate row color of grid.
            </td>
        </tr>
        <tr>
            <td>
                e-rowcell
            </td>
            <td>
                This class is added to all cells in grid. This is to override cells appearance and styling.
            </td>
        </tr>
        <tr>
            <td>
                e-groupcaption
            </td>
            <td>
                This class is added to 'td' of group caption which is to change background color of caption cell.
            </td>
        </tr>
        <tr>
            <td>
                e-selectionbackground
            </td>
            <td>
                This class will be added to each selected rows of grid. This can be used to override the selection.
            </td>
        </tr>
        <tr>
            <td>
                e-hover 
            </td>
            <td>
                This class adds to row of grid while hover grid rows.
            </td>
        </tr>
        <tr>
            <td rowspan="3">
                Pager
            </td>
            <td>
                e-pager
            </td>
            <td>
                This class is added to root element of pager. This to change appearance of background color and color of font.
            </td>
        </tr>
        <tr>  
            <td>
                e-pagercontainer
            </td>
            <td>
                This class is added to numeric items of pager.
            </td>
        </tr>
        <tr>   
            <td>
                e-parentmsgbar
            </td>
            <td>
                This class is added to pager info of pager.
            </td>
        </tr>
        <tr>
            <td rowspan="4">
                Summary
            </td>
            <td>
                e-gridfooter
            </td>
            <td>
                This class is added to root of summary div.
            </td>
        </tr>
        <tr>    
            <td>
                e-gridsummary
            </td>
            <td>
                This class is added to table of summary. This CSS class makes table width as 100 %.
            </td>
        </tr>
        <tr>   
            <td>
                e-gridSummaryRows
            </td>
            <td>
                This class is added to rows of grid summary. 
            </td>
        </tr>
        <tr>
            <td>
                e-summaryrow
            </td>
            <td>
                This class is added to cells of summary row. This to override background color of summary.
            </td>
        </tr>
    </table>
	
## Toolbar Customization

To customize toolbar, you need to use toolbar default CSS class to override icon in toolbar. 

{% seealso %} [customize toolbar ](http://www.syncfusion.com/kb/5076/how-to-change-custom-icons-for-default-edit-toolbar-items "customize toolbar") {% endseealso %}
