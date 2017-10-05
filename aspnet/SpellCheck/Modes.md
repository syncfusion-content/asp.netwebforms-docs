---
title: SpellCheck - Operations
description: SpellCheck Operations
platform: aspnet
control: spellcheck
documentation: ug
keywords: operations, spellcheck modes, dialog mode, context menu mode,  custom menu, handling menu actions, handling dialog actions
---
# SpellCheck Operations

Essential SpellCheck provides two ways to perform the spell check operations(error correction). They are as follows,

* Dialog Mode 
* Context Menu Mode  

## Dialog Mode

### Description

SpellCheck provides the dialog mode option to perform the following spell check operations.

* Ignore Once
* Ignore All
* Change
* Change All
* Add to Dictionary

### Open Dialog Mode

The following code snippet shows how to open the dialog to spell check the content.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
</script>
{% endhighlight %}

### Handling Dialog Actions

To define the specific actions before the dialog window open, the client-side event **DialogBeforeOpen** can be used as depicted in the below code example.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" DialogBeforeOpen="onDialogBeforeOpen">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
        function onDialogBeforeOpen(args) {
            if (args.requestType == "dialogBeforeOpen") {
                alert("dialog before open event triggered");
            }
        }
</script>
{% endhighlight %}

The client-side event **DialogOpen** can be used to define the specific actions after the dialog window open as shown in the following code example.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" DialogOpen="onDialogOpen">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
        function onDialogOpen(args) {
            if (args.requestType == "dialogOpen") {
                alert(args.targetText);
            }
        }
</script>

{% endhighlight %}

The following code example used to define some actions after the dialog closing by using the client-side event **DialogClose**.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" DialogClose="onDialogClose">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
        function onDialogClose(args) {
            if (args.requestType == "dialogClose") {
                alert(args.updatedText);
            }
        }
</script>

{% endhighlight %}

It is possible to predict the error word details before starting the spell check operations through dialog mode by using the client-side event **Start**. The below code example describes the above behavior.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" Start="onSpellCheckStart">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
        function onSpellCheckStart(args) {
            if (args.requestType == "spellCheckDialog") {
                alert(JSON.stringify(args.errorWords));
            }
        }
</script>

{% endhighlight %}

You can get the corrected text content details before updating it into target element with the help of the client side event **Complete** as mentioned in the below code example.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInDialog" Text="Spell Check using Dialog" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" Complete="onSpellCheckComplete">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
</ej:SpellCheck>

<script type="text/javascript">
        function showInDialog() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
        function onSpellCheckComplete(args) {
            if (args.requestType == "changeErrorWord") {
                alert(args.targetText);
            }
        }
</script>

{% endhighlight %}

## Context Menu Mode

SpellCheck provides default context menu options to perform the spell check operations. It also allows to define additional custom context menu options.

The options that are available under **ContextMenuSettings** are as follows,

* **Enable** - Enables/disables the context menu option in SpellCheck.
* **MenuItems** - Contains the options to perform spell check operations.

### Default Menu Options

The menu items contains the following options to perform the spell check operations.

* Ignore All
* Add to Dictionary 

The following code snippet shows how to enable the context menu settings in SpellCheck and to make use of it with default available options.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInContextMenu" Text="Spell Check" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    <ContextMenuSettings Enable="true"/>
</ej:SpellCheck>

<script type="text/javascript">
        function showInContextMenu() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
</script>

{% endhighlight %}

N> For default menu items, the id must be defined the same as mentioned in the above code example – as we have processed the menus based on this id within our source.

### Custom Menu Options

Apart from the default available options, it is also possible to add custom menu options to the context-menu list.

The following code example depicts how **to add the custom menu items** into the context menu settings.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInContextMenu" Text="Spell Check" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    <ContextMenuSettings Enable="true">  
        <MenuItems>
            <ej:SpellContextMenuItem ID="Ignore" Text="Ignore Once" />
            <ej:SpellContextMenuItem ID="IgnoreAll" Text="IgnoreAll" />
            <ej:SpellContextMenuItem ID="AddToDictionary" Text="Add to Dictionary" />
        </MenuItems>                  
    </ContextMenuSettings>
</ej:SpellCheck>

<script type="text/javascript">
        function showInContextMenu() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
</script>

{% endhighlight %}

N> The **ID** given for the custom menu items **must be unique**.

### Handling Menu Actions

The client-side event **ContextClick** can be used to define specific actions when a click made on the custom menu items. The following code example describes the above behavior.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInContextMenu" Text="Spell Check" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" ContextClick="onCustomMenuClick">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    <ContextMenuSettings Enable="true">  
        <MenuItems>
            <ej:SpellContextMenuItem ID="Ignore" Text="Ignore Once" />
            <ej:SpellContextMenuItem ID="IgnoreAll" Text="IgnoreAll" />
            <ej:SpellContextMenuItem ID="AddToDictionary" Text="Add to Dictionary" />
        </MenuItems>                  
    </ContextMenuSettings>
</ej:SpellCheck>

<script type="text/javascript">
        function showInContextMenu() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
        function onCustomMenuClick(args) {
            if (args.selectedOption == "Ignore") {
                alert("Custom menu clicked");
            }
        }
</script>

{% endhighlight %}

It is possible to predict the target (error word) on which the right click is made with the use of the event **ContextOpen**. The below code example shows how to block the display of context menu, when right clicked on the word by setting **args.cancel** as **true**.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInContextMenu" Text="Spell Check" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" ContextOpen="onBeforeOpen">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    <ContextMenuSettings Enable="true"/>
</ej:SpellCheck>

<script type="text/javascript">
        function showInContextMenu() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
        function onBeforeOpen(args) {
            if (args.selectedErrorWord == "Bluetec") {
                args.cancel = true;
            }
        }
</script>

{% endhighlight %}

You can get the current spell check operation arguments details with the client-side event **Validating**. The following code example describes the way to block the ignoreAll operation for the particular word.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<ej:Button ID="CheckButton" Type="Button" ClientSideOnClick="showInContextMenu" Text="Spell Check" runat="server"></ej:Button>
<ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" Validating="onSpellChecking">
    <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    <ContextMenuSettings Enable="true"/>
</ej:SpellCheck>

<script type="text/javascript">
        function showInContextMenu() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
        function onSpellChecking(args) {
            if (args.requestType == "ignoreAll" && args.ignoreWord == "Bluetec") {
                args.cancel = true;
            }
        }
</script>

{% endhighlight %}