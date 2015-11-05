---
layout: post
title: Getting Started | Ribbon | ASP.NET Webforms | Syncfusion
description: getting started
platform: aspnet
control: Ribbon
documentation: ug
---

# Getting Started

This section explains briefly how to create a Ribbon in your application with ASP.NET.

## Create your Ribbon in ASP.NET

You can create a Ribbon with highly customizable look and feel. The Ribbon control displays the controls in multiple tabs. This section explains the ribbon tabs, adding controls to the groups, expand/collapse ribbon option, and the control separator.

![](Getting-Started_images/Getting-Started_img1.png)


1. Create a Syncfusion ASP.NET Web form application.
2. Drag and drop the Ribbon control in the Index.aspx page from the toolbox.

   ![](Getting-Started_images/Getting-Started_img2.png)


## Application Tabs

Application menu support has been provided in the ribbon control ApplicationTab. Use ApplicationTab tag to define the application tab with menu. In ApplicationTab attributes, Type property to define the ApplicationMenu and the value is ApplicationMenu,ItemID property to specify ID of the UL list for the application menu and the MenuSettings property to specify all the members and events of the menu.

 ![](Getting-Started_images/Getting-Started_img3.png)




{% highlight html %}





<ej:Ribbon ID="defaultRibbon" runat="server" Width="100%">

            <ApplicationTab MenuItemID="menu" Type="Menu">

                <MenuSettings OpenOnClick="false"></MenuSettings>

            </ApplicationTab>

            <RibbonTabs>

                <ej:RibbonTab Id="home" Text="HOME">

                    <TabGroupCollection>

                        <ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="HomeDiv" />

                    </TabGroupCollection>

                </ej:RibbonTab>

            </RibbonTabs>

        </ej:Ribbon>

    </div>

    <ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

            </ul>

        </li>

    </ul>

    <div id="HomeDiv">Ribbon Control</div>



{% endhighlight %}

The following screenshot illustrates Ribbon control with Application Tab.

![](Getting-Started_images/Getting-Started_img4.png)








## Contextual Tabs

You can add contextual tabs in the Ribbon control. Inside ContextualTabs tag use ContextualTab tag to add a single or set of contextual tabs. In the ContextualTab tag, use BackgroundColor property to apply background color to the contextual tabs. Use BorderColor property to apply border color to the contextualTab.

![](Getting-Started_images/Getting-Started_img5.png)




{% highlight html %}





<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

     <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%">

        <ApplicationTab MenuItemID="menu" Type="Menu">

           <MenuSettings OpenOnClick="false"></MenuSettings>

        </ApplicationTab>

     <RibbonTabs>

     <ej:RibbonTab Id="home" Text="HOME">

    <TabGroupCollection>        <ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="homeDiv">

</ej:TabGroup>

       </TabGroupCollection>

     </ej:RibbonTab>

     <ej:RibbonTab Id="calculator" Text="CALCULATOR">

       <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="calculate" />

       </TabGroupCollection>

    </RibbonTabs>

<ContextualTabs>

   <ej:ContextualTab BackgroundColor="#FCFBEB" BorderColor="#F2CC1C">

       <RibbonTabCollection >

         <ej:RibbonTab Id="design" Text="DESIGN">

            <TabGroupCollection>

               <ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="designing" />

              </TabGroupCollection>

          </ej:RibbonTab>

        </RibbonTabCollection >

    </ej:ContextualTab>

</ContextualTabs>

</ej:Ribbon>

</div>

    <ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

                <li><a>Save</a></li>

                <li><a>Save as</a></li>

                <li><a>Print</a></li>

            </ul>

        </li>

    </ul>

    <div id="homeDiv">Ribbon Control</div>

    <div id="calculate">Calculator</div>

    <div id="designing">Designing</div>

</asp:Content>



{% endhighlight %}



The following screenshot illustrates Ribbon control with Contextual tabs.

![](Getting-Started_images/Getting-Started_img6.png)


## Tabs

Tabs can be created by using RibbonTab property. In RibbonTab, define the TabGroupCollection property that allows you to create one or more TabGroups in the RibbonTab.

![](Getting-Started_images/Getting-Started_img7.png)


