---
layout: post
title: Getting Started | TimePicker | ASP.NET | Syncfusion
description: getting started
platform: aspnet
control: TimePicker
documentation: ug
---

# Getting Started

This section explains briefly how to create a TimePicker in your application with ASP.NET.

## Create your first TimePicker in ASP.NET

The Essential ASP.NET TimePicker provides support to display a TimePicker in your web page and allows you to pick a time from the given TimePicker. Here, you can learn how to customize two dates and TimePickers in a real-time hotel table booking application. 

The following screenshot illustrates the functionality of a TimePicker with a time range of morning to evening. You can select a time to book a table, from a period of 9.00 AM to 6.00 PM for the current day. This avoids selecting a time prior to the morning.

![](Getting-Started_images/Getting-Started_img1.png) 

### Create a TimePicker 

You can create an ASP.NET Web Forms Project and add necessary assemblies and scripts with the help of the given [ASP.NET Web Forms-Getting Started](https://help.syncfusion.com/aspnet/getting-started) Documentation.



Add the following code to the corresponding ASPX page to render the TimePicker.

{% highlight html %}

    <table>
        <tr>
            <td class="table-data">
                Select date
            </td>
            <td class="table-data">
                Select time
            </td>
            <td class="table-data">
                Select party size
            </td>
        </tr>
        <tr>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:DatePicker ID="DatePicker" runat="server" />
                </span>
            </td>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:TimePicker ID="TimePicker" runat="server" />
                </span>
            </td>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:DropDownList name="party_size" ID="DropDownList" SelectedItemIndex="0" runat="server">
                        <Items>
                            <ej:DropDownListItem Text="select people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="5 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="10 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="15 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="20 people">
                            </ej:DropDownListItem>
                        </Items>
                    </ej:DropDownList>
                </span>
            </td>
        </tr>
        <tr>
            <td class="table-data">
                <ej:Button ID="Book" Type="Button" Text="Book" ClientSideOnClick="acknowledge" runat="server">
                </ej:Button>
            </td>
        </tr>
    </table>

{% endhighlight %}

Add the following styles to show the TimePicker control.

{% highlight css %}

.e-table-data
{
	width: 200px;
	font-weight: bold;
}
.inner-datepicker
{
	display: inline-block;
}

{% endhighlight %}

The following screenshot displays the TimePicker control.


![](Getting-Started_images/Getting-Started_img2.png) 


### Set the Min and Max Values

In a real-time hotel table booking scenario, the booking is open only for a limited time and limited number of days. You have to select a time and date from the given range. This is achieved by using the properties **MinTime** and **MaxTime**, **MinDate** and **MaxDate**. By this way, times ranging between MinTime and MaxTime, MinDate and MaxDate are enabled in the TimePicker.

{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
	DatePicker.MinDate = DateTime.Now.ToString();
	DatePicker.MaxDate = DateTime.Now.AddDays(30).ToString();
	TimePicker.MinTime = "9:00:00";
	TimePicker.MaxTime = "18:00:00";
}

{% endhighlight %}



The above code example displays the following output.

![](Getting-Started_images/Getting-Started_img3.png) 



### Set Time Interval

You can select the Time in the TimePicker with the interval of one hour. You need to set the property Interval as 60.

The following code example shows how to set Time interval.

{% highlight html %}

<ej:TimePicker ID="TimePicker1" runat="server" Interval="60" />

{% endhighlight %}



Run the above code to achieve the desired result. You can select the date and time in the TimePicker within the given range of one hour interval. This scenario is illustrated in the following screenshot.

![](Getting-Started_images/Getting-Started_img4.png) 



### Display the Acknowledgment Message

The acknowledgment message is displayed when you click the Book button.

The following code example shows how to display the acknowledgment message.

{% highlight js %}

<script type="text/javascript">
        function acknowledge() {
            var a = $('#DatePicker').val();
            var b = $('#TimePicker').val();
            var c = $('#DropDownList').val();
            alert("You are booked the table with date " + a + " time " + b + " Party_size is " + c);
        }
</script>

{% endhighlight %}

The following screenshot displays the acknowledgment message.

![](Getting-Started_images/Getting-Started_img5.png) 

### Create Two TimePickers

You can select the Start time in the first TimePicker and then the End time in the second TimePicker. The validation process is done after the selection of Start time and the changes are reflected in the End time selection TimePicker. You can manipulate this process in the Select event of Start Time selection TimePicker. 

Add input element to render Two TimePickers.

{% highlight html %}

<table>
        <tr>
            <td class="table-data">
                Select Date
            </td>
            <td class="table-data">
                Select start time
            </td>
            <td class="table-data">
                Select end time
            </td>
            <td class="table-data">
                Select party size
            </td>
        </tr>
        <tr>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:DatePicker ID="DatePicker" runat="server" />
                </span>
            </td>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:TimePicker ID="TimePicker" ClientSideOnSelect="selectedStartTime" MinTime="9:00:00"
                        MaxTime="18:00:00" Interval="60" runat="server" />
                </span>
            </td>
            <td class="table-data">
                <span class="inner-datepicker">
                    <ej:TimePicker ID="TimePickerEnd" MinTime="9:00:00" MaxTime="18:00:00" Interval="60"
                        runat="server" />
                </span>
            </td>
            <td class="table-data">
               <span class="inner-datepicker">
                    <ej:DropDownList name="party_size" ID="DropDownList" SelectedItemIndex="0" runat="server">
                        <Items>
                            <ej:DropDownListItem Text="select people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="5 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="10 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="15 people">
                            </ej:DropDownListItem>
                            <ej:DropDownListItem Text="20 people">
                            </ej:DropDownListItem>
                        </Items>
                    </ej:DropDownList>
               </span>
            </td>
        </tr>
        <tr>
            <td class="table-data">
                <ej:Button ID="Book" Type="Button" Text="Book" ClientSideOnClick="acknowledge" runat="server">
               </ej:Button>
            </td>
            <td>
            </td>
            <td class="table-data">
            </td>
            <td class="table-data">
            </td>
        </tr>
   </table>

{% endhighlight %}



Display the acknowledge message by using following script.

{% highlight js %}

<script type="text/javascript">
	function acknowledge() {
		var a = $('#DatePicker').val();
		var b = $('#TimePicker').val();
		var c = $('#DropDownList').val();
		alert("You are booked the table with date " + a + " time " + b + " Party_size is " + c);
	}
	function selectedStartTime(sender) {
		var selDate = sender.value; // mentions the selected time.
		minTimepicker = $("#TimePickerEnd").data("ejTimePicker"); // creating TimePicker object
		minTimepicker.setModel({ "minTime": selDate }); // setting minTime property through setModel of TimePicker object.
	}
</script>

{% endhighlight %}

Run the above code to achieve the desired result. By selecting the Start Time in the first TimePicker, you can select the End Time within the given range. This restricts you from selecting false time. This scenario is illustrated in the following screenshot.

![](Getting-Started_images/Getting-Started_img6.png) 

You can also add additional functionalities such as localization and time formats to the TimePicker. 



