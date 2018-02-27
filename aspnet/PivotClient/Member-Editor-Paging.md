---
layout: post
title: Member Editor Paging | PivotClient | ASP.NET | Syncfusion 
description: memebr editor paging
platform: aspnet
control: PivotClient
documentation: ug
---

# Member editor paging

I> This feature is applicable only for the OLAP data source.

The member editor paging helps you to improve the rendering performance of the dialog by dividing the large amount of data into sections and displaying them.

You can enable the member editor paging and set the member editor page size in the pivot client control by setting the [`EnableMemberEditorPaging`] and [`MemberEditorPageSize`] properties.


{% highlight html %}

<ej:PivotClient ID="PivotClient1" runat="server" EnableMemberEditorPaging="true" MemberEditorPageSize="100" >
    //...
</ej:PivotClient>

{% endhighlight %}

Following are the navigation options available in the member editor pager:
* Move first: Navigates to the first page.
* Move previous: Navigates to the previous page from the current page.
* Move next: Navigates to the next page from the current page.
* Move last: Navigates to the last page.
* Numeric box: Navigates to the desired page by entering an appropriate page number in numeric value.


![](Member_Editor_images/member_editor.png)