{% tabs %}

{% highlight html %}





<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

 <ej:Ribbon ID="defaultRibbon" runat="server" Width="500px">

   <ApplicationTab MenuItemID="menu" Type="Menu">

     <MenuSettings OpenOnClick="false"></MenuSettings>

   </ApplicationTab>

 <RibbonTabs>

   <ej:RibbonTab Id="home" Text="HOME">

    <TabGroupCollection>

     <ej:TabGroup Text="New" AlignType="Rows">

      <ContentCollection>

       <ej:TabContent>

        <ContentGroupCollection>          <ej:ContentGroup Id="new" Text="New" ToolTip="New" Type="Button">

<ButtonSettings Type="Reset" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-new" Click="executeAction" />

</ej:ContentGroup>

        </ContentGroupCollection>

        <ContentDefaults Width="60" Height="70" Type="Button" />

       </ej:TabContent>

      </ContentCollection>

     </ej:TabGroup>

    <ej:TabGroup Text="Font" AlignType="Rows">

   <ContentCollection>

  <ej:TabContent>

       <ContentDefaults Height="28" Type="DropDownList" />

       <ContentGroupCollection>

<ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">

<DropdownSettings Value="Segoe UI" Text="Fonts" Width="150" Select="executeAction"></DropdownSettings>

   </ej:ContentGroup>

<ej:ContentGroup Id="fontsize" ToolTip="FontSize" Type="DropDownList">

<DropdownSettings Value="1pt" Width="65" Select="executeAction"></DropdownSettings>

   </ej:ContentGroup>

   </ContentGroupCollection>

 </ej:TabContent>

  <ej:TabContent>

   <ContentGroupCollection>

<ej:ContentGroup Id="bold" Text="Bold" ToolTip="Bold">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon bold" Click="executeAction" />

  </ej:ContentGroup>

<ej:ContentGroup Id="italic" Text="Italic" ToolTip="Italic" EnableSeparator="true">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonitalic" Click="executeAction" />

  </ej:ContentGroup>

<ej:ContentGroup Id="underline" Text="Underline" ToolTip="Underline">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonunderline" Click="executeAction" />

  </ej:ContentGroup>                             

  </ContentGroupCollection>

       <ContentDefaults Type="Button" IsBig="false" />

   </ej:TabContent>

   </ContentCollection>

</ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="calculator" Text="CALCULATOR">

 <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="calculate" />                        

 </TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="design" Text="DESIGN">

    <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="designing" />                   

    </TabGroupCollection>

   </ej:RibbonTab>

  </RibbonTabs>

</ej:Ribbon>

</div>

<ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

                <li><a>Save</a></li>

                <li><a>Save as</a></li>

                <li><a>Print</a></li>

            </ul>

        </li>

</ul>

    <div id="calculate">Calculator</div>

    <div id="designing">Design</div>

</asp:Content>



{% endhighlight %}













