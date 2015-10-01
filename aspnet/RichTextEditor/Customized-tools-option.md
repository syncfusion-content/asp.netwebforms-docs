---
layout: post
title: Customized tools option | RichTextEditor | ASP.NET Webforms | Syncfusion
description: customized tools option
platform: aspnet
control: RichTextEditor
documentation: ug
---

# Customized tools option

## Add the tool item

In Rich Text Editor, toolbars are customizable. When you want to include a new tool item with new functionality that is not available in the existing RTE toolbar items, it is possible to create a new tool item by using the custom tool option. The following example illustrates how to insert an HTML, JavaScript, or CSS code in the editing area as a code block. 

Add the following code in your ASPX page to render RTE with new tool item.



{% highlight html %}



<ej:RTE ID="rteSample" AllowEditing="true" ToolsList="customTool" runat="server">

    <Tools>

        <CustomTool>

            <ej:CustomTool Action="showDialog" Css="codeInsert" Name="codeInsert" Tooltip="Insert code snippets" />

        </CustomTool>

    </Tools>

</ej:RTE>



<div id="TargetList">

    <ul>

        <li>Java Script</li>

        <li>HTML</li>

        <li>CSS</li>

    </ul>

</div>



<ej:Dialog ID="customSourceCode" Title="Paste you code and inset to RTE" ShowOnInit="false" EnableModal="true" Width="596" EnableResize="false" runat="server">

    <DialogContent>

        <table>

            <tr>

                <td style="width: 100px">Select type :</td>

                <td>

                    <div>

                        <ej:DropDownList ID="languageList" TargetID="TargetList" SelectedItemIndex="0" runat="server" />

                    </div>

                </td>

            </tr>

            <tr>

                <td colspan="2">

                    <textarea id="srcCode" style="width: 550px; height: 250px" rows="4"></textarea>

                </td>

            </tr>

            <tr>

                <td colspan="2">

                    <div class="e-rte-button e-fieldseparate">

                        <ej:Button ID="insert" Type="Button" Text="Insert" runat="server" ClientSideOnClick="customBtnClick"></ej:Button>

                        <ej:Button ID="cancel" Type="Button" Text="Cancel" runat="server" ClientSideOnClick="customBtnClick"></ej:Button>

                    </div>

                </td>

            </tr>

        </table>

    </DialogContent>

</ej:Dialog>





{% endhighlight %}



To Add Custom Toolbar to the RTE control, you have to include Syncfusion.JavaScript.Models namespace in your web.cofig file under &lt;system.web&gt; section

{% highlight xml %}

<system.web>

    <pages>

      <controls>

        <add  namespace="Syncfusion.JavaScript.Models, Version=XX.XXXX.X.XX, Culture=neutral, PublicKeyToken=3D67ED1F87D44C89" assembly="Syncfusion.EJ" tagPrefix="ej"/>

      </controls>

    </pages>

  </system.web>



{% endhighlight %}



Add the following code example to define the CustomTool action in script section

{% highlight js %}



    var rteObj;

    function showDialog() {

            $("#srcCode").val("").show();

            $("#<%=customSourceCode.ClientID%>").ejDialog("open");

    }

    function customBtnClick() {

        rteObj = $("#<%=rteSample.ClientID%>").data("ejRTE");

        if (this._id == "<%=customSourceCode.ClientID%>_insert") {

            rteObj.executeCommand("inserthtml", $("#srcCode")[0].value);

        }

        $("#<%=customSourceCode.ClientID%>").ejDialog("close");

    }





{% endhighlight %}



The following screenshot demonstrates the functionality of new tool item.



![](Customized-tools-option_images/Customized-tools-option_img1.png)



## Remove the tool item

In some cases you may have to remove a particular item from existing toolbar item of RTE. It can easily be done by using the property removeToolBarItem in RTE. Consider a content blog that does not require "insert table" option. In that case, you can remove the “CreateTable” tool item from the toolbar. The following code illustrates how to remove the “CreateTable” tool item from list of toolbars.

Add the following code in your ASPX page.



{% highlight html %}



<ej:RTE ID="rteSample" Width="850" runat="server"></ej:RTE>





{% endhighlight %}



Add the following code in script section.

{% highlight js %}



    $("#<%=rteSample.ClientID %>").ejRTE();

    var rteeObj = $("#<%=rteSample.ClientID %>").data("ejRTE");

    rteeObj.removeToolbarItem("<%=rteSample.ClientID %>createTable"); // remove toolbar item





{% endhighlight %}



![](Customized-tools-option_images/Customized-tools-option_img2.png)



## Enable or disable

You can enable or disable the tool items that are available in the RTE toolbar. Intermittently, it is not possible to allow some tool item actions in the editing area. To avoid mistakes in such a situation, you can disable the unnecessary tool items. Later, you can enable the disabled tool items, and when you are not going to use images in your blog you can disable the image tool item by using the “disableToolbarItem” method. The following example illustrates how to disable the “image” tool.

Add the following code in your ASPX page.

{% highlight html %}



<ej:RTE ID="rteSample" Width="850" runat="server">



{% endhighlight %}



Add the following code in script section.

{% highlight js %}



    var rteobj;

    $("#<%=rteSample.ClientID %>").ejRTE();

rteobj = $("#<%=rteSample.ClientID %>").data("ejRTE");

    //Here the Insert image toolbar icon is disabled

rteobj.disableToolbarItem("<%=rteSample.ClientID%>image");





{% endhighlight %}



![](Customized-tools-option_images/Customized-tools-option_img3.png)



Showcase for disable the insert image in toolbar
{:.caption} 

