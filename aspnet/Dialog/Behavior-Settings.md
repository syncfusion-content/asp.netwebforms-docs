---
layout: post
title: Behavior-Settings
description: behavior settings 
platform: aspnet
control: Dialog
documentation: ug
---

# Behavior Settings 

## Resize Support

The Dialog control can be resized by using this feature. You can resize the Dialog by dragging the bottom right corner area. EnableResize accepts Boolean value. 

### Enable Resize Option

The following steps explain the implementation of resize option in the Dialog control. 

In the ASPX page, add the Dialog control and set the EnableResize as true. 

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" EnableResize="true" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}



The output of the Dialog control when EnableResize is true.                                  

![](Behavior-Settings_images/Behavior-Settings_img1.png) 



## Drag Support

The Dialog control supports the drag function. You can click the Dialog header and drag the control anywhere in the web page.

### Allow Drag Option

The following steps explain the implementation of drag option in the Dialog control. 

In the ASPX page, add the Dialog control and set the AllowDraggable to true. 

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" AllowDraggable="true" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}

The output of Dialog control when AllowDraggable is true.                                         

![](Behavior-Settings_images/Behavior-Settings_img2.png) 



## Close Icon ToolTip Support

You can change the close icon ToolTip in the Dialog control by using the CloseIconTooltip property. The default value for CloseIconTooltip is close.

### Define Close Icon ToolTip

The following steps explain how to implement close icon ToolTip option in the Dialog control. 

In the ASPX page, add the Dialog control and set the CloseIconTooltip value as close.

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" CloseIconTooltip="close" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}



The output of Dialog control when CloseIconTooltip is close.



![](Behavior-Settings_images/Behavior-Settings_img3.png) 



## Persistence Support

The Dialog control supports state maintenance where you can maintain the state of the Dialog control in the web page. The default value for EnablePersistence is false.

## Enable Persistence Option

The following steps explain the implementation of persistence support in the Dialog control. 

In the ASPX page, add the Dialog control and set the EnablePersistence as true.

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" EnablePersistence="true" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}

You can resize and reload the web page. The state is maintained in the Dialog control. The following is the output when EnablePersistence is true. 



![](Behavior-Settings_images/Behavior-Settings_img4.png) 



## Enabled or Disabled

The Dialog control supports enabled and disabled options that allow you to enable or disable the Dialog control in the web page.

### Enable Dialog Control

The following steps explain how to implement the enable option in the Dialog control. 

In the ASPX page, add the Dialog control and set Enabled to true.

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" Enabled="true" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}



The output of the Dialog control when Enabled is true.          

![](Behavior-Settings_images/Behavior-Settings_img5.png) 



### Disable Dialog Control

The following steps explain the implementation of disable option in the Dialog control. 

In the ASPX page, add the Dialog control and set Enabled to false.

{% highlight html %}



<ej:Dialog ID="dialog" runat="server" Width="300" Height="200" Enabled="false" Title="Syncfusion Dialog">

    <DialogContent>       

        <div>

            The Syncfusion Dialog control is rendered.

        </div>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}



The following is the output when Enabled is set to false.            

![](Behavior-Settings_images/Behavior-Settings_img6.png) 



## Dialog Position

The Dialog provides the option to place the control based on its X axis and Y axis positions in the web page. The following steps explain how to position the Dialog.

In the ASPX page, add the Dialog control and set Position values.

{% highlight html %}



    <ej:Dialog ID="dialog" runat="server" Width="300" Height="200" Title="Syncfusion Dialog">

<Position XValue="20" YValue="26" />

        <DialogContent>

            <div>

                The Syncfusion Dialog control is rendered.<br />

                Position

              <br />

                X-Axis : 20

              <br />

                Y-Axis : 26

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}



The output of the Dialog control after setting X axis and Y axis values.

![](Behavior-Settings_images/Behavior-Settings_img7.png) 



## Header Option

You can show or hide the Dialog header by setting the ShowHeader property. The following steps explains how to set the header option.

### Show Header

In the ASPX page, add the Dialog control and set the ShowHeader to true.

{% highlight html %}



    <ej:Dialog ID="dialog" runat="server" Width="300" Height="200" ShowHeader="true" Title="Syncfusion Dialog">

        <DialogContent>

            <div>

                The Syncfusion Dialog control is rendered.               

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}



The following screenshot displays the Dialog control when ShowHeader is true.

![](Behavior-Settings_images/Behavior-Settings_img8.png) 



### Hide Header

In the ASPX page, add the Dialog control and set the ShowHeader to false.

{% highlight html %}



    <ej:Dialog ID="dialog" runat="server" Width="300" Height="200" ShowHeader="false" Title="Syncfusion Dialog">

        <DialogContent>

            <div>

                The Syncfusion Dialog control is rendered.               

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}



The following screenshot displays the Dialog control when ShowHeader is set to false.

![C:/Users/ApoorvahR/Desktop/9.png](Behavior-Settings_images/Behavior-Settings_img9.png) 







## Show at Initial

The Dialog control contains an option to be visible or hidden at initialization. The default value for ShowOnInit is true. Setting it to false hides the dialog control at initialization.

In the ASPX page, add the Dialog control and set the ShowOnInit to true.

{% highlight html %}



    <ej:Dialog ID="dialog" runat="server" Width="300" Height="200" ShowOnInit="true" Title="Syncfusion Dialog">

        <DialogContent>

            <div>

                The Syncfusion Dialog control is rendered.               

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}

The output when ShowOnInit is set to true.

![](Behavior-Settings_images/Behavior-Settings_img10.png) 



## Rounded Corner Support

The Dialog supports rounded corners. The default value for ShowRoundedCorner is false. 

In the ASPX page, add the Dialog control and set the ShowRoundedCorner to true.

{% highlight html %}



    <ej:Dialog ID="dialog" runat="server" Width="300" Height="200" ShowRoundedCorner="true" Title="Syncfusion Dialog">

        <DialogContent>

            <div>

                The Syncfusion Dialog control is rendered.               

            </div>

        </DialogContent>

    </ej:Dialog>





{% endhighlight %}



The output of Dialog control when ShowRoundedCorner is true.



![](Behavior-Settings_images/Behavior-Settings_img11.png) 



