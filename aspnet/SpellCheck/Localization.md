---
title: Localization
description: Localizing SpellCheck
platform: aspnet
control: spellcheck
documentation: ug
keywords: spellcheck localize, localize, localization, localize specific words
---
# Localization

SpellCheck dialog mode comes with default localization support which allows it to customize the display of text within the SpellCheck dialog in a user-specific culture and locale. The SpellCheck control can be localized in specific culture using the common API **locale** along with the collection of localized words defined for that culture using the ej.SpellCheck.Locale [**culture-code**].

By default, the SpellCheck control is localized in **en-US** culture. Please find the following table lists the default keywords and its localized text values for en-US culture.

<table>
        <tr>
            <th>
                Locale key words </th>
            <th>
                Text
            </th>
        </tr>
        <tr>
            <td>
                SpellCheckButtonText
            </td>
            <td>
                Spelling:
            </td>
        </tr>
        <tr>
            <td>
                NotInDictionary
            </td>
            <td>
                Not in Dictionary:
            </td>
        </tr>
        <tr>
            <td>
                SuggestionLabel
            </td>
            <td>
                Suggestions:
            </td>
        </tr>
        <tr>
            <td>
                IgnoreOnceButtonText
            </td>
            <td>
                Ignore Once
            </td>
        </tr>
        <tr>
            <td>
                IgnoreAllButtonText
            </td>
            <td>
                Ignore All
            </td>
        </tr>
        <tr>
            <td>
                AddToDictionary
            </td>
            <td>
                Add to Dictionary
            </td>
        </tr>
        <tr>
            <td>
                ChangeButtonText
            </td>
            <td>
                Change
            </td>
        </tr>
        <tr>
            <td>
                ChangeAllButtonText
            </td>
            <td>
                Change All
            </td>
        </tr>
        <tr>
            <td>
                CloseButtonText
            </td>
            <td>
                Close
            </td>
        </tr>
        <tr>
            <td>
                CompletionPopupMessage
            </td>
            <td>
                Spell check is complete
            </td>
        </tr>
        <tr>
            <td>
                CompletionPopupTitle
            </td>
            <td>
                Spell check
            </td>
        </tr>
        <tr>
            <td>
                Ok
            </td>
            <td>
                OK
            </td>
        </tr>
        <tr>
            <td>
                NoSuggestionMessage
            </td>
            <td>
                No suggestions available
            </td>
        </tr>
		 <tr>
            <td>
                NotValidElement
            </td>
            <td>
                Specify the valid control id or class name to spell check
            </td>
        </tr>
</table>

To localize SpellCheck into any particular culture, it is necessary to refer the culture-specific script files in your application after the reference of **ej.web.all.min.js** file, which are available under the following location.                   

_<**Installed location**>\Syncfusion\Essential Studio\{{ site.releaseversion }}\JavaScript\assets\scripts\i18n_

The following code example shows how to localize the SpellCheck control in **fr-FR** culture.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes.
        The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea" Locale="fr-FR">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    </ej:SpellCheck>    
</div>
<div>
    <ej:Button ID="CheckText" Type="Button" ClientSideOnClick="checkErrors" Text="Spell Check" runat="server"></ej:Button>
</div>

<script>
        ej.SpellCheck.Locale["fr-FR"] = {
            SpellCheckButtonText: "Orthographe",
            NotInDictionary: "Pas dans le dictionnaire",
            SuggestionLabel: "Suggestions",
            IgnoreOnceButtonText: "Ignorer une fois",
            IgnoreAllButtonText: "Ignorer tout",
            AddToDictionary: "Ajouter au dictionnaire",
            ChangeButtonText: "Changement",
            ChangeAllButtonText: "Tout modifier",
            CloseButtonText: "Fermer",
            CompletionPopupMessage: "VÃ©rification orthographique est terminÃ©e",
            ErrorPopupMessage: "VÃ©rification orthographique est pas terminÃ©e",
            CompletionPopupTitle: "VÃ©rification orthographique alerte",
            OK: "D'accord",
            NoSuggestionMessage: "Aucune suggestion disponible",
        };

        function checkErrors() {
            var spellObj = $("#SpellCheck").data("ejSpellCheck");
            spellObj.showInDialog();
        }
</script>

{% endhighlight %}

N> Refer the **ej.culture.fr-FR.min.js** file in your HTML application and also define the **locale** property for the SpellCheck control with the appropriate **culture-code** [**fr-FR**].

For further information on how to refer the required culture scripts into your application, refer [here](https://help.syncfusion.com/js/localization).

### Localizing Specific Words

To customize or localize only some specific words in the default **ej.SpellCheck.Locale["en-US"]** collection, the words to be localized/customized can be defined in a separate variable and then extended to the original collection as depicted in the following code example.

{% highlight html %}

<div id="TextArea" contenteditable="true">
        Facebook is a social networking service headquartered in Menlo Park, California. Its website was launched on February 4, 2004, by Mark Zuckerberg with his Harvard College roommates and fellow students Eduardo, Andrew McCollum, Dustin and Chris Hughes. The fouders had initially limited the websites membrship to Harvard students, but later expanded it to collges in the Boston area, the Ivy League, and Stanford Univrsity. It graually added support for students at various other universities and later to high-school students.
</div>
<div>
    <ej:SpellCheck ID="SpellCheck" ClientIDMode="Static" runat="server" ControlsToValidate="#TextArea">
        <DictionarySettings DictionaryUrl="../api/SpellCheck/CheckWords" CustomDictionaryUrl="../api/SpellCheck/AddToDictionary" />
    </ej:SpellCheck>    
</div>
<div>
    <ej:Button ID="CheckText" Type="Button" ClientSideOnClick="checkErrors" Text="Spell Check" runat="server"></ej:Button>
</div>

<script>
        
    var customizationMessage = {
		CompletionPopupMessage: "Completed",
	};
	// Extend only the required changes to the original locale collection
	$.extend(ej.SpellCheck.Locale["en-US"], customizationMessage);

    function checkErrors() {
        var spellObj = $("#SpellCheck").data("ejSpellCheck");
        spellObj.showInDialog();
    }
</script>

{% endhighlight %}