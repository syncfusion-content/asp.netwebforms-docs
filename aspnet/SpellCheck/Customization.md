---
title: SpellCheck - Customization
description: SpellCheck Customization
platform: aspnet
control: spellcheck
documentation: ug
keywords: customization, spellcheck customization, misspell word appearance, restrict suggestion count
---
# SpellCheck Customization

The SpellCheck control provides option to customize the following scenarios.

* Misspell Word Appearance
* Restrict Suggestion Count
    
## Misspell Word Appearance

The SpellCheck control provide the option **MisspellWordCss** to display the error word in user defined style. By default, displays the error words with the red underline. 

The following code example depicts the way to customize the error word highlight (displaying error word with red color font and lightblue background).

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
        The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" MisspellWordCss="highlight">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    </ej:SpellCheck>    
</div>
<div>
    <ej:Button ID="CheckText" Type="Button" ClientSideOnClick="checkErrors" Text="Spell Check" runat="server"></ej:Button>
</div>

<script>
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
</script>

<style>
        .highlight {
            background-color: lightblue;
            color: red;
        }
</style>

{% endhighlight %}

## Restrict Suggestion Count

The SpellCheck control provide the option **MaxSuggestionCount** to restrict the the number of items to be displayed in the suggestion list.

The following code example describes the way to control the suggestion count.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
        The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" MaxSuggestionCount="3">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    </ej:SpellCheck>    
</div>
<div>
    <ej:Button ID="CheckText" Type="Button" ClientSideOnClick="checkErrors" Text="Spell Check" runat="server"></ej:Button>
</div>

<script>
        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.validate();
        }
</script>

{% endhighlight %}