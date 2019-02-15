---
layout: post
title:  Format String | PivotGrid | ASP.NET | Syncfusion
description: format string
platform: aspnet
control: PivotGrid
documentation: ug
---

### Format Strings

I> This feature is applicable only for Relational data source at Client Mode.

Formatted numeric values like n (number with decimal points), c (currency or accounting) and p (percentage) can be displayed with desired decimal places using `FormatString` option.

>**Note**: This is applicable only when the `Format` option is set.

{% highlight js %}

<ej:PivotGrid ID="PivotGrid1" Url="" runat="server" ClientIDMode="Static">
    <DataSource>
        <Rows>
            <ej:Field FieldName="Country" FieldCaption="Country"></ej:Field>
            <ej:Field FieldName="State" FieldCaption="State"></ej:Field>
        </Rows>
        <Columns>
            <ej:Field FieldName="Product" FieldCaption="Product"></ej:Field>
        </Columns>
        <Values>
            <ej:Field FieldName="Amount" FieldCaption="Amount" Format="currency" FormatString="{0:c0}"></ej:Field>
        </Values>
    </DataSource>
    <ClientSideEvents Load="onLoad" />

</ej:PivotGrid>

<script type="text/javascript">
        function onLoad(args) {
            args.model.dataSource.data = pivot_dataset; // Datasource
        }
</script>

{% endhighlight %}

![Format string support in ASP NET pivot grid contrtol](Number-Format_images/formatstring.png)

The following table describes the result of applying some commonly used format strings on numeric values.

<table>
<tr>
<td><b>Label Value</b></td>
<td><b>Label Format property value</b></td>
<td><b>Result </b></td>
<td><b>Description </b></td>
</tr>
<tr>
<td>1000</td>
<td>n1</td>
<td>1000.0</td>
<td>The Number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n2</td>
<td>1000.00</td>
<td>The Number is rounded to 2 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>n3</td>
<td>1000.000</td>
<td>The Number is rounded to 3 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p1</td>
<td>1.0%</td>
<td>The Number is converted to percentage with 1 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p2</td>
<td>1.00%</td>
<td>The Number is converted to percentage with 2 decimal place</td>
</tr>
<tr>
<td>0.01</td>
<td>p3</td>
<td>1.000%</td>
<td>The Number is converted to percentage with 3 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c1</td>
<td>$1,000.0</td>
<td>The Currency symbol is appended to number and number is rounded to 1 decimal place</td>
</tr>
<tr>
<td>1000</td>
<td>c2</td>
<td>$1,000.00</td>
<td>The Currency symbol is appended to number and number is rounded to 2 decimal place</td>
</tr>
<tr>
<td>1.0</td>
<td>d2</td>
<td>01</td>
<td>The number is rounded with 2 whole number place</td>
</tr>
<tr>
<td>1.0</td>
<td>d3</td>
<td>001</td>
<td>The number is rounded with 3 whole number place</td>
</tr>
</table>

The following table describes some common results on applying standard format sets to date format using `FormatString` option.

<table>
<tr>
<th>
Format Pattern </th><th>
Description </th><th>
Result</th></tr>
<tr>
<td>
d<br/><br/></td><td>
The day of the month between 1 and 31.  <br/><br/></td><td>
"1"  to "31"<br/><br/></td></tr>
<tr>
<td>
dd<br/><br/></td><td>
The day of the month with leading zero if required.<br/><br/></td><td>
"01" to "31"<br/><br/></td></tr>
<tr>
<td>
ddd<br/><br/></td><td>
Abbreviated day name.<br/><br/></td><td>
"Mon" to "Sun"<br/><br/></td></tr>
<tr>
<td>
dddd<br/><br/></td><td>
The full day name<br/><br/></td><td>
"Monday" to "Sunday"<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
M<br/><br/></td><td>
The month of the year between 1 - 12<br/><br/></td><td>
"1" to "12"<br/><br/></td></tr>
<tr>
<td>
MM<br/><br/></td><td>
The month of the year with leading zero if required<br/><br/></td><td>
"01" to "12"<br/><br/></td></tr>
<tr>
<td>
MMM<br/><br/></td><td>
Abbreviated month name<br/><br/></td><td>
"Jan" to "Dec"<br/><br/></td></tr>
<tr>
<td>
MMMM<br/><br/></td><td>
The full month name<br/><br/></td><td>
"January" to "December"<br/><br/></td></tr>
<tr>
<td>
<br/><br/></td><td>
<br/><br/></td><td>
<br/><br/></td></tr>
<tr>
<td>
yy<br/><br/></td><td>
The year as a two-digit number<br/><br/></td><td>
"99" or "08"<br/><br/></td></tr>
<tr>
<td>
yyyy<br/><br/></td><td>
The full four digit year<br/><br/></td><td>
"1999" or "2008"<br/><br/></td></tr>
<tr>
<td>
MM/dd/yyyy<br/><br/></td><td>
The Date is displayed in "month/date/year" format<br/><br/></td><td>
"04/09/1900"<br/><br/></td></tr>
<tr>
<td>
d M, y<br/><br/></td><td>
The Date is displayed in "date month, year" format<br/><br/></td><td>
"7 9, 0"<br/><br/></td></tr>
<tr>
<td>
d MM, y<br/><br/></td><td>
The Date is displayed in "date month, year" format<br/><br/></td><td>
"7 09, 0"<br/><br/></td></tr>
<tr>
<td>
dddd, d MMMM, yy<br/><br/></td><td>
The Date is displayed in "day, date month, year" format<br/><br/></td><td>
"Tuesday, 7 September, 00"<br/><br/></td></tr>
<tr>
<td>
yyyy-MM-dd<br/><br/></td><td>
The Date is displayed in "year-month-date"(UTC) format<br/><br/></td><td>
"1900-09-06"<br/><br/></td></tr>
</table>