{% highlight c# %}





protected void Page_Load(object sender, EventArgs e)

        {

         var fontlist = new List<string> { "Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica" };

          var fontsize = new List<string> { "1pt", "2pt", "3pt", "4pt", "5pt" };

         this.fontfamily.DropdownSettings.DataSource = fontlist;

         this.fontsize.DropdownSettings.DataSource = fontsize;}



{% endhighlight %}

{% endtabs %}

The following screenshot illustrates Ribbon with Tab Group Collections.

![](Getting-Started_images/Getting-Started_img8.png)


## Create Ribbon Control 

1. Create a Master file and add the following references to the required libraries. 

   ~~~ html

		<!doctype html>

		<html>

		<head>

		<meta name="viewport" content="width=device-width, initial-scale=1.0" charset="utf-8" />

		<!-- style sheet for default theme(flat azure) -->

		<link href="http://cdn.syncfusion.com/13.1.0.21/js/web/flat-azure/ej.web.all.min.css" rel="stylesheet" />

		<!--scripts-->

		<script src="[http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js](http://cdn.syncfusion.com/js/assets/external/jquery-1.10.2.min.js)"></script>

		<script src="[http://cdn.syncfusion.com/js/assets/external/jquery.globalize.js](http://cdn.syncfusion.com/js/assets/external/jquery.globalize.js)"> </script>

		<script src="[http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.js](http://cdn.syncfusion.com/js/assets/external/jquery.easing.1.3.js)">

		</script>

		<script src="http://cdn.syncfusion.com/13.1.0.21/js/web/ej.web.all.min.js"></script>

		</head>

		<body>

		</body>

		</html>

   ~~~

2. Add a Ribbon tag in the .aspx page as shown in the following code example.

   ~~~ html

		<%--..--%>

		<ej:Ribbon ID="defaultRibbon" runat="server" Width="100%"> </ej:Ribbon>

		<%--..--%>

   ~~~

3. Create the Ribbon control as follows. The Width property allows you to define the width to the ribbon. In applicationTab definition, the ItemID property allows you to specify the ID of the ul list to create the application menu. In RibbonTab, define the TabGroupCollection property that allows you to create one or more TabGroups in the RibbonTab. In contextual Tabs definition, the BackgroundColor property allows you to define the background color of the contextual tab and BorderColor property allows you to define the border color of the contextual tab.


   ~~~ html

		<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

		<div>

		     <ej:Ribbon ID="defaultRibbon" runat="server" Width="100%">

		        <ApplicationTab MenuItemID="menu" Type="Menu">

		           <MenuSettings OpenOnClick="false"></MenuSettings>

		        </ApplicationTab>

		     <RibbonTabs>

		     <ej:RibbonTab Id="home" Text="HOME">

		    <TabGroupCollection>        <ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="homediv">

		</ej:TabGroup>

			   </TabGroupCollection>

		     </ej:RibbonTab>

		     <ej:RibbonTab Id="calculator" Text="CALCULATOR">

		       <TabGroupCollection>

		<ej:TabGroup Text="Calculator" AlignType="Rows" Type="custom" ContentID="calculate" />

			   </TabGroupCollection>

			 </ej:RibbonTab>

		    </RibbonTabs>

		<ContextualTabs>

		   <ej:ContextualTab BackgroundColor="#FCFBEB" BorderColor="#F2CC1C">

		       <RibbonTabCollection >

		         <ej:RibbonTab Id="design" Text="DESIGN">

		            <TabGroupCollection>

		               <ej:TabGroup Text="Design" AlignType="Rows" Type="custom" ContentID="designing" />

		              </TabGroupCollection>

		          </ej:RibbonTab>

		        </RibbonTabCollection >

		    </ej:ContextualTab>

		</ContextualTabs>

		</ej:Ribbon>

		</div>

		    <ul id="menu">

		        <li><a>FILE</a>

		            <ul>

		                <li><a>New</a></li>

		                <li><a>Open</a></li>

		                <li><a>Save</a></li>

		                <li><a>Save as</a></li>

		                <li><a>Print</a></li>

		            </ul>

		        </li>

		    </ul>

		    <div id="homediv">Ribbon Control</div>

		    <div id="calculate">Calculator</div>

		    <div id="designing">Design</div></asp:Content>

   ~~~

4. The following screenshot illustrates the Ribbon control.

   ![](Getting-Started_images/Getting-Started_img9.png)

## Add Controls

Add controls to each Ribbon tab by using the tag ContentCollection. You can also add custom controls by using the property ContentID. The property AlignType is used to align the groups in row or column order.Button, Split button, DropdownLlist and Toggle button, Gallery, and Custom controls support have provided in the Ribbon control.The default AlignType is rows.

{% tabs %}

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

     <ej:Ribbon ID="defaultRibbon" runat="server" Width="500px">

     <ApplicationTab MenuItemID="menu" Type="Menu">

     <MenuSettings OpenOnClick="false"></MenuSettings>

     </ApplicationTab>

     <RibbonTabs>

        <ej:RibbonTab Id="home" Text="HOME">

     <TabGroupCollection>

     <ej:TabGroup Text="New" AlignType="Rows">

        <ContentCollection>

     <ej:TabContent>

     <ContentGroupCollection>

 <ej:ContentGroup Id="new" Text="New" ToolTip="New" Type="Button">

  <ButtonSettings Type="Reset" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-new" Click="executeAction" />

 </ej:ContentGroup>

     </ContentGroupCollection>

 <ContentDefaults Width="60" Height="70" Type="Button" />

     </ej:TabContent>

     </ContentCollection>

  </ej:TabGroup>

   <ej:TabGroup Text="Font" AlignType="Rows">

    <ContentCollection>

     <ej:TabContent>

    <ContentDefaults Height="28" Type="DropDownList" />

     <ContentGroupCollection>

 <ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">

<DropdownSettings Value="Segoe UI" Text="Fonts" Width="150" Select="executeAction"></DropdownSettings>

   </ej:ContentGroup>

  <ej:ContentGroup Id="fontsize" ToolTip="FontSize" Type="DropDownList">

<DropdownSettings Value="1pt" Width="65" Select="executeAction">

</DropdownSettings>

  </ej:ContentGroup>

   </ContentGroupCollection>

  </ej:TabContent>

  <ej:TabContent>

  <ContentGroupCollection>

  <ej:ContentGroup Id="bold" Text="Bold" ToolTip="Bold">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon bold" Click="executeAction" />

  </ej:ContentGroup>

    <ej:ContentGroup Id="italic" Text="Italic" ToolTip="Italic">

 <ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonitalic" Click="executeAction" />

   </ej:ContentGroup>

 </ContentGroupCollection>

   <ContentDefaults Type="Button" IsBig="false" />

    </ej:TabContent>

      </ContentCollection>

       </ej:TabGroup>

 <ej:TabGroup Text="CustomControls" AlignType="Rows" Type="custom" ContentID="Contents">

   <ContentCollection>

     <ej:TabContent>

        <ContentGroupCollection>

 <ej:ContentGroup Id="Customcontrol" Text="Bold" ToolTip="Custom">

 <ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-ribbon bold"  />

          </ej:ContentGroup>

         </ContentGroupCollection>

       <ContentDefaults Type="Button" IsBig="false" />

     </ej:TabContent>

   </ContentCollection>

 </ej:TabGroup>

 </TabGroupCollection>

 </ej:RibbonTab>

 <ej:RibbonTab Id="calculator" Text="CALCULATOR">

     <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="calculate" />                       

     </TabGroupCollection>

 </ej:RibbonTab>

   <ej:RibbonTab Id="design" Text="DESIGN">  

     <TabGroupCollection>

 <ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="designing" />                        

     </TabGroupCollection>

    </ej:RibbonTab>

   </RibbonTabs>

 </ej:Ribbon>

 </div>

    <ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

                <li><a>Save</a></li>

                <li><a>Save as</a></li>

                <li><a>Print</a></li>

            </ul>

        </li>

    </ul>

    <div id="Contents"><button id="custom">Custom Control</button></div>

</asp:Content>

{% endhighlight %}

{% highlight c# %}
protected void Page_Load(object sender, EventArgs e)

  {

     var fontlist = new List<string> { "Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica" };

     var fontsize = new List<string>() { "1pt", "2pt", "3pt", "4pt", "5pt" };

     this.fontfamily.DropdownSettings.DataSource = fontlist;

    this.fontsize.DropdownSettings.DataSource = fontsize;}

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates Ribbon with controls,

![](Getting-Started_images/Getting-Started_img10.png)


## Expand/Collapse

The expand/collapse support has been provided to the Ribbon.

The following screenshot illustrates Ribbon in the expanded state.

![](Getting-Started_images/Getting-Started_img11.png)


The following screenshot illustrates Ribbon in the collapsed state,

![](Getting-Started_images/Getting-Started_img12.png)


## Separator for Controls

The control Separator support is provided in the Ribbon control. Set EnableSeparator value to true to enable the separator after a control. Control Separator supports only row type group.

{% tabs %}

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div>

 <ej:Ribbon ID="defaultRibbon" runat="server" Width="500px">

   <ApplicationTab MenuItemID="menu" Type="Menu">

     <MenuSettings OpenOnClick="false"></MenuSettings>

   </ApplicationTab>

 <RibbonTabs>

   <ej:RibbonTab Id="home" Text="HOME">

    <TabGroupCollection>

     <ej:TabGroup Text="New" AlignType="Rows">

      <ContentCollection>

       <ej:TabContent>

        <ContentGroupCollection>

          <ej:ContentGroup Id="new" Text="New" ToolTip="New" Type="Button">

<ButtonSettings Type="Reset" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-new" Click="executeAction" />

</ej:ContentGroup>

        </ContentGroupCollection>

        <ContentDefaults Width="60" Height="70" Type="Button" />

       </ej:TabContent>

      </ContentCollection>

     </ej:TabGroup>

    <ej:TabGroup Text="Font" AlignType="Rows">

   <ContentCollection>

  <ej:TabContent>

       <ContentDefaults Height="28" Type="DropDownList" />

       <ContentGroupCollection>

<ej:ContentGroup Id="fontfamily" ToolTip="Font" Type="DropDownList">

<DropdownSettings Value="Segoe UI" Text="Fonts" Width="150" Select="executeAction"></DropdownSettings>

   </ej:ContentGroup>

<ej:ContentGroup Id="fontsize" ToolTip="FontSize" Type="DropDownList">

<DropdownSettings Value="1pt" Width="65" Select="executeAction"></DropdownSettings>

   </ej:ContentGroup>

   </ContentGroupCollection>

 </ej:TabContent>

  <ej:TabContent>

   <ContentGroupCollection>

<ej:ContentGroup Id="bold" Text="Bold" ToolTip="Bold">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon bold" Click="executeAction" />

  </ej:ContentGroup>

<ej:ContentGroup Id="italic" Text="Italic" ToolTip="Italic" EnableSeparator="true">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonitalic" Click="executeAction" />

  </ej:ContentGroup>

<ej:ContentGroup Id="underline" Text="Underline" ToolTip="Underline">

<ButtonSettings ContentType="ImageOnly" Type="Reset" PrefixIcon="e-ribbon e-ribbonunderline" Click="executeAction" />

  </ej:ContentGroup>                             

  </ContentGroupCollection>

       <ContentDefaults Type="Button" IsBig="false" />

   </ej:TabContent>

   </ContentCollection>

</ej:TabGroup>

<ej:TabGroup Text="CustomControls" AlignType="Rows" Type="custom" ContentID="Contents">

<ContentCollection>

   <ej:TabContent>

  <ContentGroupCollection>

<ej:ContentGroup Id="Customcontrol" Text="Bold" ToolTip="Custom">

<ButtonSettings ContentType="ImageOnly" Type="Button" PrefixIcon="e-ribbon bold"  />

   </ej:ContentGroup>

  </ContentGroupCollection>

        <ContentDefaults Type="Button" IsBig="false" />

   </ej:TabContent>

  </ContentCollection>

  </ej:TabGroup>

</TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="calculator" Text="CALCULATOR">

 <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="calculate" />                        

 </TabGroupCollection>

</ej:RibbonTab>

<ej:RibbonTab Id="design" Text="DESIGN">

    <TabGroupCollection>

<ej:TabGroup Text="New" AlignType="Rows" Type="custom" ContentID="designing" />                   

    </TabGroupCollection>

   </ej:RibbonTab>

  </RibbonTabs>

</ej:Ribbon>

</div>

<ul id="menu">

        <li><a>FILE</a>

            <ul>

                <li><a>New</a></li>

                <li><a>Open</a></li>

                <li><a>Save</a></li>

                <li><a>Save as</a></li>

                <li><a>Print</a></li>

            </ul>

        </li>

</ul>

    <div id="homediv">Ribbon Control</div>

    <div id="calculate"></div>

    <div id="designing"></div>

</asp:Content>



{% endhighlight %}



{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)

        {
            var fontlist = new List<string> { "Segoe UI", "Arial", "Times New Roman", "Tahoma", "Helvetica" };

              var fontsize = new List<string>() { "1pt", "2pt", "3pt", "4pt", "5pt" };

            this.fontfamily.DropdownSettings.DataSource = fontlist;

            this.fontsize.DropdownSettings.DataSource = fontsize;}

{% endhighlight %}

{% endtabs %}

The following screenshot illustrates the control Separator after the Italic Button control.

![](Getting-Started_images/Getting-Started_img13.png)