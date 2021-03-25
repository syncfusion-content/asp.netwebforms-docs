---
layout: post
title: Localization with Kanban widget for Syncfusion Essential ASP.NET
description: This section explains how to provide support for localization in the Syncfusion ASP.NET Web Forms Kanban component.
platform: aspnet
control: Kanban
documentation: ug
---


# Localization

## Localization

All text in Kanban can be localized using `ej.Kanban.Locale` object. Please find the table with list of properties and its value in locale object.

<table>
<tr>
<th>
Locale key words </th><th>
Text</th></tr>
<tr>
<td>
EmptyCard</td><td>
No records to display</td></tr>
<tr>
<td>
SaveButton</td><td>
Save</td></tr>
<tr>
<td>
CancelButton</td><td>
Cancel</td></tr>
<tr>
<td>
EditFormTitle</td><td>
Details of</td></tr>
<tr>
<td>
AddFormTitle</td><td>
Add New Card</td></tr>
<tr>
<td>
SwimlaneCaptionFormat</td><td>
"- item items "</td></tr>
<tr>
<td>
FilterSettings</td><td>
Filters:</td></tr>
<tr>
<td>
Min</td><td>
Min</td></tr>
<tr>
<td>
Max</td><td>
Max</td></tr>
<tr>
<td>
FilterOfText</td><td>
Of</td></tr>
<tr>
<td>
Cards</td><td>
Cards</td></tr>
<tr>
<td>
ItemsCount
</td><td>
Items Count :
</td></tr>
<tr>
<td>
Unassigned
</td><td>
Unassigned
</td></tr>
<tr>
<td>
AddCard
</td><td>
Add Card
</td></tr>
<tr>
<td>
EditCard
</td><td>
Edit Card
</td></tr>
<tr>
<td>
DeleteCard
</td><td>
Delete Card
</td></tr>
<tr>
<td>
TopofRow
</td><td>
Top of Row
</td></tr>
<tr>
<td>
BottomofRow
</td><td>
Bottom of Row
</td></tr>
<tr>
<td>
MoveUp
</td><td>
Move Up
</td></tr>
<tr>
<td>
MoveDown
</td><td>
Move Down
</td></tr>
<tr>
<td>
MoveLeft
</td><td>
Move Left
</td></tr>
<tr>
<td>
MoveRight
</td><td>
Move Right
</td></tr>
<tr>
<td>
MovetoSwimlane
</td><td>
Move to Swimlane
</td></tr>
<tr>
<td>
HideColumn
</td><td>
Hide Column
</td></tr>
<tr>
<td>
VisibleColumns
</td><td>
Visible Columns
</td></tr>
<tr>
<td>
PrintCard
</td><td>
Print Card
</td></tr>
<tr>
<td>
Search
</td><td>
Search
</td></tr>
</table>

The following code example describes the above behavior. 

{% highlight js %}

          <script type="text/javascript">
                ej.Kanban.Locale["de-DE"] = {
                    EmptyCard: "Keine Karten angezeigt werden",
                    SaveButton: "Speichern",
                    CancelButton: "stornieren",
                    EditFormTitle: "Details von ",
                    AddFormTitle: "Neue Karte hinzufügen",
                    SwimlaneCaptionFormat: "- {{:count}}{{if count == 1 }} Artikel {{else}} Artikel {{/if}}",
                    FilterSettings: "Filter:",
                    FilterOfText: "Von",
                    Max: "Max.",
                    Min: "Min.",
                    Cards: "Karten",
                    ItemsCount: "Artikel Graf :"
                    Unassigned:"Nicht zugewiesen",
                };
            </script>    

{% endhighlight  %}

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" KeyField="Status" Locale="de-DE" EnableTotalCount="true">
                <Columns>
                    <ej:KanbanColumn HeaderText="Backlog" Key="Open" />
                    <ej:KanbanColumn HeaderText="In Progress" Key="InProgress">
                        <Constraints Max="2" />
                    </ej:KanbanColumn>
                    <ej:KanbanColumn HeaderText="Done" Key="Close" />
                </Columns>
                <ClientSideEvents ContextClick="contextclick" />
                <Fields Content="Summary" PrimaryKey="Id" Tag="Tags" SwimlaneKey="Assignee" />
      </ej:Kanban>

