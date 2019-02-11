---
layout: post
title: Member Editor | PivotGrid | ASP.NET | Syncfusion
description: Member editor in pivot grid control
platform: aspnet
control: PivotGrid
documentation: ug
---

# Member Editor

The member editor dialog displays the members of current field in a tree view structure, which is opened by clicking the filter icon available in the grouping bar. It helps to search, filter, and sort the field members available in the pivot grid control.

![Member editor in ASP NET pivot grid control](Member_Editor_images/member_editor.png)

## Member editor - Paging

The paging support in the member editor helps you to improve the rendering performance of the member editor dialog by dividing the large amounts of data into sections and displaying them.

You can enable the member editor paging and set the member editor page size in the pivot grid control by setting the `EnableMemberEditorPaging` and `MemberEditorPageSize` properties.

{% highlight html %}

<ej:PivotClient ID="PivotGrid1" runat="server" EnableMemberEditorPaging="true" MemberEditorPageSize="100" >
    <%--...--%>
</ej:PivotClient>

{% endhighlight %}

Following are the navigation options available in the member editor pager:
* Move first: Navigates to the first page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Move last: Navigates to the last page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in the numeric value.


![Paging support in member editor of ASP NET pivot grid control](Member_Editor_images/member_editor_paging.png)

## Member editor - Sorting

The sorting support in the member editor helps you to sort the field members in ascending or descending order.

You can enable the member editor sorting in the pivot grid control by setting the `enableMemberEditorSorting` property.

{% highlight html %}

<ej:PivotClient ID="PivotGrid1" runat="server" EnableMemberEditorSorting="true">
    <%--...--%>
</ej:PivotClient>

{% endhighlight %}

![Ascending order of field items in ASP NET pivot grid control](Member_Editor_images/member_editor_sorting_ascending.png)

![Descending order of field items in ASP NET pivot grid control](Member_Editor_images/member_editor_sorting_descending.png)