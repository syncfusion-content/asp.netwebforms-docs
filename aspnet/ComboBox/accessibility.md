---
layout: post
title: Accessibility with ComboBox control for Syncfusion ASP.NET WebForm.
description: Describes about the accessibility in ComboBox control for Syncfusion Essential WebForm.
platform: aspnet
control: ComboBox
documentation: ug
keywords: ComboBox, ComboBox, Accessibility, ARIA attributes, Keyboard interaction
---

# Accessibility

The ComboBox component has been designed, keeping in mind the `WAI-ARIA` specifications, and applies the WAI-ARIA roles, states, and properties along with `keyboard support`. This component is characterized by complete keyboard interaction support and ARIA accessibility support that makes it easy for people who use assistive technologies (AT) or those who completely rely on keyboard navigation.

## ARIA attributes

The ComboBox component uses the `combobox` role, and each list item has an `option` role. The following `ARIA attributes` denote the ComboBox state.

| **Properties** | **Functionalities** |
| --- | --- |
| aria-haspopup | Indicates whether the ComboBox input element has a popup list or not. |
| aria-expanded | Indicates whether the popup list has expanded or not. |
| aria-selected | Indicates the selected option. |
| aria-readonly | Indicates the readonly state of the ComboBox element. |
| aria-disabled | Indicates whether the ComboBox component is in a disabled state or not. |
| aria-activedescendent | This attribute holds the ID of the active list item  to focus its descendant child element. |
| aria-owns | This attribute contains the ID of the popup list to indicate popup as a child element. |
| aria-autocomplete | This attribute contains the ‘both’ to a list of options shows and the currently selected suggestion also shows inline. |

## Keyboard interaction

You can use the following key shortcuts to access the ComboBox without interruptions.

| **Keyboard shortcuts** | **Actions** |
| --- | --- |
| <kbd>Arrow Down</kbd> | Selects the first item in the ComboBox when no item selected. Otherwise, selects the item next to the currently selected item. |
| <kbd>Arrow Up</kbd> | Selects the item previous to the currently selected one. |
| <kbd>Page Down</kbd> | Scrolls down to the next page and selects the first item when popup list opens. |
| <kbd>Page Up</kbd> | Scrolls up to the previous page and selects the first item when popup list opens. |
| <kbd>Enter</kbd> | Selects the focused item and popup list closes when it is in open state. |
| <kbd>Tab</kbd> | Focuses on the next TabIndex element on the page when the popup is closed. Otherwise, closes the popup list and remains the focus of the component. |
| <kbd>Shift + tab </kbd> | Focuses on the previous TabIndex element on the page when the popup is closed. Otherwise, closes the popup list and remains the focus of the component. |
| <kbd>Alt + Down</kbd> | Open the popup list |
| <kbd>Alt + Up</kbd> | Close the popup list|
| <kbd>Esc(Escape)</kbd> | Closes the popup list when it is in an open state and the currently selected item remains the same. |
| <kbd>Home</kbd> | Selects the first item when popup open state. If it is in closed state, cursor moves to before of first character in input |
| <kbd>End</kbd> | Selects the last item when popup open state. If it is in closed state, cursor moves to next of last character in input  |

> In the following sample, focus the ComboBox component using <kbd>alt+j</kbd> keys.

{% tabs %}
	
{% highlight html %}
	
<ej:ComboBox ID="selectCar" runat="server" Placeholder="Select a car" DataTextField="text" Width="100%"> </ej:ComboBox>
		
{% endhighlight %}
    
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
    this.selectCar.DataSource = CarsList.GetCarList();
}

{% endhighlight %}

{% highlight javascript %}

<script>
	
$(document).on("keydown", function (e) {
    if (e.altKey && e.keyCode === 74) { // j- key code.
        $("#LayoutSection_ControlsSection_selectCar").focus();
    }
});	

</script>
		
{% endhighlight %}

{% endtabs %}

 