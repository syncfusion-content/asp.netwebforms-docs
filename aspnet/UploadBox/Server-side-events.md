---
layout: post
title: Server side events | UploadBox | ASP.NET | Syncfusion
description: server side events
platform: aspnet
control: UploadBox
documentation: ug
---

# Server side events

<table>
<tr>
<th>
Event Names</th><th>
Description</th><th>
Parameters</th></tr>
<tr>
<td>
OnComplete</td><td>
Event triggered when the file upload is completed</td><td>
(Object Sender, UploadBoxCompleteEventArgs e)Values passed in argument are as below,<br/><br/>
Size - to get the file size<br/><br/>
Name - returns uploaded file name<br/><br/>
Extension - to get the uploaded file extension<br/><br/>
EventType - returns the event name<br/><br/>
FileStatus - to get the dictionary value of Size, Name, Extension and RawFile<br/><br/>
</td></tr>
<tr>
<td>
OnErrorFile</td><td>
Event triggered when the file upload is returned with an error without uploading it</td><td>
(Object Sender, UploadBoxErrorFileEventArgs e)Values passed in argument are as below,<br/><br/>
Size - to get the file size<br/><br/>
Name - returns uploaded file name<br/><br/>
Extension - to get the uploaded file extension<br/><br/>
EventType - returns the event name<br/><br/>
Arguments - to get the dictionary value of action, errors and file details<br/><br/>
Action – returns the current upload action <br/><br/>
</td></tr>
<tr>
<td>
OnRemoveFile</td><td>
Event triggered when a uploaded file is removed </td><td>
(Object Sender, UploadBoxErrorFileEventArgs e)Values passed in argument are as below,
Size - to get the file size<br/><br/>
Name - returns uploaded file name<br/><br/>
Extension - to get the uploaded file extension<br/><br/>
EventType - returns the event name<br/><br/>
FileStatus - to get the dictionary value of Size, Name, Extension and RawFile<br/><br/>
</td></tr>
</table>

The following steps explain the configuration of the Server side events in UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}

<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" OnComplete="Uploadbox_Complete" OnErrorFile="Uploadbox_ErrorFile" OnRemoveFile="Uploadbox_RemoveFile"></ej:UploadBox>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

### Define the corresponding server side handlers in code behind

{% highlight c# %}

protected void Uploadbox_Complete(object sender, Syncfusion.JavaScript.Web.UploadBoxCompleteEventArgs e)

{

    //e.Size - Gets the file size

    //e.Name - Returns uploaded file name

    //e.Extension - Gets the uploaded file extension

    //e.EventType - Returns the event name

    //e.FileStatus - Gets the dictionary value of Size, Name, Extension and RawFile

}

protected void Uploadbox_ErrorFile(object sender, Syncfusion.JavaScript.Web.UploadBoxErrorFileEventArgs e)

{
    //e.Size - Gets the file size

    //e.Name - Returns uploaded file name

    //e.Extension - Gets the uploaded file extension

    //e.EventType - Returns the event name

    //e.Arguments - Gets the dictionary value of action, errors and file details

    //e.Action – Returns the current upload action 

}

protected void Uploadbox_RemoveFile(object sender, Syncfusion.JavaScript.Web.UploadBoxRemoveFileEventArgs e)

{
    //e.Size - Gets the file size

    //e.Name - Returns uploaded file name

    //e.Extension - Gets the uploaded file extension

    //e.EventType - Returns the event name

    //e.FileStatus - Gets the dictionary value of Size, Name, Extension and RawFile

}

{% endhighlight %}