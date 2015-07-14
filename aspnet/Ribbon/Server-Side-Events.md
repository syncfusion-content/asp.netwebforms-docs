---
layout: post
title: Server-Side-Events
description: server side events
platform: aspnet
control: Ribbon
documentation: ug
---

## Server Side Events

The server side events for the _Ribbon_ control are as follows.

<table>
<tr>
<td>
Event</td><td>
Description</td><td>
Arguments</td></tr>
<tr>
<td>
TabSelect</td><td>
The event is triggered when the {{ '_Ribbon_' | markdownify }} tab gets selected.</td><td>
The selected items are passed as arguments.Arguments:1. {{ '_Current Tab Index_' | markdownify }}: Selected tab Index.2. {{ '_Previous tab Index_' | markdownify }}: Previous Active Tab Index</td></tr>
<tr>
<td>
<br>GroupClick</td><td>
The event is triggered when the {{ '_Ribbon_' | markdownify }} Group gets clicked.</td><td>
The selected items are passed as arguments.Arguments:1. {{ '_Control ID_' | markdownify }}: selected group ID. 2. Ribbon model.</td></tr>
<tr>
<td>
<br>GalleryItemClick</td><td>
The event is triggered when the gallery items get clicked.</td><td>
The selected items are passed as arguments. Arguments:1. Control ID: selected gallery Item ID. 2. Gallery model.</td></tr>
</table>







The following code example demonstrates how to handle the _TabSelect_event to get the selected tab information.

{% highlight html %}

[ASP.NET]

[ASPX]

<ej:Ribbon ID="Ribbon" runat="server" Width="100%" OnTabSelect="OnTabSelect">

        <ApplicationTab ItemID="menu" Type="ApplicationMenu"/>

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="New" AlignType="rows">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentGroupCollection>

                                    <ej:ContentGroup Id="New" Text="New" Type="Button">

                                      <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-ribbon e-new" Click="executeAction" />

                                    </ej:ContentGroup>

                                </ContentGroupCollection>

                                <ContentDefaults Width="60" Height="70" Type="Button" />

                            </ej:TabContent>

                        </ContentCollection>

                    </ej:TabGroup>

                </TabGroupCollection>

            </ej:RibbonTab>

        </RibbonTabs>

    </ej:Ribbon>

<ul id="menu">

<li><a>FILE</a></li>

</ul>



{% endhighlight %}



Add the following code example in code behind.

{% highlight c# %}

[CS]

protected void OnTabSelect(object sender, RibbonEventArgs e)

        {

            Label1.Text = "Ribbon Tab"+e.CurrentTabIndex+" is Selected"; //Ribbon Tab1 is Selected.

        }



{% endhighlight %}