{% endhighlight %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "Analyze the new requirements gathered from the customer.", "Story", "Low", "Analyze,Customer", 3.5, "Nancy", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "Improve application performance", "Improvement", "Normal", "Improvement", 6, "Andrew", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", "Arrange a web meeting with the customer to get new requirements.", "Others", "Critical", "Meeting", 5.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "InProgress", "Fix the issues reported in the IE browser.", "Bug", "Release Breaker", "IE", 2.5, "Janet", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(5, "Testing", "Fix the issues reported by the customer.", "Bug", "Low", "Customer", 3.5, "Steven", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", "Arrange a web meeting with the customer to get the login page requirements.", "Others", "Low", "Meeting", 2, "Michael", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", "Validate new requirements", "Improvement", "Low", "Validation", 1.5, "Robert", "../content/images/kanban/7.png", 4));
            Task.Add(new Tasks(8, "Close", "Login page validation", "Story", "Release Breaker", "Validation,Fix", 2.5, "Laura", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "Fix the issues reported in Safari browser.", "Bug", "Release Breaker", "Fix,Safari", 1.5, "Nancy", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the IE browser.", "Story", "Low", "Testing,IE", 5.5, "Margaret", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "Validate the issues reported by the customer.", "Story", "High", "Validation,Fix", 1, "Steven", "../content/images/kanban/5.png", 5));
            Task.Add(new Tasks(12, "Testing", "Check Login page validation.", "Story", "Release Breaker", "Testing", 0.5, "Michael", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", "API improvements.", "Improvement", "High", "Grid,API", 3.5, "Robert", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", "Add responsive support to application", "Epic", "Critical", "Responsive", 6, "Laura", "../content/images/kanban/8.png", 3));
            Task.Add(new Tasks(15, "Open", "Show the retrieved data from the server in grid control.", "Story", "High", "Database,SQL", 5.5, "Margaret", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
           }

{% endhighlight  %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![ASPNET Kanban Localization image1](Localization_images/Localization_img1.png)

## Right to Left (RTL)

By default, Kanban render its text and layout from left to right. To customize Kanban’s direction, you can change direction from LTR to RTL by using `EnableRTL` as true.

The following code example describes the above behavior.

{% highlight js %}

            <script type="text/javascript">
                ej.Kanban.Locale["ar-AE"] = {
                    EmptyCard: "لا بطاقات لعرض",
                    SaveButton: "حفظ",
                    CancelButton: "إلغاء",
                    EditFormTitle: "تفاصيل ",
                    AddFormTitle: "إضافة بطاقة جديدة",
                    SwimlaneCaptionFormat: "- {{:count}}{{if count == 1 }} بند {{else}} العناصر {{/if}}",
                    FilterSettings: "مرشحات:",
                    FilterOfText: "من",
                    Max: "ماكس",
                    Min: "دقيقة",
                    Cards: "  بطاقات",
                    ItemsCount: "عد العناصر:",
                    Unassigned: "غير معين",
                };
            </script>

{% endhighlight  %}

{% tabs %}

{% highlight html %}

     <ej:Kanban ID="Kanban" runat="server" Locale="ar-AE" EnableRTL="true" AllowTitle="true" KeyField="Status">
                <Columns>
                    <ej:KanbanColumn HeaderText="تراكم الأعمال غير المنجزة" Key="Open" />
                    <ej:KanbanColumn HeaderText="في تَقَدم" Key="InProgress">
                        <Constraints Max="2" />
                    </ej:KanbanColumn>
                    <ej:KanbanColumn HeaderText="فعله" Key="Close" />
                </Columns>
                <Fields Content="Summary" ImageUrl="ImgUrl" PrimaryKey="Id" SwimlaneKey="Assignee" />
      </ej:Kanban>

{% endhighlight %}

{% highlight c# %}

          List<Tasks> Task = new List<Tasks>();  
          protected void Page_Load(object sender, EventArgs e)
          {
            Task.Add(new Tasks(1, "Open", "تحليل المتطلبات الجديدة التي تم جمعها من العملاء.", "قصة", "منخفض", " تحليل, زبون", 3.5, "Davolio  نانسي", "../content/images/kanban/1.png", 1));
            Task.Add(new Tasks(2, "InProgress", "تحسين أداء التطبيقات.", " تحسين", "عادي", " تحسين", 6, " أندرو فولر", "../content/images/kanban/2.png", 1));
            Task.Add(new Tasks(3, "Open", " ترتيب لقاء على شبكة الإنترنت مع العملاء للحصول على المتطلبات الجديدة.", "آخرون", "حرج", "لقاء", 5.5, "جانيت Leverling", "../content/images/kanban/3.png", 2));
            Task.Add(new Tasks(4, "في تَقَدم", "إصلاح المشكلات التي أعلن عنها في متصفح إنترنت إكسبلورر.", "بق", "قواطع الإفراج", "أي", 2.5, "جانيت Leverling", "../content/images/kanban/3.png", 4));
            Task.Add(new Tasks(5, "Testing", "إصلاح المشكلات التي أبلغ عنها العملاء.", "بق", "منخفض", "زبون", 3.5, "ستيفن ووكر", "../content/images/kanban/5.png", 1));
            Task.Add(new Tasks(6, "Close", " ترتيب شبكة لقاء مع زبون للحصول على صفحة تسجيل الدخول المتطلبات.", "آخرون", "منخفض", "لقاء", 2, "مايكل أسعد", "../content/images/kanban/6.png", 1));
            Task.Add(new Tasks(7, "Validate", " تحقق المتطلبات الجديدة تحقق المتطلبات الجديدة", " تحسين", "منخفض", " التحقق من صحة", 1.5, "روبرت الملك", "../content/images/kanban/7.png", 5));
            Task.Add(new Tasks(8, "Close", " التحقق من صحة الصفحة الدخول", " قصة", " قواطع الإفراج", " التحقق من صحة,حل", 2.5, "لورا كالاهان", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(9, "Testing", "إصلاح المشكلات التي أعلن عنها في متصفح سفاري.", "بق", "قواطع الإفراج", "حل, رحلات السفاري", 1.5, "Davolio  نانسي", "../content/images/kanban/1.png", 2));
            Task.Add(new Tasks(10, "Close", "Test the application in the أي browser.", " قصة", "منخفض", "تجريب,أي", 5.5, " مارغريت Hamilton", "../content/images/kanban/4.png", 3));
            Task.Add(new Tasks(11, "Validate", "التحقق من صحة the issues reported by the  زبون.", " قصة", "عالي", " التحقق من صحة,حل", 1, "ستيفن ووكر", "../content/images/kanban/5.png", 6));
            Task.Add(new Tasks(12, "Testing", "Check Login page  التحقق من صحة.", " قصة", "قواطع الإفراج", "تجريب", 0.5, "مايكل أسعد", "../content/images/kanban/6.png", 3));
            Task.Add(new Tasks(13, "Open", " تحسينات API.", " تحسين", "عالي", "شبكة,API", 3.5, " روبرت الملك", "../content/images/kanban/7.png", 3));
            Task.Add(new Tasks(14, "InProgress", " إضافة دعم استجابة لطلب.", "الملحمي", "حرج", "Responsive", 6, "لورا كالاهان", "../content/images/kanban/8.png", 2));
            Task.Add(new Tasks(15, "Open", " عرض البيانات التي تم استردادها من الملقم في مراقبة الشبكة.", " قصة", "عالي", " قاعدة البيانات,SQL", 5.5, " مارغريت Hamilton", "../content/images/kanban/4.png", 4));
            this.Kanban.DataSource = Task;
            this.Kanban.DataBind();
        }

{% endhighlight  %}

{% endtabs %}

The following output is displayed as a result of the above code example.

![ASPNET Kanban Localization image2](Localization_images/Localization_img2.png)