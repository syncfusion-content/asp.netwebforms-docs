---
layout: post
title: Web Accessbility in DropDownList | Syncfusion | ASP.NET WebForms
description: Web accessibliy support to DropDownList control for Syncfusion Essential ASP.NET
platform: aspnet
control: DropDownList
documentation: ug
keywords: Keyboard Navigation, DropDownList, Accessibility
---

# Accessibility 

## Keyboard Navigation

You can use the keyboard short cut keys as an alternative to the mouse and interact with DropDownList control.
Keyboard shortcut keys are,

<table>
<tr>
<td>
**Key**
</td>
<td>
**Single selection**
</td>
<td>
**Multi-selection**
</td>
</tr>
<tr>
    <td>
       {{'[Access key](http://en.wikipedia.org/wiki/Access_key)' | markdownify }} + j
    </td>
    <td>
        Sets focus to the input
    </td>
    <td>
        Sets focus to the input
    </td>
</tr>
<tr>
<td>
Up
</td>
<td>
Selects the previous item when the popup is opened/closed

</td>
<td>
Selects the previous item when the popup is opened/closed and clears all other selection 

</td>
</tr>
<tr>
<td>
Down
</td>
<td>
Selects the next item when the popup is opened/closed
</td>
<td>
Selects the next item when the popup is opened/closed and clears all other selection 

</td>
</tr>
<tr>
<td>
Page up 
</td>
<td>
Selects the item in next page (i.e.,) scrolls down to next set of items when the popup is opened/closed

</td>
<td>
Selects the item in next page (i.e.,) scrolls down to next set of items when the popup is opened/closed and clear all existing selection 

</td>
</tr>
<tr>
<td>
Page down 
</td>
<td>
Selects the item in previous page (i.e.,) scrolls up to previous set of items when the popup is opened/closed

</td>
<td>
Selects the item in previous page (i.e.,) scrolls up to previous set of items when the popup is opened/closed and clear all existing selection
</td>
</tr>
<tr>
<td>
Left arrow
</td>
<td>
Selects the previous item when the popup is opened/closed. But in RTL mode selects next item

</td>
<td>
Selects the previous item when the popup is opened/closed and clears all other selection but in RTL mode selects the next item 
</td>
</tr>
<tr>
<td>
Right arrow
</td>
<td>
Selects the next item when the popup is opened/closed. But in RTL mode selects previous item

</td>
<td>
Selects the next item when the popup is opened/closed and clears all other selection but in RTL mode selects the previous item
</td>
</tr>
<tr>
<td>
Backspace
</td>
<td>
No actions 
</td>
<td>
Deletes the selected items from last when visual mode is enabled. (i.e.,) on first backspace key press, the last item will be selected and second backspace press will remove the corresponding item. 
</td>
</tr>
<tr>
<td>
Tab
</td>
<td>
Close the popup if it is opened and  focuses to next DOM element 
</td>
<td>
Close the popup if it is opened and  focuses to next DOM element
</td>
</tr>
<tr>
<td>
End
</td>
<td>
Selects the last list item
</td>
<td>
Select the last item and clear all selection 
</td>
</tr>
<tr>
<td>
Home
</td>
<td>
Selects the first list item 
</td>
<td>
Select the first item and clear all selection 
</td>
</tr>
<tr>
<td>
Esc
</td>
<td>
Close the popup if it’s opened
</td>
<td>
Close the popup if it’s opened
</td>
</tr>
<tr>
<td>
Space bar
</td>
<td>
Close the popup is it’s opened
</td>
<td>
Check and uncheck the items which is focused.  
</td>
</tr>
<tr>
<td>
Delete
</td>
<td>
No actions
</td>
<td>
Deletes the focused item in textbox when visual mode is enabled
</td>
</tr>
<tr>
<td>
Shift + up
</td>
<td>
Selects the previous item when the popup is opened/closed

</td>
<td>
Selects the immediate preceding item from current selected item 

</td>
</tr>
<tr>
<td>
Shift + down
</td>
<td>
Selects the next item when the popup is opened/closed

</td>
<td>
Selects the immediate successive item from current selected item  

</td>
</tr>
<tr>
<td>
Shift + home
</td>
<td>
Select the first list item
</td>
<td>
Select all items between focused item to first item

</td>
</tr>
<tr>
<td>
Shift + end
</td>
<td>
Selects the last list item
</td>
<td>
Select all items between focused item to last item 
</td>
</tr>
<tr>
<td>
Shift + page up
</td>
<td>
Selects the item in previous page (i.e.,) scrolls down to previous set of items when the popup is opened/closed

</td>
<td>
Select all item between focused item to previous page or previous set of items when the popup is opened/closed

</td>
</tr>
<tr>
<td>
Shift + page down
</td>
<td>
Selects the item in next page (i.e.,) scrolls up to next set of items when the popup is opened/closed

</td>
<td>
Select all item between focused item to next page or next set of items when the popup is opened/closed

</td>
</tr>
<tr>
<td>
Ctrl +  up
</td>
<td>
Selects the previous item when the popup is opened/closed

</td>
<td>
Maintain current selections and hovers to the previous item when the popup is opened/closed

</td>
</tr>
<tr>
<td>
Ctrl + down
</td>
<td>
Selects the next item when the popup is opened/closed

</td>
<td>
Maintain current selection and hovers to the next item when the popup is opened/closed

</td>
</tr>
<tr>
<td>
Alt + down
</td>
<td>
Opens the popup if it’s closed
</td>
<td>
Open the popup if it’s closed
</td>
</tr>
<tr>
<td>
Alt + up
</td>
<td>
Closes the popup if it’s opened
</td>
<td>
Close the popup if it’s opened
</td>
</tr>
<tr>
<td>
Enter
</td>
<td>
Closes the popup if it’s opened
</td>
<td>
Selects the focused item when ctrl key pressed otherwise closes the popup if it’s opened
</td>
</tr>
<tr>
<td>
Shift + Tab
</td>
<td>
Focuses the previous DOM element 
</td>
<td>
Focuses the previous DOM element
</td>
</tr>
<tr>
<td>
Ctrl + shift + up 
</td>
<td>
Selects the previous item when the popup is opened/closed

</td>
<td>
Maintains the existing items selection and selects the previous item from current selection. 

</td>
</tr>
<tr>
<td>
Ctrl + shift + down
</td>
<td>
Selects the next item when the popup is opened/closed

</td>
<td>
Maintain the existing items selection and selects next item from current selection. 

</td>
</tr>
</table>

**Note:**

i) *For Ctrl and Shift operations with multi-selection, the current focused item should be selected.*

ii) *No round robin method is used on navigating through the list items in pop up, so that navigation stops when reaching the start/end of the popup list.* 