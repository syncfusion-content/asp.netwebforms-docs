---
layout: post
title: Server Side Event | Tab | ASP.NET | Syncfusion
description: server side event
platform: aspnet
control: Tab
documentation: ug
---

# Server Side Event

The following server side event is available in the Tab control.

<table>
<tr>
<th>
Event</th><th>
Event Description</th><th>
Argument Details</th></tr>
<tr>
<td>
OnTabItemActive</td><td>
It raises when Active Tab is changed.</td><td>

Event Argument contains the following parameters:<br/>

e.NewSelectedItem - Current Selected index value.<br/>

e.OldSelectedItem - Previous index value.<br/>

e.EventType - Event Name<br/>

e.Arguments - Contain keys and values for prevActiveIndex and ActiveIndex.<br/>

</td></tr>
</table>

 In the ASPX page, add the Tab control to configure Tab events.

{% highlight html %}

<%--Add serverside event for Radio Button control as follows--%>

<ej:Tab ID="pizzaMenu" runat="server" Width="650px" OnTabItemActive="pizzaMenu_TabItemActive">

    <Items>

        <ej:TabItem ID="gardenfresh" Text="GARDEN FRESH (Veg)">

            <ContentSection>

                <img src="http://js.syncfusion.com/demos/web/images/accordion/garden-veggie.png"

                    alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $50

                    <br />

                    Ingredients : cheese, onions, green capsicums & tomatoes.

                </div>

            </ContentSection>

        </ej:TabItem>

        <ej:TabItem ID="cornandspinach" Text="CORN & SPINACH (Veg)">

            <ContentSection>

                <img src="http://js.syncfusion.com/demos/web/images/accordion/corn-and-spinach-05.png"

                    alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $70

                    <br />

                    Ingredients : cheese, sweet corn & green capsicums.

                </div>

            </ContentSection>

        </ej:TabItem>

        <ej:TabItem ID="chickendelite" Text="CHICKEN DELITE (Non-veg)">

            <ContentSection>

                <img src=" http://js.syncfusion.com/demos/web/images/accordion/chicken-delite.png"

                    alt="garden-fresh" />

                <div class="ingredients">

                    Rate : $100

                    <br />

                    Ingredients : cheese, chicken chunks, onions & pineapple chunks.

                </div>

            </ContentSection>

        </ej:TabItem>

    </Items>

</ej:Tab>

{% endhighlight %}

Then Define pizzaMenu_TabItemActive server side event in the code behind.

{% highlight c# %}

protected void pizzaMenu_TabItemActive(object sender, Syncfusion.JavaScript.Web.TabEventArgs e)
{

	//e.NewSelectedIndex – Current selected index value.

	//e.OldSelectedIndex – Previous index value.

	//e.EventType – Event Name

	//e.Arguments – Contains Keys and Values for prevActiveIndex and activeIndex

}

{% endhighlight %}