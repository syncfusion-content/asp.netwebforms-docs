---
layout: post
title: Position | Tooltip | ASP.NET | Syncfusion
description: Positionining support to Tooltip widget for Syncfusion Essential JS
platform: aspnet
control: Tooltip
documentation: ug
keywords : aspTooltip, ASP Tooltip, asp Tooltip,ASP Tooltip widget,ASP Tooltip position,ASP Tooltip collision
---

# Position

The position object defines various attributes of the Tooltip position, including the element it is positioned in relation to, and how the position is adjusted within the defined container.

Lets position the Tooltips (stems) left center corner at the right center of the target element.

{% highlight CSHTML %}
 
    <div class="img" id="sample">
        <a target="_blank" href="image/taj.png">
            <img src="http://asp.syncfusion.com/demos/web/content/images/tooltip/template-05.png" alt="Delphi">
        </a>
        <div class="desc">Delphi Succinctly</div>
    </div>

    <ej:Tooltip For="sample" runat="server" ClientIDMode="Static"  Content="Learn the fundamentals of Delphi to build a variety of solutions for many devices and platforms.">
        <Position>
            <Stem Horizontal="left" Vertical="center" />
            <Target Horizontal="right" Vertical="center" />
        </Position>
    </ej:Tooltip>

{% endhighlight %}

Apply the following styles to show the Tooltip.

{% highlight css %}

    <style>
        div.img {
            border: 1px solid #ccc;
            float: left;
            box-sizing: border-box;
            height: 200px;
            width: 146px;
        }
        div.img img{
            width: 100%;
            height: 166px;
        }
        div.desc {
            padding: 6px;
            text-align: center;
        }
    </style>
    
{% endhighlight %}

![Position](Position_images/position.png)

N> By default, the Tooltips "center bottom" corner is placed at the center top of the target element.

## Containment 

Determines the HTML element in which the Tooltip is appended to e.g. its containing element and The tooltip will be restricted to move only within the specified container element.

Let's append our Tooltip to a custom 'frame' container:

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip1"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>
    
    <ej:Tooltip For="tooltip1" runat="server" ClientIDMode="Static" Containment=".frame"  Content="JavaScript is the programming language of HTML and the Web."></ej:Tooltip>
    
{% endhighlight %}

N> By default all Tooltips are appended to the document.body element.

## Associates 

 The Tooltip will be positioned in relation to target element. Can also be set to 'mouse' or the window, or an absolute x/y position on the page.
 
 Let's position the Tooltip in relation to the 'a' element inside the div element:
 
 {% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip2"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="tooltip2" runat="server" ClientIDMode="Static" Containment=".frame"  Content="JavaScript is the programming language of HTML and the Web."></ej:Tooltip>
    
{% endhighlight %}
 
We can also position the Tooltip in relation to the mouse.
 
{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip3"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="tooltip3" runat="server" ClientIDMode="Static" Associate="Mousefollow"  Content="JavaScript is the programming language of HTML and the Web."></ej:Tooltip>
    
{% endhighlight %}

Position the tooltip at the current mouse position, once enter to the target element as follows

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip4"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="tooltip4" runat="server" ClientIDMode="Static" Associate="Mouseenter"  Content="JavaScript is the programming language of HTML and the Web."></ej:Tooltip>
    
{% endhighlight %}


It also possible to place the tooltip relation to the window as follows

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip5"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="tooltip5" runat="server" ClientIDMode="Static" Associate="Window"  Content="JavaScript is the programming language of HTML and the Web.">
    <Position>
            <Target Horizontal="right" Vertical="bottom" />
        </Position>
    </ej:Tooltip>
    
{% endhighlight %}
    
And last but not least, absolute positioning via X,Y co-ordinates e.g. a Tooltip at 10px from left and top of the page:

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip6"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="tooltip6" runat="server" ClientIDMode="Static" Associate="Axis"  Content="JavaScript is the programming language of HTML and the Web.">
    <Position>
            <Target Horizontal="10" Vertical="10" />
        </Position>
    </ej:Tooltip>
    
{% endhighlight %}

## Collision 

When the positioned element overflows the window in some direction, move it to an alternative position. 

The following values determines the kind of positioning that takes place.

<table>
<tr>
<td>
Value<br/></td><td>
Description<br/></td></tr>
<tr>
<td>
Flip<br/></td><td>
Flips the element to the opposite side of the target if the collision detected.<br/></td></tr>
<tr>
<td>
Fit<br/></td><td>
Shift the element away from the edge of the window.<br/></td></tr>
<tr>
<td>
FlipFit(Default)<br/></td><td>
Ensure as much of the element is visible as possible to showcase.<br/></td></tr>
<tr>
<td>
None<br/></td><td>
Does not apply any collision detection.<br/></td></tr>
</table>

{% highlight CSHTML %}
 
    <div class="frame">
        <div class="control">
            TypeScript lets you write <a id="tooltip7"><u> JavaScript</u> </a>the way you really want to.
        </div>
    </div>

    <ej:Tooltip For="ttooltip7est" runat="server" ClientIDMode="Static" Collision="Fit"  Content="JavaScript is the programming language of HTML and the Web."></ej:Tooltip>
    
{% endhighlight %}