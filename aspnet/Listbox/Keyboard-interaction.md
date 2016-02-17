---
layout: post
title: Keyboard interaction | ListBox | ASP.NET Webforms | Syncfusion
description: keyboard interaction
platform: aspnet
control: ListBox
documentation: ug
---

# Keyboard interaction

You can use Keyboard shortcut keys as an alternative for mouse actions to interact with the ListBox widget. Please refer the below table for details about short cut keys and its corresponding usage.

<table>
<tr>
<td>
<b>Shortcut Key</b></td><td>
<b>Usage</b></td></tr>
<tr>
<td>
<kbd>Enter</kbd></td><td>
Selects the focused item</td></tr>
<tr>
<td>
<kbd>Up</kbd></td><td>
Moves to previous item</td></tr>
<tr>
<td>
<kbd>Down</kbd></td><td>
Moves to next item</td></tr>
<tr>
<td>
<kbd>Left</kbd></td><td>
Moves to previous item</td></tr>
<tr>
<td>
<kbd>Right</kbd></td><td>
Moves to next item</td></tr>
<tr>
<td>
<kbd>Home</kbd></td><td>
Moves to first item</td></tr>
<tr>
<td>
<kbd>End</kbd></td><td>
Moves to last item</td></tr>
</table>

N> Initial focus can be done by pressing tab key multiple times until it is focused.

## Incremental Search

The [Incremental search](https://en.wikipedia.org/wiki/Incremental_search) helps in finding the specific item in the ListBox,as the user types the text one or more possible matches for the text are found and the first matched item will be selected.It can be enabled in the ListBox widget using “EnableIncrementalSearch” API. The search can be case sensitive or case insensitive.

{% highlight html %}

<ej:ListBox ID="ListBox" runat="server" EnableIncrementalSearch="true" CaseSensitiveSearch="true">
        <Items>
            <ej:ListBoxItems Text="Audi A4"></ej:ListBoxItems>
            <ej:ListBoxItems Text="Audi A5"></ej:ListBoxItems>
            <ej:ListBoxItems Text="Audi A6"></ej:ListBoxItems>
            <ej:ListBoxItems Text="Audi A7"></ej:ListBoxItems>
            <ej:ListBoxItems Text="Audi A8"></ej:ListBoxItems>
            <ej:ListBoxItems Text="BMW 501"></ej:ListBoxItems>
            <ej:ListBoxItems Text="BMW 502"></ej:ListBoxItems>
            <ej:ListBoxItems Text="BMW 503"></ej:ListBoxItems>
            <ej:ListBoxItems Text="Batch"></ej:ListBoxItems>
            <ej:ListBoxItems Text="BMW 507"></ej:ListBoxItems>
        </Items>
    </ej:ListBox>


{% endhighlight %}


![](Keyboard-interaction_images\Keyboard-interaction_img1.png)

Press <kbd>tab</kbd> key to get ListBox focus and press <kbd>“A” </kbd> (enable caps lock or press <kbd>shift</kbd> + <kbd>“A” </kbd> since case sensitive search is enabled) to get the below output.

![](Keyboard-interaction_images\Keyboard-interaction_img2.png)
