---
layout: post
title: Server Side Events | Ribbon | ASP.NET Webforms | Syncfusion
description: server side events
platform: aspnet
control: Ribbon
documentation: ug
---

# Server Side Events

The server side events for the Ribbon control are as follows.


<table>
<tr>
<th>
Event</th><th>
Description</th><th>
Arguments</th></tr>
<tr>
<td>
OnServerTabSelect</td><td>
The event is triggered when the Ribbon tab gets selected.</td><td>
The selected items are passed as arguments.

Arguments:
<ol>
<li>Current Tab Index: Selected tab Index.</li>
<li>Previous tab Index: Previous Active Tab Index</li>
</ol></td></tr>
<tr>
<td>
<br>OnServerGroupClick</td><td>
The event is triggered when the Ribbon Group gets clicked.</td><td>
The selected items are passed as arguments.

Arguments:
<ol>
<li>Control ID: selected group ID.</li>
<li>Ribbon model.</li>
</ol></td></tr>
<tr>
<td>
<br>OnServerGalleryItemClick</td><td>
The event is triggered when the gallery items get clicked.</td><td>
The selected items are passed as arguments. 

Arguments:
<ol>
<li>Control ID: selected gallery Item ID.</li>
<li>Gallery model.</li>
</ol></td></tr>
</table>

The following code example demonstrates how to handle the TabSelect event to get the selected tab information.

{% highlight html %}

<ej:Ribbon ID="Ribbon" runat="server" Width="100%" OnServerTabSelect="OnTabSelect">

        <ApplicationTab MenuItemID="menu" Type="Menu"/>

        </ApplicationTab>

        <RibbonTabs>

            <ej:RibbonTab Id="home" Text="HOME">

                <TabGroupCollection>

                    <ej:TabGroup Text="New" AlignType="rows">

                        <ContentCollection>

                            <ej:TabContent>

                                <ContentGroupCollection>

                                    <ej:ContentGroup Id="New" Text="New" Type="Button">

                                      <ButtonSettings Type="Button" ContentType="ImageOnly" ImagePosition="ImageTop" PrefixIcon="e-icon e-ribbon e-new" Click="executeAction" />

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

protected void OnTabSelect(object sender, RibbonEventArgs e)

        {

            Label1.Text = "Ribbon Tab"+e.CurrentTabIndex+" is Selected"; //Ribbon Tab1 is Selected.

        }

{% endhighlight %}