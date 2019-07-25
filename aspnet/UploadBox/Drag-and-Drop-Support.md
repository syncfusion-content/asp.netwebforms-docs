---
layout: post
title: Drag and Drop Support | UploadBox | ASP.NET | Syncfusion
description: drag and drop support
platform: aspnet
control: UploadBox
documentation: ug
---

# Drag and Drop Support

The UploadBox control provides the drag and drop support. You can simply drag-and-drop files, directly from the computer to the droppable area. A list of files can be dragged and dropped when you enable the MultipleFilesSelection.

The following screenshot displays the drag and drop support.

 ![Drag and Drop](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img1.png)



## Enable drag and drop 

You can enable or disable drag and drop by using the AllowDragAndDrop property. By default, the AllowDragAndDrop property is set to false in the UploadBox control. You can enable drag and drop by setting the AllowDragAndDrop property to true. When you want to drag and drop multiple files, you can enable multiple file selection by setting MultipleFilesSelection to true in the UploadBox control.

The following steps explain how to enable drag and drop in the UploadBox control.

In the ASPX page, configure element UploadBox element to enable the drag and drop in the UploadBox control.

{% highlight html %}

<div class="frame">

    <div class="control">

        <ej:UploadBox ID="UploadBox1" runat="server" AllowDragAndDrop="true" MultipleFilesSelection="true" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx">

        </ej:UploadBox>

    </div>

</div>

{% endhighlight %}

N> The SaveUrl and RemoveUrl are the same as above (see Save File Action and Remove File Action section).

In CSS, configure the custom styles for drag and drop.

{% highlight css %}

.frame {

    width: 500px;

    height: 100px;

    margin-top: 10%;

}



.control {

    width: 100%;

    height: 100%;

}

{% endhighlight %}



The following screenshot displays the output for the above code.

 ![Dragged file uploaded](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img2.png)



## Drag Area text

You can change the drag area text by using the DragAreaText property.  By default, the DragAreaText (string) property is Drop files or click to upload in the UploadBox control.

In the ASPX page, configure UploadBox element to enable the drag and drop in the UploadBox control.


{% highlight html %}

<div class="frame">

    <div class="control">

        <ej:UploadBox ID="UploadBox1" runat="server" AllowDragAndDrop="true" DragAreaText="Drop files here" MultipleFilesSelection="true"

            SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx">

        </ej:UploadBox>

    </div>

</div>

{% endhighlight %}



In CSS, configure the custom styles for drag and drop.

{% highlight css %}

.frame

{

    width: 500px;

    height: 100px;

    margin-top: 10%;

}



.control

{

    width: 100%;

    height: 100%;

}

{% endhighlight %}



 The following screenshot displays the output for the above code.

 ![Drag Area text](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img3.png)



## Adjust Drop area size

The UploadBox control provides the ability to change or adjust the drop area size. The DropAreaHeight andDropAreaWidth properties in the UploadBox control allow you to set the maximum height and maximum width for the drop area. The value set to this property is string or number type.

The following steps explain how to adjust the Drop Area Size.

In the ASPX page, configure UploadBox element to enable the drag and drop in the UploadBox control.

{% highlight html %}

<ej:UploadBox ID="UploadBox1" runat="server" AllowDragAndDrop="true" MultipleFilesSelection="true" DropAreaHeight="300px" DropAreaWidth="600px" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx">

</ej:UploadBox>

{% endhighlight %}

The following screenshot displays the output for the above code.

 ![Drop area size](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img4.png)



## Drop area with Browse button behavior

You can click anywhere in the droppable area to browse and upload the files. The droppable area behaves like a browse button.

### Droppable area behavior

Enable the AllowDragAndDrop property to achieve this feature. Next, set the ShowBrowseButton to false in the UploadBox control.

The following steps explains the droppable area containing the browse button behavior

In the ASPX page, configure UploadBox element to enable the drag and drop in the UploadBox control.



{% highlight html %}

<div class="frame">

    <div class="control">

        <ej:UploadBox ID="UploadBox1" runat="server" AllowDragAndDrop="true" DragAreaText="Drop files here for uploading" MultipleFilesSelection="true"

           ShowBrowseButton="false" SaveUrl="SaveFiles.ashx" RemoveUrl="RemoveFiles.ashx">

        </ej:UploadBox>

    </div>

</div>

{% endhighlight %}



In CSS, configure the custom styles for drag and drop.

{% highlight css %}

.frame

{

    width: 500px;

    height: 100px;

    margin-top: 10%;

}



.control

{

    width: 100%;

    height: 100%;

}

{% endhighlight %}



The following screenshot displays the output for the above code.



 ![Droppable area](Drag-and-Drop-Support_images/Drag-and-Drop-Support_img5.png)



