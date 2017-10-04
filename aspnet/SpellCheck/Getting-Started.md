---
title: Getting started with SpellCheck component	
description: Rendering a basic SpellCheck
platform: aspnet
control: spellcheck
documentation: ug
keywords: SpellCheck, Getting Started, Service Reference, Content Checking
---
# Getting Started 

This section explains the step-by-step instructions to add SpellCheck control in an ASP.NET web application.

## Create your First SpellCheck in ASP.NET

    1. Create an ASP.NET Web Forms application and add SpellCheck control to the Default.aspx page.
       
{% highlight html %}
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server">        
    </ej:SpellCheck>    
</div>
{% endhighlight %}

    2. Add the target element and map its id or class name to the SpellCheck control.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">        
    </ej:SpellCheck>    
</div>

{% endhighlight %}

N> You need to pass the target element id or class name value in the **ControlsToValidate** property to perform the spell check properly.

    3. Adding the Service Reference

Assign the service method (CheckWords) path reference to the property **DictionaryUrl**, which is mandatory to check the spelling of the word.

The CheckWords method will perform the splitting of target sentence into separate words and check each word is that an erroneous or not. If the word is erroneous fetching the possible suggestions for it and returns those details as a result.

{% highlight html %}
<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords"/>
    </ej:SpellCheck>    
</div>

{% endhighlight %}

    4. Spell Checking the Content

To spell check the content of the target element, you need to add one button and calling any one of the SpellCheck method **showInDialog** or **validate** by clicking the button to highlight the error words.

The following code example depicts that checking the spelling of the target element through the "validate" method.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:Button ID="CheckText" Type="Button" ClientSideOnClick="checkErrors" Text="Spell Check" runat="server"></ej:Button>
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    </ej:SpellCheck>    
</div>
<script type="text/javascript">
    function checkErrors() {
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
        spellObj.validate();
    }
</script>
{% endhighlight %}

