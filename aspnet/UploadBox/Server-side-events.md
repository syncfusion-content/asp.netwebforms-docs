---
layout: post
title: Server-side-events
description: server side events
platform: aspnet
control: UploadBox
documentation: ug
---

## Server side events

<table>
<tr>
<td>
Event Names</td><td>
Description</td><td>
Parameters</td></tr>
<tr>
<td>
OnComplete</td><td>
Event triggered when the file upload is completed</td><td>
(Object Sender, UploadBoxCompleteEventArgs e)Values passed in argument are as below,Size - to get the file sizeName - returns uploaded file nameExtension - to get the uploaded file extensionEventType - returns the event nameFileStatus - to get the dictionary value of Size, Name, Extension and RawFile</td></tr>
<tr>
<td>
OnErrorFile</td><td>
Event triggered when the file upload is returned with an error without uploading it</td><td>
(Object Sender, UploadBoxErrorFileEventArgs e)Values passed in argument are as below,Size - to get the file sizeName - returns uploaded file nameExtension - to get the uploaded file extensionEventType - returns the event nameArguments - to get the dictionary value of action, errors and file detailsAction – returns the current upload action </td></tr>
<tr>
<td>
OnRemoveFile</td><td>
Event triggered when a uploaded file is removed </td><td>
(Object Sender, UploadBoxErrorFileEventArgs e)Values passed in argument are as below,Size - to get the file sizeName - returns uploaded file nameExtension - to get the uploaded file extensionEventType - returns the event nameFileStatus - to get the dictionary value of Size, Name, Extension and RawFile</td></tr>
</table>
The following steps explain the configuration of the Server side events in UploadBox. 

In the ASPX page, add the UploadBox element.

{% highlight html %}



<ej:UploadBox ID="Uploadbox" runat="server" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx" OnComplete="Uploadbox_Complete" OnErrorFile="Uploadbox_ErrorFile" OnRemoveFile="Uploadbox_RemoveFile"></ej:UploadBox>



{% endhighlight %}

> _Note: The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section)._

Define the corresponding server side handlers in code behind

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



