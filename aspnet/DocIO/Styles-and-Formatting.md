---
layout: post
title: Styles and Formatting | DocIO | ASP.NET Webforms | Syncfusion
description: styles and formatting
platform: aspnet
control: DocIO
documentation: ug
---

# Styles and Formatting

Styles and Formatting make a Word document a full fledged and well formatted one. Word document and document elements have their own styles and formatting.

Styles or Formattings can be classified into three types based on its behavior:

* Character style
* Paragraph style
* Table style

The following are the types of formattings supported by DocIO.

* Character formatting
* Paragraph formatting
* List style fromatting


N> DocIO currently does not support table styles.



## Introduction to styles and formatting in DocIO

DocIO allows you to create your own paragraph style and list styles (user-defined style), which can be applied to any paragraph or list item. Refer to the Paragraph formatting section to know more about the user-defined styles.


N> In a Word document style hierarchy, “Normal” is the base style and is the default style for paragraphs and tables, if the user has not specified style definition.



Collection of DocIO Character and Paragraph styles are accessible through the WordDocument.Styles property. Collection of List styles is accessible through the WordDocument.ListStyles property.

## Style Class

DocIO Style class is a base class for the other style classes. Style is an abstract class. CharacterFormat property of Style class specifies character formatting. This property returns the instance of WCharacterFormat type. Name property specifies the name of the style. BaseStyle property specifies the base style (style inherits formatting of base style). User can apply one of the built-in Word styles by using the WParagraph.ApplyStyle method. The built-in styles are accessible through the BuiltinStyle enumeration.

### Public Properties

_Table_ _109_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
CharacterFormat</td><td>
Gets the character format.    </td></tr>
<tr>
<td>
Name</td><td>
Gets or sets the style name.  </td></tr>
<tr>
<td>
StyleType</td><td>
Gets the type of style.  </td></tr>
<tr>
<td>
IsPrimaryStyle</td><td>
Gets or sets the Primary style definition. If you set this to true, then the corresponding style will be displayed in Syles ribbon of Microsoft Word.</td></tr>
</table>

### Public Methods

_Table_ _110_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
ApplyBaseStyle</td><td>
Applies base style for current style.</td></tr>
<tr>
<td>
Clone</td><td>
Clones itself.</td></tr>
</table>


## Acessing Styles

You can access the collection of styles defined in the document by using the Styles property. This collection holds both the built-in and user-defined styles in a document. A particular style can be obtained by its name or index.

The following code example illustrates how to access the collection of styles defined in the Word document.


{% highlight C# %}



//Gets a collection of styles defined in the document.

IStyleCollection coll = document.Styles;



//Accesses a particular style.

IStyle style= coll.FindByName(string Stylename ) ;

IStyle style= coll.FindByName(string Stylename,StyleType styleType) ;

//Accesses a particular style by using the index.

IStyle style1=coll[0];

{% endhighlight %}

{% highlight vbnet %}



'Gets a collection of styles defined in the document.

Dim coll As IStyleCollection = document.Styles



'Accesses a particular style.

Dim style As IStyle= coll.FindByName(String Stylename)

Dim style As IStyle= coll.FindByName(String Stylename,StyleType styleType)

'Accesses a particular style using the index.

Dim style1 As IStyle = coll(0)

{% endhighlight %}

## Character Formatting Properties

### Character Styles

This sections elaborates how to deal with the Character Styles. The class CharacterStyle takes resposibilty for handling the character styles. 


N> DocIO does not provide support to add user-defined character styles to the document

### Class Hierarchy

Style

   |

    CharacterStyle



### Public Properties



_Table_ _111_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
BaseStyle</td><td>
Gets the base style.</td></tr>
<tr>
<td>
StyleType</td><td>
Gets the type of style.  </td></tr>
<tr>
<td>
UseContextualAlternates</td><td>
Gets or sets a value indicating whether to use contextual alternates (Microsoft Word 2010 specific property).</td></tr>
<tr>
<td>
Ligatures</td><td>
Gets or sets the ligatures type (Microsoft Word 2010 specific property).</td></tr>
<tr>
<td>
NumberForm</td><td>
Gets or sets the number form type (Microsoft Word 2010 specific property).</td></tr>
<tr>
<td>
NumberSpacing</td><td>
Gets or sets the number spacing type (Microsoft Word 2010 specific property).</td></tr>
<tr>
<td>
StylisticSet</td><td>
Gets or sets the stylistic set type (Microsoft Word 2010 specific property).</td></tr>
</table>


### Public Methods

_Table_ _112_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
Clone</td><td>
Clones itself.</td></tr>
<tr>
<td>
NameToBuiltIn</td><td>
Converts string style names to BuiltinStyle.</td></tr>
</table>

### Character Formatting

The class WCharacterFormat represents the character formats in Essential DocIO. It is used to get or set the formatting for text chunks, special symbol, or marker (for example marker of picture, text box, footnote, etc.). WCharacterFormat customizes the appearance of the element (for example text chunk or symbol) in the document, starting with font name to the style of texture and spacing between characters.

### Class Hierarchy

FormatBase

         |

         WCharacterFormat



### Public Constructor

_Table_ _113_: _Public Constructors_

<table>
<tr>
<th>
Constructor </th><th>
Description</th></tr>
<tr>
<td>
WCharacterFormat.WCharacterFormat (IWordDocument)</td><td>
Initializes a new instance of the WCharacterFormat class.</td></tr>
</table>


### Public Properties

_Table_ _114_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
AllCaps</td><td>
Gets or sets the AllCaps property of text.</td></tr>
<tr>
<td>
Bidi</td><td>
Gets or sets the right-to-left property of text.  </td></tr>
<tr>
<td>
Bold</td><td>
Gets or sets the bold style of text.</td></tr>
<tr>
<td>
BoldBidi</td><td>
Gets or sets the bold property for right-to-left text.  </td></tr>
<tr>
<td>
Border</td><td>
Gets the border for text.</td></tr>
<tr>
<td>
CharacterSpacing</td><td>
Gets or sets the space width between characters in text.  </td></tr>
<tr>
<td>
DoubleStrike</td><td>
Gets or sets the doublestrikeout style to text.  </td></tr>
<tr>
<td>
Emboss           </td><td>
Gets or sets the emboss property of text.  </td></tr>
<tr>
<td>
Engrave</td><td>
Gets or sets the engrave property of text.  </td></tr>
<tr>
<td>
Font</td><td>
Gets or sets the font as System.Drawing.Font. </td></tr>
<tr>
<td>
FontName</td><td>
Gets or sets the font name for text.</td></tr>
<tr>
<td>
FontNameBidi</td><td>
Gets or sets the font name for right-to-left text.  </td></tr>
<tr>
<td>
FontSize</td><td>
Gets or sets the font size (in points).</td></tr>
<tr>
<td>
FontSizeBidi</td><td>
Gets or sets the font size of the right-to-left text (in points).  </td></tr>
<tr>
<td>
Hidden</td><td>
Gets or sets the hidden property of text.  </td></tr>
<tr>
<td>
HighlightColor</td><td>
Gets or sets the highlight color of text.  </td></tr>
<tr>
<td>
Italic</td><td>
Gets or sets the italic style to text.  </td></tr>
<tr>
<td>
ItalicBidi</td><td>
Gets or sets the italic property for right-to-left text.  </td></tr>
<tr>
<td>
LineBreak</td><td>
Gets or sets the line break after the text.  </td></tr>
<tr>
<td>
OutLine</td><td>
Gets or sets the outline character property.  </td></tr>
<tr>
<td>
Position</td><td>
Gets or sets the text vertical position.  </td></tr>
<tr>
<td>
Shadow</td><td>
Gets or sets the shadow property of text.  </td></tr>
<tr>
<td>
SmallCaps</td><td>
Gets or sets the SmallCaps property of text.  </td></tr>
<tr>
<td>
Strikeout</td><td>
Gets or sets the strikeout style to text.  </td></tr>
<tr>
<td>
SubSuperScript</td><td>
Gets or sets the subscript/superscript mode to text.  </td></tr>
<tr>
<td>
TextBackgroundColor</td><td>
Gets or sets the text background color.  </td></tr>
<tr>
<td>
TextColor</td><td>
Gets or sets the text color.  </td></tr>
<tr>
<td>
UnderlineStyle</td><td>
Gets or sets the underline style to text.</td></tr>
<tr>
<td>
LocaleIdASCII</td><td>
Gets or sets the localeidentifier (language) of the formatted characters.</td></tr>
<tr>
<td>
LocaleIdFarEast</td><td>
Gets or sets the the localeidentifier (language) of the formatted Asian characters.</td></tr>
</table>


The following code example illustrates how to use the WCharacterFormat class.

{% highlight C# %}



//Writes different font name or font size.

string[] fontNames = new string[] {"Times New Roman", "Verdana", "Symbol", };



IWSection section = doc.AddSection();

IWParagraph paragraph;

IWTextRange textRange;



for (int j = 0, len = fontNames.Length; j < len; j++)

{

    paragraph = section.AddParagraph();

    string fontName = fontNames[j];



    for (int i = 9; i < 40; i++)

    {

        textRange = paragraph.AppendText(fontName + " " + i.ToString() + " ");

        textRange.CharacterFormat.FontSize = i;

        textRange.CharacterFormat.FontName = fontName;

        if (i > 15)

        {

            i += 5;

        }

    }

    IWTextRange txtRange2 = paragraph.AppendText(fontName + "34,5 ");

    txtRange2.CharacterFormat.FontSize = (float)34.5;

    txtRange2.CharacterFormat.FontName = fontName;

}



//Writes bold or italic or underline or strike text.

paragraph = section.AddParagraph();

textRange = paragraph.AppendText("Bold Text_Bold Text   ");

textRange.CharacterFormat.Bold = true;

textRange = paragraph.AppendText("Italic Text_Italic Text   ");

textRange.CharacterFormat.Italic = true;

textRange = paragraph.AppendText("Underline Text_Underline Text   ");

textRange.CharacterFormat.UnderlineStyle = UnderlineStyle.Dash;

textRange = paragraph.AppendText("Strike Text_Strike Text   ");

textRange.CharacterFormat.Strikeout = true;



textRange = paragraph.AppendText("Shadow Text_Shadow Text   ");

textRange.CharacterFormat.Shadow = true;



paragraph = section.AddParagraph();

paragraph = section.AddParagraph();



textRange = paragraph.AppendText("Merged Font Style Text_Merged Font Style Text");

textRange.CharacterFormat.Bold = true;

textRange.CharacterFormat.Italic = true;

textRange.CharacterFormat.Strikeout = true;

textRange.CharacterFormat.UnderlineStyle = UnderlineStyle.Dash;



//Specifies the locale for recognition of Microsoft Word.

//For the list of locale identifiers see, http://www.microsoft.com/globaldev/reference/lcid-all.mspx.



//Sets the locale identifier (language) of the formatted characters. 
textRange.CharacterFormat.LocaleIdASCII = ( short )LocaleIDs.uk_UA;



//or

textRange.CharacterFormat.LocaleIdASCII = 1093;



//Sets the locale identifier (language) of the formatted Asian characters.

textRange.CharacterFormat.LocaleIdFarEast = 2052

{% endhighlight %}

{% highlight vbnet %}



'Writes different font name or font size.

Dim fontNames As String() = New String() { "Times New Roman", "Verdana","Symbol", }



Dim section As IWSection = doc.AddSection()

Dim paragraph As IWParagraph

Dim textRange As IWTextRange



Dim j As Integer = 0

len = fontNames.Length

Do While j < len

      paragraph = section.AddParagraph()

Dim fontName As String = fontNames(j)



      For i As Integer = 9 To 39

            textRange = paragraph.AppendText(fontName and " " and i.ToString() and " ")

            textRange.CharacterFormat.FontSize = i

            textRange.CharacterFormat.FontName = fontName

            If i > 15 Then

                  i += 5

            End If

      Next i

Dim txtRange2 As IWTextRange = paragraph.AppendText(fontName and "34,5 ")

      txtRange2.CharacterFormat.FontSize = CSng(34.5)

      txtRange2.CharacterFormat.FontName = fontName

      j += 1

Loop



'Writes bold or italic or underline or strike text.

paragraph = section.AddParagraph()

textRange = paragraph.AppendText("Bold Text_Bold Text   ")

textRange.CharacterFormat.Bold = True

textRange = paragraph.AppendText("Italic Text_Italic Text   ")

textRange.CharacterFormat.Italic = True

textRange = paragraph.AppendText("Underline Text_Underline Text   ")

textRange.CharacterFormat.UnderlineStyle = UnderlineStyle.Dash

textRange = paragraph.AppendText("Strike Text_Strike Text   ")

textRange.CharacterFormat.Strikeout = True



textRange = paragraph.AppendText("Shadow Text_Shadow Text   ")

textRange.CharacterFormat.Shadow = True



paragraph = section.AddParagraph()

paragraph = section.AddParagraph()



textRange = paragraph.AppendText("Merged Font Style Text_Merged Font Style Text")

textRange.CharacterFormat.Bold = True

textRange.CharacterFormat.Italic = True

textRange.CharacterFormat.Strikeout = True

textRange.CharacterFormat.UnderlineStyle = UnderlineStyle.Dash



'Specifies the locale for recognition of Microsoft Word.

'For the list of locale identifiers, seehttp://www.microsoft.com/globaldev/reference/lcid-all.mspx.



'Sets the locale identifier (language) of the formatted characters.

textRange.CharacterFormat.LocaleIdASCII = CType(LocaleIDs.uk_UA, Short)



'or

textRange.CharacterFormat.LocaleIdASCII = 1093



'Sets the locale identifier (language) of the formatted Asian characters.

textRange.CharacterFormat.LocaleIdFarEast = 2052

{% endhighlight %}

## Paragraph Formatting Properties

###Paragraph Style

WParagraphStyle class represents paragraph style in DocIO. Paragraph Style is a pattern of paragraph formatting. You can also apply custom paragraph styles to the paragraph. The following screenshot illustrates how to achieve this in Microsoft Word.

![](Styles-and-Formatting_images/Styles-and-Formatting_img4.png)



_Figure_ _50_: _Setting Paragraph Style_



DocIO also lets you add your own paragraph styles to the document. A collection of DocIOParagraph Styles is accessible through WordDocument.Styles property. You can apply one of the built-in Word paragraph styles by using the WParagraph.ApplyStyle method. You can also use the ApplyBaseStyle method to apply the base style for the current paragraph style.

### Class Hierarchy

Style

  |

    WParagraphStyle



### Public Constructors

_Table_ _115_: _Public Constructors_

<table>
<tr>
<th>
Constructor </th><th>
Description</th></tr>
<tr>
<td>
WParagraphStyle.WParagraphStyle (IWordDocument)</td><td>
Initializes a new instance of the WParagraphStyle class.  </td></tr>
</table>


### Public Properties

_Table_ _116_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
BaseStyle</td><td>
Gets a base style of paragraph.  </td></tr>
<tr>
<td>
ParagraphFormat</td><td>
Gets formatting of paragraph.  </td></tr>
<tr>
<td>
StyleType</td><td>
Gets the type of the style.</td></tr>
</table>


### Public Methods

_Table_ _117_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
ApplyBaseStyle</td><td>
Applies base style for current style.</td></tr>
<tr>
<td>
Clone</td><td>
Clones itself.</td></tr>
</table>


The following code example illustrates how to create user-defined Paragraph Styles by using DocIO.

{% highlight C# %}



IWordDocument doc = new WordDocument();

IWParagraphStyle style = (IWParagraphStyle)doc.AddParagraphStyle("Normal");



style = (IWParagraphStyle)doc.AddParagraphStyle("UserStyle_Heading1");

style.CharacterFormat.Bold = true;

style.CharacterFormat.FontName = "Verdana";

style.CharacterFormat.FontSize = 25;

style = (IWParagraphStyle)doc.AddParagraphStyle("UserStyle_Heading2");

style.CharacterFormat.Italic = true;

style.CharacterFormat.FontName = "Verdana";

style.CharacterFormat.FontSize = 20;

style = (IWParagraphStyle)doc.AddParagraphStyle("UserStyle_Heading3");

style.CharacterFormat.Bold = true;

style.CharacterFormat.FontName = "Times New Roman";

style.CharacterFormat.FontSize = 20;

style.CharacterFormat.UnderlineStyle = UnderlineStyle.Single;



IWSection section = doc.AddSection();



for (int i = 0; i < doc.Styles.Count; i++)

{

    style = (IWParagraphStyle)doc.Styles[i];

    IWParagraph paragraph = section.AddParagraph();

    paragraph.ApplyStyle(style.Name);

    paragraph.AppendText("[ Style Applied ]: ");

    paragraph.AppendText(style.Name);

}

section.AddParagraph();

doc.Save("UserStyle.doc");

{% endhighlight %}

{% highlight vbnet %}



Dim doc As IWordDocument = New WordDocument()



Dim style As IWParagraphStyle = CType(doc.AddParagraphStyle("Normal"), IWParagraphStyle)

Dim style = CType(doc.AddParagraphStyle("UserStyle_Heading1"), IWParagraphStyle)

style.CharacterFormat.Bold = True

style.CharacterFormat.FontName = "Verdana"

style.CharacterFormat.FontSize = 25



style = CType(doc.AddParagraphStyle("UserStyle_Heading2"), IWParagraphStyle)

style.CharacterFormat.Italic = True

style.CharacterFormat.FontName = "Verdana"

style.CharacterFormat.FontSize = 20



style = CType(doc.AddParagraphStyle("UserStyle_Heading3"), IWParagraphStyle)

style.CharacterFormat.Bold = True

style.CharacterFormat.FontName = "Times New Roman"

style.CharacterFormat.FontSize = 20

style.CharacterFormat.UnderlineStyle = UnderlineStyle.Single



Dim section As IWSection = doc.AddSection()



Dim i As Integer = 0

Do While i < doc.Styles.Count

style = CType(doc.Styles(i), IWParagraphStyle)

Dim paragraph As IWParagraph = section.AddParagraph()

paragraph.ApplyStyle(style.Name)

paragraph.AppendText("[ Style Applied ]: ")

paragraph.AppendText(style.Name)

i += 1

Loop

section.AddParagraph()

doc.Save("UserStyle.doc")

{% endhighlight %}

The following code illustrates how to apply built-in paragraph styles to the Word document.

{% highlight C# %}



IWordDocument doc = new WordDocument();

doc.EnsureMinimal();



doc.LastParagraph.AppendText("Heading 1");

doc.LastParagraph.ApplyStyle(BuiltinStyle.Heading1);



doc.Save("BuiltinStyle.doc");







Dim doc As IWordDocument = New WordDocument()



doc.EnsureMinimal()



doc.LastParagraph.AppendText("Heading 1")

doc.LastParagraph.ApplyStyle(BuiltinStyle.Heading1)



doc.Save("BuiltinStyle.doc")

{% endhighlight %}

## Paragraph Format

WParagraphFormat class represents paragraph formatting in Essential DocIO. The following screenshot illustrates how to define Paragraph Format to a paragraph in Microsoft Word.

![](Styles-and-Formatting_images/Styles-and-Formatting_img5.png) 



_Figure_ _51_: _Paragraph Formatting_



### Class Hierarchy

FormatBase

           |

            WParagraphFormat 

### Public Constructors



_Table_ _118_: _Public Constructors_

<table>
<tr>
<th>
Constructors </th><th>
Description</th></tr>
<tr>
<td>
WParagraphFormat.WParagraphFormat ()</td><td>
Initializes a new instance of WParagraphFormat class. </td></tr>
<tr>
<td>
WParagraphFormat.WParagraphFormat (IWordDocument)</td><td>
Initializes a new instance of WParagraphFormat class.</td></tr>
</table>

### Public Properties

_Table_ _119_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
AfterSpacing</td><td>
Gets or sets the spacing (in points) after the paragraph.</td></tr>
<tr>
<td>
BackColor</td><td>
Gets or sets the background color of the paragraph.</td></tr>
<tr>
<td>
BeforeSpacing</td><td>
Gets or sets the spacing (in points) before the paragraph.</td></tr>
<tr>
<td>
Bidi</td><td>
Gets or sets the right-to-left property of the paragraph.</td></tr>
<tr>
<td>
Borders</td><td>
Gets collection of borders in the paragraph.</td></tr>
<tr>
<td>
ColumnBreakAfter</td><td>
True if a column break is forced after the paragraph.</td></tr>
<tr>
<td>
FirstLineIndent</td><td>
Gets or sets the first paragraph line indent.</td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Gets or sets the horizontal alignment for the paragraph.  </td></tr>
<tr>
<td>
Keep</td><td>
True if all lines in the paragraph are to remain on the same page.  </td></tr>
<tr>
<td>
KeepFollow</td><td>
True if the paragraph is to remain on the same page as the paragraph that follows it.  </td></tr>
<tr>
<td>
FirstLineIndent</td><td>
Gets or sets the first paragraph line indent (in points).</td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Gets or sets the horizontal alignment for the paragraph.  </td></tr>
<tr>
<td>
Keep</td><td>
True if all lines in the paragraph are to remain on the same page.  </td></tr>
<tr>
<td>
KeepFollow</td><td>
True if the paragraph is to remain on the same page as the paragraph that follows it.  </td></tr>
<tr>
<td>
LeftIndent</td><td>
Gets or sets the value that represents the left indent for paragraph (in points). </td></tr>
<tr>
<td>
LineSpacing</td><td>
Gets or sets the line spacing property of the paragraph   (in points) that specifies the space between two paragraphs.</td></tr>
<tr>
<td>
LineSpacingRule</td><td>
Gets or sets the line spacing rule property of the paragraph.  </td></tr>
<tr>
<td>
PageBreakAfter</td><td>
True if a page break is forced after the paragraph.  </td></tr>
<tr>
<td>
PageBreakBefore</td><td>
True if a page break is forced before the paragraph.</td></tr>
<tr>
<td>
RightIndent</td><td>
Gets or sets the right indent for paragraph (in points). </td></tr>
<tr>
<td>
MirrorIndents</td><td>
Gets or sets a value indicating whether the indentation type is mirror indents (Microsoft Word 2007 and 2010 specific property).</td></tr>
</table>


{% highlight C# %}



para.ParagraphFormat.OutlineLevel = OutlineLevel.Level8;

{% endhighlight %}

{% highlight vbnet %}



para.ParagraphFormat.OutlineLevel = OutlineLevel.Level8

{% endhighlight %}

## Tabs

Tabs class represents a tab collection within a paragraph. Tab class represents a single tab within the tab collection.

### Class Hierarchy

WParagraphFormat

   |

    Tabs

### Public Properties

_Table_ _120_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
Justification</td><td>
Gets or sets the tab justification.</td></tr>
<tr>
<td>
TabLeader</td><td>
Gets or sets the tab leader.</td></tr>
<tr>
<td>
Position</td><td>
Gets or sets the tab position.</td></tr>
<tr>
<td>
DeletePostion</td><td>
Gets or sets the Clear tab position.</td></tr>
</table>


### Public Methods



_Table_ _121_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
AddTab()</td><td>
Adds default tab to the paragraph.</td></tr>
<tr>
<td>
AddTab(float position)</td><td>
Adds tab at the specfied position.</td></tr>
<tr>
<td>
AddTab(float position, TabJustification justification TabLeader leader)</td><td>
Adds tab at specified location with the specified tab justification and leader.</td></tr>
<tr>
<td>
RemoveAt(int index)</td><td>
Removes tab at specified index from the tab collection.</td></tr>
<tr>
<td>
RemoveByTabPosition(float position)</td><td>
Removes tab at specified tab position from the tab collection.</td></tr>
</table>


The following code example illustrates how to add the tab to a paragraph and delete the tab from a paragraph.

{% highlight C# %}



//Creates a new instance for a Word document.

WordDocument document = new WordDocument();

//Adds one section to the document.

IWSection section=document .AddSection ();

//Adds one paragraph to the section.

IWParagraph paragraph=section.AddParagraph ();



//Adds tab stop at the postion 36 with tab justification [left] and tab leader[dotted].

paragraph .ParagraphFormat .Tabs.AddTab(36,TabJustification .Left ,Syncfusion.DocIO.DLS.TabLeader .Dotted );

//Adds tab stop at the postion 80 with tab justification[Right] and tab leader[Hyphenated].

paragraph .ParagraphFormat .Tabs.AddTab(80,TabJustification .Right ,Syncfusion.DocIO.DLS.TabLeader.Hyphenated  );

//Adds tab stop at the postion 144 with tab justification[Center] and with no tab leader.

paragraph .ParagraphFormat .Tabs.AddTab(144,TabJustification .Centered ,Syncfusion.DocIO.DLS.TabLeader .NoLeader );



//Removes tab at index 1 from the tab collection.

paragraph .ParagraphFormat .Tabs .RemoveAt (1);

//Removes tab at the position 144.

paragraph .ParagraphFormat .Tabs .RemoveByTabPosition (144);

//Appends tab character.

paragraph.AppendText("\t");

//Appends Text to the paragraph.

paragraph.AppendText("Tabs are added and removed");

//Saves a Word document.

document .Save ("Sample.doc",FormatType.Doc  );

{% endhighlight %}

{% highlight vbnet %}



'Creates a new instance for a Word document.

Dim document As New WordDocument()

'Adds one section to the document.

Dim section As IWSection = document.AddSection()

'Adds one paragraph to the section.

Dim paragraph As IWParagraph = section.AddParagraph()



'Adds tab stop at the postion 36 with tab justification[left] and tab leader[dotted].

paragraph.ParagraphFormat.Tabs.AddTab(36, TabJustification.Left, Syncfusion.DocIO.DLS.TabLeader.Dotted)

'Adds tab stop at the postion 80 with tab justification[Right] and tab leader[Hyphenated].

paragraph.ParagraphFormat.Tabs.AddTab(80, TabJustification.Right, Syncfusion.DocIO.DLS.TabLeader.Hyphenated)

'Adds tab stop at the postion 144 with tab justification[Center] and with no tab leader.

paragraph.ParagraphFormat.Tabs.AddTab(144, TabJustification.Centered, Syncfusion.DocIO.DLS.TabLeader.NoLeader)



'Removes tab at index 1 from the tab collection.

paragraph.ParagraphFormat.Tabs.RemoveAt(1)

'Removes tab at the position 144.

paragraph.ParagraphFormat.Tabs.RemoveByTabPosition(144)

'Appends tab character.

paragraph.AppendText("\t")

'Appends Text to the paragraph.

paragraph.AppendText("Tabs are added and removed")

'Saves a Word document.

document.Save("Sample.doc", FormatType.Doc)

{% endhighlight %}

## List Style Properties

List is one of the popular features available in Word document. It lets you arrange the contents in an arranged and sequential representation. This section elaborates how DocIO handles List and list items effectively.

### List Style

ListStyle class represents list properties in the Paragraph style. Collection of list styles is accessible through the WordDocument.ListStyles property.

DocIO allows you to create your own list style definition that can be applied to any list. To add a list style by using DocIO, use the WordDocument.AddListStyle method. Every list style has its own name. You can use the Name property to access the style names. The following are possible list types in DocIO.

* Numbered
* Bulleted

You can specify the type of the list style by using the ListType property. Every ListStyle instance contains the collection of list levels. This collection can contain from one to nine levels (maximum number of list levels). Collection of list levels is accessible through the Levels property. This property returns the ListLevelCollection instance. List Level Collection (ListLevelCollection class) contains objects of the WListLevel class.

The following screenshot demonstrates how to create list styles by using Microsoft Word.

![](Styles-and-Formatting_images/Styles-and-Formatting_img6.png) 



_Figure_ _52_: _Creating List Styles_



### Public Properties

_Table_ _122_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
Levels</td><td>
Gets the list levels collection.  </td></tr>
<tr>
<td>
ListType</td><td>
Gets or sets list type.  </td></tr>
<tr>
<td>
Name</td><td>
Gets the style name.  </td></tr>
<tr>
<td>
StyleType</td><td>
Gets the type of the style.  </td></tr>
<tr>
<td>
ListStyle.ListStyle (IWordDocument, ListType)</td><td>
Initializes a new instance of the ListStyle class.</td></tr>
</table>

### Public Methods

_Table_ _123_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
Clone</td><td>
Clones current style object.  </td></tr>
<tr>
<td>
CreateEmptyListStyle</td><td>
Static method. Creates empty list style.</td></tr>
</table>


WListLevel class represents list level in Essential DocIO. By using the WListLevel class, you can customize the list level options.

### Public Constructor

_Table_ _124_: _Public Constructors_

<table>
<tr>
<th>
Constructor </th><th>
Description</th></tr>
<tr>
<td>
WListLevel.WListLevel (ListStyle)</td><td>
Initializes new instance of WListLevel class.</td></tr>
</table>
Public Methods

_Table_ _125_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
Clone</td><td>
Clones this instance.  </td></tr>
<tr>
<td>
GetListItemText</td><td>
Gets list symbol for specified item index.</td></tr>
</table>
Public Properties

_Table_ _126_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
BulletCharacter</td><td>
Gets or sets bullet pattern.  </td></tr>
<tr>
<td>
CharacterFormat</td><td>
Gets or sets the character formats of list symbol.  </td></tr>
<tr>
<td>
FollowCharacter</td><td>
Gets or sets the type of character following the number text for the paragraph.  </td></tr>
<tr>
<td>
IsLegalStyleNumbering</td><td>
Gets or sets the ArabicNumberFormat property ( true if the level turns all inherited numbers to arabic, false if it preserves their number format code ).  </td></tr>
<tr>
<td>
NoRestartByHigher</td><td>
True if the level's number sequence is not restarted by higher (more significant) levels in the list.  </td></tr>
<tr>
<td>
NumberAlignment</td><td>
Gets or sets the alignment (left, right, or centered) of the paragraph number.  </td></tr>
<tr>
<td>
NumberPosition</td><td>
Gets or sets the number/bullet position for current listlevel (in points).</td></tr>
<tr>
<td>
NumberPrefix</td><td>
Gets or sets the prefix pattern for numbered level.  </td></tr>
<tr>
<td>
NumberSuffix</td><td>
Gets or sets the suffix pattern for numbered level.  </td></tr>
<tr>
<td>
ParagraphFormat</td><td>
Gets or sets the paragraph format of list level.  </td></tr>
<tr>
<td>
PatternType</td><td>
Gets or sets the list numbering type.  </td></tr>
<tr>
<td>
StartAt</td><td>
Gets or sets the start at value.  </td></tr>
<tr>
<td>
TabSpaceAfter</td><td>
Gets or sets the spacing after list level's number or bullet ( tab position if follow character is tab ).  </td></tr>
<tr>
<td>
TextPosition</td><td>
Gets or sets the the left listlevel indent (in points).</td></tr>
<tr>
<td>
UsePrevLevelPattern</td><td>
When true, number generated will include previous levels (used for legal numbering).  </td></tr>
</table>


The following code example illustrates how to create user-defined list styles and apply it to a paragraph.

{% highlight C# %}



//User bullet list style.

ListStyle bulStyle = doc.AddListStyle(ListType.Bulleted, "BulletStyle");

WListLevel bulLevel1 = bulStyle.Levels[0];

bulLevel1.FollowCharacter = FollowCharacterType.Space;

bulLevel1.TextPosition = 40f;

bulLevel1.NumberAlignment = ListNumberAlignment.Right;



WListLevel bulLevel2 = bulStyle.Levels[1];

bulLevel2.FollowCharacter = FollowCharacterType.Space;

bulLevel2.TextPosition = 60f;

bulLevel2.NumberAlignment = ListNumberAlignment.Right;

bulLevel2.TabSpaceAfter = 40f;



paragraph = section.AddParagraph();

paragraph.AppendText("First bulleted ( level 0 )");

paragraph.ListFormat.ApplyStyle("BulletStyle");



paragraph = section.AddParagraph();

paragraph.AppendText("Level 1");

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.IncreaseIndentLevel();





paragraph = section.AddParagraph();

paragraph.AppendText("Level 0");

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.DecreaseIndentLevel();



//User numbered list style.

ListStyle newStyle = doc.AddListStyle(ListType.Numbered, "NewStyle");

WListLevel listLevelNew = newStyle.Levels[0];

listLevelNew.FollowCharacter = FollowCharacterType.Tab;

listLevelNew.TextPosition = 80f;

listLevelNew.NumberAlignment = ListNumberAlignment.Right;

listLevelNew.TabSpaceAfter = 40f;

listLevelNew.StartAt = 2;

listLevelNew.NumberPrefix = ">>";

listLevelNew.NumberSufix = "<<";

listLevelNew.CharacterFormat.FontSize = 15;

listLevelNew.CharacterFormat.TextColor = Color.Blue;



WListLevel listLevelNew1 = newStyle.Levels[1];

listLevelNew1.IsLegalStyleNumbering = true;



WListLevel listLevelNew2 = newStyle.Levels[2];

listLevelNew1.NoRestartByHigher = true;



paragraph = section.AddParagraph();

paragraph.AppendText("First Numbered ( level 0 )");

paragraph.ListFormat.ApplyStyle("NewStyle");



paragraph = section.AddParagraph();

paragraph.AppendText("Level 1");

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.IncreaseIndentLevel();



paragraph = section.AddParagraph();

paragraph.AppendText("Level 0");

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.ListLevelNumber = 0;

{% endhighlight %}

{% highlight vbnet %}



'User bullet list style.

Dim bulStyle As ListStyle = doc.AddListStyle(ListType.Bulleted, "BulletStyle")

Dim bulLevel1 As WListLevel = bulStyle.Levels(0)

bulLevel1.FollowCharacter = FollowCharacterType.Space

bulLevel1.TextPosition = 40f

bulLevel1.NumberAlignment = ListNumberAlignment.Right



Dim bulLevel2 As WListLevel = bulStyle.Levels(1)

bulLevel2.FollowCharacter = FollowCharacterType.Space

bulLevel2.TextPosition = 60f

bulLevel2.NumberAlignment = ListNumberAlignment.Right

bulLevel2.TabSpaceAfter = 40f



paragraph = section.AddParagraph()

paragraph.AppendText("First bulleted ( level 0 )")

paragraph.ListFormat.ApplyStyle("BulletStyle")



paragraph = section.AddParagraph()

paragraph.AppendText("Level 1")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.IncreaseIndentLevel()





paragraph = section.AddParagraph()

paragraph.AppendText("Level 0")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.DecreaseIndentLevel()



'User numbered list style.

Dim newStyle As ListStyle = doc.AddListStyle(ListType.Numbered, "NewStyle")

Dim listLevelNew As WListLevel = newStyle.Levels(0)

listLevelNew.FollowCharacter = FollowCharacterType.Tab

listLevelNew.TextPosition = 80f

listLevelNew.NumberAlignment = ListNumberAlignment.Right

listLevelNew.TabSpaceAfter = 40f

listLevelNew.StartAt = 2

listLevelNew.NumberPrefix = ">>"

listLevelNew.NumberSufix = "<<"

listLevelNew.CharacterFormat.FontSize = 15

listLevelNew.CharacterFormat.TextColor = Color.Blue



listLevelNew1 As WListLevel = newStyle.Levels(1)

listLevelNew1.IsLegalStyleNumbering = True



listLevelNew2 As WListLevel = newStyle.Levels(2)

listLevelNew1.NoRestartByHigher = True



paragraph = section.AddParagraph()

paragraph.AppendText("First Numbered ( level 0 )")

paragraph.ListFormat.ApplyStyle("NewStyle")



paragraph = section.AddParagraph()

paragraph.AppendText("Level 1")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.IncreaseIndentLevel()



paragraph = section.AddParagraph()

paragraph.AppendText("Level 0")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.ListLevelNumber = 0

{% endhighlight %}

## List Format

WListFormat class specifies the formatting for DocIO list paragraph. The type of the list is specified by using the ListType property of WListFormat. ListLevelNumber property specifies the level number for the list paragraph. CurrentListStyle property specifies the list style, applied for the current list paragraph. CurrentListLevel property returns the instance of the WListLevel type, which specifies the formatting for the list level (paragraph). For example, a value that the list starts at (for numbered lists), list symbols, alignment of list text, and so forth.



* To apply default bullet or numbered style to the paragraph, use ApplyDefBulletStyle or ApplyDefNumberedStyle method.
* To apply custom style, use ApplyStyle method.
* ContinueListNumbering method is used to continue previous list numbering.
* Use IncreaseIndentLevel or DecreaseIndentLevel to increase or decrease indent for the level.
* To remove list from the paragraph, use RemoveList method.

### Class Hierarchy

FormatBase

|

            WListFormat 

### Public Constructor

_Table_ _127_: _Public Constructors_

<table>
<tr>
<th>
Constructor </th><th>
Description</th></tr>
<tr>
<td>
WListFormat.WListFormat (IWParagraph)</td><td>
Initializes new instance of WListFormat class.</td></tr>
</table>

 Public Properties

_Table_ _128_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
CurrentListLevel</td><td>
Gets or sets the paragraph's ListLevel.</td></tr>
<tr>
<td>
CurrentListStyle</td><td>
Gets the paragraph's list style.</td></tr>
<tr>
<td>
CustomStyleName</td><td>
Gets or sets the name of custom style.</td></tr>
<tr>
<td>
ListLevelNumber</td><td>
Gets or sets the list nesting level.</td></tr>
<tr>
<td>
ListType</td><td>
Gets or sets the type of the list.</td></tr>
<tr>
<td>
RestartNumbering</td><td>
Gets or sets whether numbering of the list must restart from previous list.</td></tr>
</table>

### Public Methods

_Table_ _129_: _Public Methods_

<table>
<tr>
<th>
Methods</th><th>
Description</th></tr>
<tr>
<td>
ApplyDefBulletStyle</td><td>
Applies default bullet style for current paragraph.  </td></tr>
<tr>
<td>
ApplyDefNumberedStyle</td><td>
Applies default numbered style for current paragraph.  </td></tr>
<tr>
<td>
ApplyStyle</td><td>
Gets or sets the name of custom style.  </td></tr>
<tr>
<td>
ContinueListNumbering</td><td>
Continues last list.  </td></tr>
<tr>
<td>
DecreaseIndentLevel</td><td>
Decreases level indent.  </td></tr>
<tr>
<td>
IncreaseIndentLevel</td><td>
Increases level indent.  </td></tr>
<tr>
<td>
RemoveList</td><td>
Removes the list from current paragraph.  </td></tr>
</table>


The following code example illustrates how to use the WListFormat and List Styles in DocIO.

{% highlight C# %}



//Writes default numbered list.         

IWParagraph paragraph = section.AddParagraph();

paragraph.AppendText( "First Numbered ( level 0 )" );     

paragraph.ListFormat.ApplyDefNumberedStyle();



paragraph = section.AddParagraph();

paragraph.AppendText( "Level 1" );

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.IncreaseIndentLevel();



paragraph = section.AddParagraph();

paragraph.AppendText( "Level 0" );

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.DecreaseIndentLevel();



section.AddParagraph();

section.AddParagraph();



//Writes default bulleted list 

paragraph = section.AddParagraph();

paragraph.AppendText( "First bulleted ( level 0 )" );     

paragraph.ListFormat.ApplyDefBulletStyle();



paragraph = section.AddParagraph();

paragraph.AppendText( "Level 1" );

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.IncreaseIndentLevel();



paragraph = section.AddParagraph();

paragraph.AppendText( "Level 0" );

paragraph.ListFormat.ContinueListNumbering();

paragraph.ListFormat.DecreaseIndentLevel();



section.AddParagraph();

section.AddParagraph();



//Writes mixed bulleted and numbered list.

ListStyle myStyle = doc.AddListStyle( ListType.Numbered, "UserStyle");

WListLevel listLevel1 = myStyle.Levels[ 0 ];

listLevel1.FollowCharacter = FollowCharacterType.Tab;

listLevel1.TextPosition = 80f;

listLevel1.NumberAlignment = ListNumberAlignment.Right;

listLevel1.TabSpaceAfter = 40f;

listLevel1.StartAt = 3;

listLevel1.NumberPrefix = "(((";

listLevel1.NumberSufix = "***.";



paragraph = section.AddParagraph();

paragraph.AppendText( "First numbered" );

paragraph.ListFormat.ApplyStyle( "UserStyle" );



paragraph = section.AddParagraph();

ListStyle bulletStyle = doc.AddListStyle( ListType.Bulleted, "UserStyle1");

WListLevel level = bulletStyle.Levels[ 0 ];

level.NumberPosition = 30f;

level.TabSpaceAfter = 15f;

level.FollowCharacter = FollowCharacterType.Tab;



paragraph.AppendText( "First bullet" );     

paragraph.ListFormat.ApplyStyle( "UserStyle1" );    



paragraph = section.AddParagraph();

paragraph.AppendText( "Bulleted level 1" );     

paragraph.ListFormat.ContinueListNumbering();



paragraph = section.AddParagraph();

paragraph.AppendText( "Numbered level 0 again" );            

paragraph.ListFormat.ApplyStyle( "UserStyle" );

section.AddParagraph();

section.AddParagraph();

{% endhighlight %}

{% highlight vbnet %}



'Writes default numbered list.         

Dim paragraph As IWParagraph = section.AddParagraph()

paragraph.AppendText("First Numbered ( level 0 )")

paragraph.ListFormat.ApplyDefNumberedStyle()



paragraph = section.AddParagraph()

paragraph.AppendText("Level 1")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.IncreaseIndentLevel()



paragraph = section.AddParagraph()

paragraph.AppendText("Level 0")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.DecreaseIndentLevel()



section.AddParagraph()

section.AddParagraph()



'Writes default bulleted list. 

paragraph = section.AddParagraph()

paragraph.AppendText("First bulleted ( level 0 )")

paragraph.ListFormat.ApplyDefBulletStyle()



paragraph = section.AddParagraph()

paragraph.AppendText("Level 1")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.IncreaseIndentLevel()



paragraph = section.AddParagraph()

paragraph.AppendText("Level 0")

paragraph.ListFormat.ContinueListNumbering()

paragraph.ListFormat.DecreaseIndentLevel()



section.AddParagraph()

section.AddParagraph()



'Writes mixed bulleted and numbered list.

Dim myStyle As ListStyle = doc.AddListStyle(ListType.Numbered, "UserStyle")

Dim listLevel1 As WListLevel = myStyle.Levels(0)

listLevel1.FollowCharacter = FollowCharacterType.Tab

listLevel1.TextPosition = 80f

listLevel1.NumberAlignment = ListNumberAlignment.Right

listLevel1.TabSpaceAfter = 40f

listLevel1.StartAt = 3

listLevel1.NumberPrefix = "((("

listLevel1.NumberSufix = "***."



paragraph = section.AddParagraph()

paragraph.AppendText("First numbered")

paragraph.ListFormat.ApplyStyle("UserStyle")



paragraph = section.AddParagraph()

Dim bulletStyle As ListStyle = doc.AddListStyle(ListType.Bulleted,"UserStyle1")

Dim level As WListLevel = bulletStyle.Levels(0)

level.NumberPosition = 30f

level.TabSpaceAfter = 15f

level.FollowCharacter = FollowCharacterType.Tab



paragraph.AppendText("First bullet")

paragraph.ListFormat.ApplyStyle("UserStyle1")



paragraph = section.AddParagraph()

paragraph.AppendText("Bulleted level 1")

paragraph.ListFormat.ContinueListNumbering()



paragraph = section.AddParagraph()

paragraph.AppendText("Numbered level 0 again")

paragraph.ListFormat.ApplyStyle("UserStyle")

section.AddParagraph()

section.AddParagraph()

{% endhighlight %}

## Text Box Format

Text Box control is a container that provides support to insert text, images, and so on. DocIO supports text box and its methods. The WTextBoxFormat class specifies formatting for the Text Box.

![](Styles-and-Formatting_images/Styles-and-Formatting_img7.png) 



_Figure_ _53_: Formatting Text Box_



## Position

Absolute positioning of Text Box is defined by using the VerticalPosition and HorizontalPosition properties. Measure unit is point. Relative positioning is defined by using the HorizontalAlignment and VerticalAlignment properties.



HorizontalAlignment returns an instance of type, ShapeHorizontalAlignment. The following are the variants for setting the Horizontal alignment of a picture.

* None: No horizontal alignment.
* Left: Left horizontal alignment.
* Center: Center horizontal alignment.
* Right: Right horizontal alignment.
* Inside: Inside horizontal alignment.
* Outside: Outside horizontal alignment.

VerticalAlignment returns an instance of type, ShapeVerticalAlignment. The following are the variants for setting the Vertical alignment of a picture.

* Bottom: Picture is aligned to the bottom of the reference origin.
* Center: Picture is centered relative to the reference origin.
* Inline: Inline vertical alignment.
* Inside: Inside vertical alignment.
* None: Picture is explicitly positioned by using position properties.
* Outside: Outside vertical alignment.
* Top: Picture is aligned to the top of the reference origin.

HorizontalOrigin and VerticalOrigin properties define the reference origin, which is used for relative positioning of the picture.

HorizontalOrigin property returns a value of type, HorizontalOrigin. The following are the variants for setting the Horizontal origin of a picture.

* Margin
* Page
* Column
* Character

VerticalOrigin property returns a value of type, VerticalOrigin. The following are the variants for setting the Vertical origin of a picture. 

* Margin
* Page
* Paragraph
* Line

## Border Style

You can specify the style of the border line of the text box by using the LineStyle property. It provides the following options.

* Simple
* Double
* ThickThin
* ThinThick
* Triple 

### Class Hierarchy

 FormatBase

            |

            WTextBoxFormat

### Public Constructor

_Table_ _130_: _Public Constructors_

<table>
<tr>
<th>
Constructor Name</th><th>
Description</th></tr>
<tr>
<td>
WTextBoxFormat.WTextBoxFormat (IWordDocument)</td><td>
Initializes a new instance of the WTextBoxFormat class.</td></tr>
</table>


### Public Properties

_Table_ _131_: _Public Properties_

<table>
<tr>
<th>
Properties</th><th>
Description</th></tr>
<tr>
<td>
FillColor</td><td>
Gets or sets the fill color for textbox.</td></tr>
<tr>
<td>
Height</td><td>
Gets or sets the textbox height (in points). </td></tr>
<tr>
<td>
HorizontalAlignment</td><td>
Gets or sets the horizontal alignment of textbox. </td></tr>
<tr>
<td>
HorizontalOrigin</td><td>
Gets or sets the horizontal origin.  </td></tr>
<tr>
<td>
HorizontalPosition</td><td>
Gets or sets the horizontal position of textbox (in points).  </td></tr>
<tr>
<td>
LineColor</td><td>
Gets or sets the line color.  </td></tr>
<tr>
<td>
LineDashing</td><td>
Gets or sets the line dashing for textbox.  </td></tr>
<tr>
<td>
LineStyle</td><td>
Gets or sets the linestyle of textbox.  </td></tr>
<tr>
<td>
LineWidth</td><td>
Gets or sets the line width of textbox (in points).  </td></tr>
<tr>
<td>
NoLine</td><td>
Gets or sets the value that specifies if there is a line around textbox shape.</td></tr>
<tr>
<td>
TextWrappingStyle</td><td>
Gets or sets the text Wrapping style.</td></tr>
<tr>
<td>
TextWrappingType</td><td>
Gets or sets the wrapping type for textbox.  </td></tr>
<tr>
<td>
VerticalAlignment</td><td>
Gets or sets the vertical alignment of textbox.  </td></tr>
<tr>
<td>
VerticalOrigin</td><td>
Gets or sets the vertical origin.  </td></tr>
<tr>
<td>
VerticalPosition</td><td>
Gets or sets  the textbox vertical position (in points).  </td></tr>
<tr>
<td>
Width</td><td>
Gets or sets  the textbox width (in points).  </td></tr>
</table>

### Public Methods

_Table_ _132_: _Public Methods_

<table>
<tr>
<th>
Method </th><th>
Description</th></tr>
<tr>
<td>
Clone</td><td>
Clones textbox format.</td></tr>
</table>


The following code example illustrates how to use the WTextBox and TextBoxFormat classes.

{% highlight C# %}



IWordDocument doc = new WordDocument();

IWSection section = doc.AddSection();

IWParagraph paragraph = section.AddParagraph();

section.PageSetup.DifferentFirstPage = true;

section.PageSetup.DifferentOddAndEvenPages = true;



//Main doc textboxes.

paragraph.AppendText("Testing textboxes");

//1 text box.

IWTextBox mainTextbox = paragraph.AppendTextBox(150, 110);

mainTextbox.TextBoxBody.AddParagraph().AppendText("Textbox text 1");

mainTextbox.TextBoxFormat.FillColor = System.Drawing.Color.Blue;

mainTextbox.TextBoxFormat.LineDashing = LineDashing.LongDashDotDotGEL;

mainTextbox.TextBoxFormat.LineWidth = 4.0f;

//2 text box.

IWTextBox mainTextbox1 = paragraph.AppendTextBox(150, 100);

mainTextbox1.TextBoxFormat.VerticalPosition = 500;

mainTextbox1.TextBoxBody.AddParagraph().AppendText("Another textbox");

mainTextbox1.TextBoxFormat.FillColor = System.Drawing.Color.Yellow;

mainTextbox1.TextBoxFormat.LineDashing = LineDashing.DashGEL;

mainTextbox1.TextBoxFormat.LineWidth = 3.75f;

mainTextbox1.TextBoxFormat.TextWrappingStyle = TextWrappingStyle.Through;

mainTextbox1.TextBoxFormat.TextWrappingType = TextWrappingType.Both;

mainTextbox1.TextBoxFormat.HorizontalAlignment =

ShapeHorizontalAlignment.Center;

mainTextbox1.TextBoxFormat.VerticalAlignment = ShapeVerticalAlignment.Bottom;



//Header or footer text boxes.

paragraph = new WParagraph(doc);

paragraph.AppendText("Hello textboxes");

IWTextBox textbox = paragraph.AppendTextBox(20, 50);

textbox.TextBoxBody.AddParagraph().AppendText("Header textbox");

textbox.TextBoxFormat.FillColor = System.Drawing.Color.Blue;

textbox.TextBoxFormat.LineDashing = LineDashing.LongDashDotDotGEL;

textbox.TextBoxFormat.LineWidth = 4.0f;



IWTextBox textbox1 = paragraph.AppendTextBox(250, 50);

textbox1.TextBoxBody.AddParagraph().AppendText("Header textbox 2");

textbox1.TextBoxFormat.FillColor = System.Drawing.Color.Tomato;

textbox1.TextBoxFormat.VerticalPosition = 250;

textbox1.TextBoxFormat.LineStyle = TextBoxLineStyle.Triple;

textbox1.TextBoxFormat.LineDashing = LineDashing.LongDashGEL;

textbox1.TextBoxFormat.LineWidth = 6.0f;

textbox1.TextBoxFormat.NoLine = true;           



section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph);



paragraph = new WParagraph(doc);

paragraph.AppendText("Hello footer textbox");

IWTextBox textbox2 = paragraph.AppendTextBox(120, 100);

textbox2.TextBoxFormat.VerticalPosition = 5;

textbox2.TextBoxBody.AddParagraph().AppendText("Footer textbox");

textbox2.TextBoxFormat.FillColor = System.Drawing.Color.Yellow;

textbox2.TextBoxFormat.LineDashing = LineDashing.DashGEL;

textbox2.TextBoxFormat.LineWidth = 3.75f;

textbox2.TextBoxFormat.TextWrappingStyle = TextWrappingStyle.Square;

textbox2.TextBoxFormat.HorizontalAlignment = ShapeHorizontalAlignment.Left;

textbox2.TextBoxFormat.VerticalAlignment = ShapeVerticalAlignment.Bottom;

section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph);

doc.Save("TextBoxes.doc");

{% endhighlight %}

{% highlight vbnet %}



Dim doc As IWordDocument = New WordDocument()

Dim section As IWSection = doc.AddSection()

Dim paragraph As IWParagraph = section.AddParagraph()

section.PageSetup.DifferentFirstPage = True

section.PageSetup.DifferentOddAndEvenPages = True



'Main doc text boxes.

paragraph.AppendText("Testing textboxes")



'1 text box.

Dim mainTextbox As IWTextBox = paragraph.AppendTextBox(150, 110)

mainTextbox.TextBoxBody.AddParagraph().AppendText("Textbox text 1")

mainTextbox.TextBoxFormat.FillColor = System.Drawing.Color.Blue

mainTextbox.TextBoxFormat.LineDashing = LineDashing.LongDashDotDotGEL

 mainTextbox.TextBoxFormat.LineWidth = 4.0f



'2 text box.

Dim mainTextbox1 As IWTextBox = paragraph.AppendTextBox(150, 100)

mainTextbox1.TextBoxFormat.VerticalPosition = 500

mainTextbox1.TextBoxBody.AddParagraph().AppendText("Another textbox")

mainTextbox1.TextBoxFormat.FillColor = System.Drawing.Color.Yellow

mainTextbox1.TextBoxFormat.LineDashing = LineDashing.DashGEL

mainTextbox1.TextBoxFormat.LineWidth = 3.75f

mainTextbox1.TextBoxFormat.TextWrappingStyle = TextWrappingStyle.Through

mainTextbox1.TextBoxFormat.TextWrappingType = TextWrappingType.Both

mainTextbox1.TextBoxFormat.HorizontalAlignment = ShapeHorizontalAlignment.Center

mainTextbox1.TextBoxFormat.VerticalAlignment = ShapeVerticalAlignment.Bottom



'Header or footer text boxes.

paragraph = New WParagraph(doc)

paragraph.AppendText("Hello textboxes")

Dim textbox As IWTextBox = paragraph.AppendTextBox(20, 50)

textbox.TextBoxBody.AddParagraph().AppendText("Header textbox")

textbox.TextBoxFormat.FillColor = System.Drawing.Color.Blue

textbox.TextBoxFormat.LineDashing = LineDashing.LongDashDotDotGEL

textbox.TextBoxFormat.LineWidth = 4.0f



Dim textbox1 As IWTextBox = paragraph.AppendTextBox(250, 50)

textbox1.TextBoxBody.AddParagraph().AppendText("Header textbox 2")

textbox1.TextBoxFormat.FillColor = System.Drawing.Color.Tomato

textbox1.TextBoxFormat.VerticalPosition = 250

textbox1.TextBoxFormat.LineStyle = TextBoxLineStyle.Triple

textbox1.TextBoxFormat.LineDashing = LineDashing.LongDashGEL

textbox1.TextBoxFormat.LineWidth = 6.0f

textbox1.TextBoxFormat.NoLine = True



section.HeadersFooters.FirstPageHeader.Paragraphs.Add(paragraph)



paragraph = New WParagraph(doc)

paragraph.AppendText("Hello footer textbox")

Dim textbox2 As IWTextBox = paragraph.AppendTextBox(120, 100)

Private textbox2.TextBoxFormat.VerticalPosition = 5

textbox2.TextBoxBody.AddParagraph().AppendText("Footer textbox")

textbox2.TextBoxFormat.FillColor = System.Drawing.Color.Yellow

textbox2.TextBoxFormat.LineDashing = LineDashing.DashGEL

textbox2.TextBoxFormat.LineWidth = 3.75f

textbox2.TextBoxFormat.TextWrappingStyle = TextWrappingStyle.Square

textbox2.TextBoxFormat.HorizontalAlignment = ShapeHorizontalAlignment.Left

textbox2.TextBoxFormat.VerticalAlignment = ShapeVerticalAlignment.Bottom

section.HeadersFooters.FirstPageFooter.Paragraphs.Add(paragraph)

doc.Save("TextBoxes.doc")

{% endhighlight %}

## Importing and Exporting

This section lets you to deal with the conversion process of one file format to another using Essential DocIO. The following are the possible conversions using Essential DocIO.

* Load and Save RTF document.
* Load and Save HTML document.
* Load and Save Text documents.
* Saving a Word document as PDF.
* Saving a Word document as EPub file.
* Saving a Word document as Image.

### Loading and Saving an RTF Document 


This section shows you how to load and save an RTFdocument using Essential DocIO. You can create new Word document or open an existing Word document and save to RTF format. 

The following code example illustrates how to open an RTF file.

{% highlight c# %}

//Opens the RTF file through WordDocument constructor.WordDocument doc = new WordDocument("Sample.rtf", FormatType.Rtf);

{% endhighlight %}

{% highlight vbnet %}

'Opens the RTF file through WordDocument constructor.Dim doc As New WordDocument("Sample.rtf", FormatType.Rtf)

{% endhighlight %}

The following code example lets you to save as RTF.

{% highlight c# %}

doc.Save("samplertf.rtf",FormatType.Rtf );
{% endhighlight %}

{% highlight vbnet %}
doc.Save("samplertf.rtf",FormatType.Rtf )</td></tr>
{% endhighlight %}


### Supported and Unsupported Elements

### DocIO Supports the following document elements.

_Table_ _133_: Document Elements_

<table>
<tr>
<th>
Element</th><th>
Support in RTF Reader</th><th>
Support in RTF Writer</th><th>
Known Limitations</th></tr>
<tr>
<td>
Document Properties</td><td>
Yes</td><td>
No</td><td>
-</td></tr>
<tr>
<td>
Paragraph</td><td>
Yes</td><td>
Yes</td><td>
Revision tracking</td></tr>
<tr>
<td>
Table</td><td>
Yes</td><td>
Yes</td><td>
3D border for the tables is not supported</td></tr>
<tr>
<td>
Picture</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Header / Footer</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Field</td><td>
Yes</td><td>
Yes</td><td>
Fields supported in Doc and Docx format are supported</td></tr>
<tr>
<td>
TOC Field</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Bookmark</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Break</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Section Property</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Paragraph Format</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Table Format</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Character Format</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Text Box</td><td>
No</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Form Fields</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Document Background </td><td>
No</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Nested Table</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Watermark</td><td>
No</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Footnote / Endnote</td><td>
No</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Lists</td><td>
Yes</td><td>
Yes</td><td>
Image bullets are not supported</td></tr>
<tr>
<td>
Hyperlink</td><td>
Yes</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Symbols</td><td>
No</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Shapes and Auto shapes</td><td>
No</td><td>
No</td><td>
-</td></tr>
<tr>
<td>
OLE Object</td><td>
No</td><td>
No</td><td>
-</td></tr>
<tr>
<td>
RTL</td><td>
No</td><td>
No</td><td>
-</td></tr>
</table>


### Loading and Saving a HTML Document

This section shows you how to Load and Save a HTML document by using Essential DocIO.

### Loading a HTML Document

This option enables to insert a whole HTML document with the following limitations:

* XHTML 1.0 Strict is preferred; XHTML 1.0 Transitional is also acceptable.
* There is an option to validate against either XHTML Strict or Transitional schema. By default the given HTML string is validated against XHTML 1.0 Transitional schema and an exception is thrown, when the HTML is found to be non-complaint. However, you can set this property on the document instance to either, validate against XHTML Transitional schema or Strict schema.
* When a block element is not supported, then its style is still parsed and applied to the supported child elements inside. 



The following references enable to validate the HTML string for XHTML compliance.

* [http://www.w3schools.com/tags/default.asp](http://www.w3schools.com/tags/default.asp)
* [http://validator.w3.org/check](http://validator.w3.org/check)



The following code example illustrates how to load a HTML file.

{% highlight c# %}

//Opens the HTML file through WordDocument constructor.WordDocument doc = new WordDocument("Sample.html", FormatType.Html);

{% endhighlight %}

{% highlight vbnet %}

'Opens the HTML file through WordDocument constructor.Dim doc As New WordDocument("Sample.html", FormatType.Html)

{% endhighlight %}

You can also use the Open method of WordDocument class to load a XHTML file into WordDocument class.

{% highlight c# %}

//Opens the HTML file through Open method.doc.Open("Sample.html", FormatType.Html, XHTMLValidationType.Strict);

{% endhighlight %}

{% highlight vbnet %}

'Opens the HTML file through Open method.doc.Open("Sample.html", FormatType.Html, XHTMLValidationType.Strict)

{% endhighlight %}

Here the Parameter XHTMLValidationType denotes the validation schema against the input XHTML document. Please refer to the XHTML Validaiton section to know more about the XHTML schema definition.



### Support for Partial Path of an Image

Currently Essential DocIO provides support for the partial path of an image only when directly loading the HTML file into the Word document using document.Open() method.



The following are the two overloaded methods:

* document.Open(string fileName, FormatType formatType, XHTMLValidationType validationType, string baseUrl)
* document.Open(Stream stream, FormatType formatType, XHTMLValidationType validationType, string baseUrl)



## Parameter Definition

* filename: Denotes the resultant file name.
* formatType: Denotes the file format type of resultant document.
* validationType: Denotes the XHTML validation type. It can be Strict, Transitional or None. You can use the type “None” when you don’t want to use any of the XHTML schema validation.
* baseURL: Denotes the location of the referred image.



The following code example illustrates loading the HTML file containing the partial path of an image. 

{% highlight c# %}

//Creates a new instance for a Word document.WordDocument document = new WordDocument();//Sets the base folder path.string basePath=@"C:\InputFolder\";//Opens the HTML file along with the base path of the HTML file.document.Open(Path .Combine (basePath ,"Input.html"), Syncfusion.DocIO.FormatType.Automatic, XHTMLValidationType.None, basePath);   

{% endhighlight %}

{% highlight vbnet %}

'Creates a new instance for a Word document.Dim document As New WordDocument()'Sets the base folder path.Dim basePath As String = "C:\InputFolder\"'Opens the HTML file along with the base path of the HTML file.document.Open(Path.Combine(basePath, "Input.html"), Syncfusion.DocIO.FormatType.Automatic, XHTMLValidationType.None, basePath)

{% endhighlight %}

### Inserting a HTML Formatted String

This section elaborates how to insert a valid HTML string into the body or paragraph of a WordDocument class instance.

The following code illustrates how to insert a HTML string into the body part of a section

{% highlight c# %}

//Inserts XHTML String.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”);

{% endhighlight %}

{% highlight vbnet %}

'Inserts XHTML String.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”)

{% endhighlight %}

You can also insert the HTML string in the particular position of the document by specifying the index of the paragraph in the InsertXHTML overload of the TextBody class.

{% highlight vbnet %}

//Inserts XHTML with Paragraph index.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”,1);

{% endhighlight %}

{% highlight vbnet %}

'Inserts XHTML with Paragraph index.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”,1)

{% endhighlight %}

You can also insert the HTML string in the particular position of the document by specifying the index of the paragraph and paragraph item in the InsertXHTML overload of the TextBody class.

{% highlight c# %}

//Inserts XHTML with Paragraph and Paragraph item index.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”,1,2);

{% endhighlight %}

{% highlight vbnet %}

'Inserts XHTML with Paragraph and Paragraph item index.section.Body.InsertXHTML(“<html><body><p>Welcome</p></body></html>”,1,2)

{% endhighlight %}

It is possible to insert XHTML formatted text inside a Paragraph with the following limitations:

* The content is placed inside a <p> tag, to validate against the XHTML schemas as explained before.
* This HTML example cannot contain any block elements like div, and so on, and results in an exception being thrown otherwise. The only exception to this case is a single <p> tag.
* Among the supported XHTML tags, only the inline tags are used for formatting text.



The following code example illustrates, appending a HTML formatted string into a paragraph.

{% highlight vbnet %}

//Adds a new paragraph to the section.IWParagraph paragraph = section.AddParagraph();//Appends XHTML in the Paragraph.paragraph.AppendXHTML(htmlstring);

{% endhighlight %}

{% highlight vbnet %}

Adds a new paragraph to the section.Dim paragraph As IWParagraph = section.AddParagraph()'Appends XHTML in the Paragraph.paragraph.AppendXHTML(htmlstring)

{% endhighlight %}



N> Currently inserting XHTML formatted string in the Word document is not supported in Silverlight and Windows Phone 8 applications.



## XHTML Validation

You can validate the given XHTML string by invoking the IsValidXHTML method of TextBody class. It returns true when the given XHTML string should meet any one of the following validation types.

* Strict
* Transitional
* None

Each of these XHTML complaints target a different level of detail for XHTML. In other words, you can choose the kind of feature you want from the different features supported by DocIO.

The Strict DTD is the most efficient as it provides minimal XHTML language for creating web pages. So you might be thinking this is a very limited DTD and may not be of any use. Actually, as mentioned before, it is the most efficient DTD and enables a fastest validation of XHTML documents. The idea behind using a strict DTD is to use style sheets for display rather than presentation elements. Thus use of a strict DTD aims to separate presentation code from content.

The Transitional is the default validation type in DocIO when you do not define any XHTML Validation types. It adds more features than a Strict DTD to XHTML document. The support for more features increases the validation process when an XHTML document is displayed. Because a Transitional DTD provides support for presentation elements.

The None type provides the feature to manipulate the XHTML without using Strict and Transitional validation mechanism. You can use this type when you are not sure about XHTML contents.

The following table illustrates the basic comparison between the Transitional and Strict validation types.

_Table_ _134_: Validation Types_

<table>
<tr>
<th>
XHTML Type</th><th>
Description</th></tr>
<tr>
<td>
Strict</td><td>
The strict type validation does not support any HTML presentation elements (such as &lt;p&gt;, &lt;a&gt;, &lt;b&gt;, etc.).
This is the low-featured XHTML validation type.</td></tr>
<tr>
<td>
Transitional</td><td>
The Transitional type DTD adds support for HTML presentation elements. That means you can use HTML elements (such as &lt;p&gt;, &lt;a&gt;, &lt;b&gt;, etc.) directly inside of your XHTML document. </td></tr>
</table>
The following code illustrates how to validate a HTML string.

{% highlight c# %}

//Checks the valid XHTML.section.Body.IsValidXHTML(htmlString, XHTMLValidationType.Strict);

{% endhighlight %}

{% highlight vbnet %}

'Checks the valid XHTML.section.Body.IsValidXHTML(htmlString, XHTMLValidationType.Strict)

{% endhighlight %}


### Parameter Description

1. htmlString: The desired HTML string to be validated.
2. XHTMLValidationType: It defines the validation type. It could be Strict, Transitional, or None.
   ![](Styles-and-Formatting_images/Styles-and-Formatting_img9.jpeg)

N> Currently XHTML Validation is not supported in Windows Store applications.



## Saving a HTML Document

The following code example shows how to save a HTML document.

{% highlight html %}

HTMLExport htmlExport = new HTMLExport();
//Saves the document as HTML file in local storage.htmlExport.SaveAsXhtml(doc,  "doctohtml_res.html");

{% endhighlight %}

{% highlight vbnet %}

Dim htmlExport As New HTMLExport()
'Saves the document as HTML file in local storage.htmlExport.SaveAsXhtml(doc, "doctohtml_res.html")

{% endhighlight %}

The following code shows how to save a HTML document in a stream.

{% highlight c# %}

MemoryStream stream = new MemoryStream();
HTMLExport htmlExport = new HTMLExport();
//Saves the document as HTML file in a stream.htmlExport.SaveAsXhtml(doc,stream);

{% endhighlight %}

{% highlight vbnet %}

Dim stream As New MemoryStream()
Dim htmlExport As New HTMLExport()
'Saves the document as HTML file in a stream.htmlExport.SaveAsXhtml(doc,stream)

{% endhighlight %}

You can also use the overload of Save method in WordDocument class to export the HTML document.

{% highlight c# %}

document.Save(fileName,FormatType.Html);

{% endhighlight %}

{% highlight vbnet %}

document.Save(fileName,FormatType.Html)

{% endhighlight %}

The following code example saves the exported XHTML file into a stream.


{% highlight c# %}

document.Save(stream,FormatType.Html);</td></tr>

{% endhighlight %}

{% highlight vbnet %}

document.Save(stream,FormatType.Html)</td></tr>

{% endhighlight %}

### SaveOptions Class

It provides some more flexibility and some extra features when exporting the HTML documents. 

The following code example shows how to save the style sheet as internal style sheet and save the images as base 64 string using SaveOptions class. While using this there is no separate folder created to save images and all the contents are stored within the HTML file itself.

{% highlight c# %}

WordDocument doc = new WordDocument(@"..\..\DocToHTML.doc");
HTMLExport htmlExport = new HTMLExport();
//Sets style sheet type as internal.doc.SaveOptions.HtmlExportCssStyleSheetType = CssStyleSheetType.Internal;
//Specifies image folder. This will store the image as base 64 string.doc.SaveOptions.HtmlExportImagesFolder = "\\"; 
htmlExport.SaveAsXhtml(doc,  "doctohtml_res.html");

{% endhighlight %}

{% highlight vbnet %}

Dim doc As New WordDocument("..\..\DocToHTML.doc")
Dim htmlExport As New HTMLExport()
'Sets style sheet type as internal.doc.SaveOptions.HtmlExportCssStyleSheetType = CssStyleSheetType.Internal
'Specifies image folder. This will store image as base 64 string.doc.SaveOptions.HtmlExportImagesFolder = "\"htmlExport.SaveAsXhtml(doc, "doctohtml_res.html")

{% endhighlight %}


The following code example shows how to preserve the TextFormField’s text as normal text while exporting to HTML document. When you set the property HtmlExportTextInputFormFieldAsText to true then the content of the TextFormField is preserved as normal text. Otherwise it is preserved as editable TextFormField.

{% highlight c# %}

document.SaveOptions.HtmlExportTextInputFormFieldAsText = true;

{% endhighlight %}

{% highlight vbnet %}

document.SaveOptions.HtmlExportTextInputFormFieldAsText = True

{% endhighlight %}

You can turn off the Header and Footer contents in the exported HTML document by using the HtmlExportHeadersFooters property of SaveOptions class. The following code illustrates the same.

{% highlight c# %}

document.SaveOptions.HtmlExportHeadersFooters = false;

{% endhighlight %}

{% highlight vbnet %}

document.SaveOptions.HtmlExportHeadersFooters = False

{% endhighlight %}

### Supported Document Elements

DocIO supports the following document elements.

_Table_ _135_: _Document Elements_

<table>
<tr>
<th>
Document Element</th><th>
Attribute</th><th>
Support Status</th><th>
Notes</th></tr>
<tr>
<td>
Bookmark</td><td>
Id</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "4">
Border</td><td>
Color</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Distance from text</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Line style</td><td>
Partial</td><td>
Some line styles are rendered as solid.</td></tr>
<tr>
<td>
Line width</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Document Properties</td><td>
</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Field</td><td>
</td><td>
Yes</td><td>
Current field result is output, but the result is not recalculated.</td></tr>
<tr>
<td>
Footnotes and Endnotes</td><td>
</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Form Field</td><td>
Text input</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Header / Footer</td><td>
Different per section</td><td>
Partial</td><td>
Only primary header is output at the beginning of a section.</td></tr>
<tr>
<td rowspan = "2">
Hyperlink</td><td>
External URL</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Local</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "3">
Image</td><td>
</td><td>
</td><td>
</td></tr>
<tr>
<td>
Inline</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Scale</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "5">
List</td><td>
Custom bullets</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Multi-level</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Numbered</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Restart numbering</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Standard bullets</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "9">
Paragraph</td><td>
Alignment</td><td>
Yes</td><td>
</td></tr>
<tr>
<td>
Borders</td><td>
Yes</td><td>
See Borders, for more details.</td></tr>
<tr>
<td>
Keep together and Keep with next properities</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Paragraph Indents</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Line spacing</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Page break before</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Shading</td><td>
Yes</td><td>
See Shading, for more details.</td></tr>
<tr>
<td>
Spacing before and after</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Window control</td><td>
Yes</td><td>
Output as both windows and orphans.</td></tr>
<tr>
<td rowspan = "2">
Shading</td><td>
Background color</td><td>
Partial</td><td>
Solid background colors are supported.</td></tr>
<tr>
<td>
Foreground color</td><td>
Partial</td><td>
Solid foreground color is used when background color is auto.</td></tr>
<tr>
<td rowspan = "3">
Styles</td><td>
Paragraph styles</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Character styles</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
List styles</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "6">
Table</td><td>
Alignment</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Cell margins</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Column widths</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Indent from left</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Preferred width</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Spacing between cells</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "6">
Table Cell</td><td>
Borders</td><td>
Partial</td><td>
See Borders, for more details.</td></tr>
<tr>
<td>
Cell margins</td><td>
Partial</td><td>
Only default table cell margins left and right are supported.</td></tr>
<tr>
<td>
Horizontal merge</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Shading</td><td>
Partial</td><td>
See Shading, for more details.</td></tr>
<tr>
<td>
Vertical alignment</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Vertical merge</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "2">
Table Row</td><td>
Height</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Padding</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td rowspan = "20">
Text</td><td>
All caps</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Bold</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Character spacing</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Color</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Emboss</td><td>
Partial</td><td>
Rendered as bold.</td></tr>
<tr>
<td>
Engrave</td><td>
Partial</td><td>
Rendered as bold.</td></tr>
<tr>
<td>
Font</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Hidden</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Highlighting</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Imprint</td><td>
Partial</td><td>
Rendered as bold.</td></tr>
<tr>
<td>
Italic</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Line breaks</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Outline</td><td>
Partial</td><td>
Rendered as bold.</td></tr>
<tr>
<td>
Page breaks</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Shading</td><td>
Partial</td><td>
See Shading, for more details.</td></tr>
<tr>
<td>
Small caps</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Special symbols</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Strike out</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Subscript / Superscript</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Underline</td><td>
Partial</td><td>
Underline types and colors are ignored.</td></tr>
</table>


N> Currently Doc to Html conversion and vice-versa is not supported in Silverlight and Windows Phone 8 applications.


## Loading and Saving a Text Document 

This section shows you how to Load and Save a Text document using Essential DocIO. You can create new Word document or open Word document and save to Text format. 

The following code example lets you to load a Text document.

{% highlight c# %}

WordDocument doc = new WordDocument(@"..\..\Document.txt");

{% endhighlight %}

{% highlight vbnet %}

doc.Save( "sample.txt", FormatType.Txt )

{% endhighlight %}

The following code example lets you to save as Text file.

{% highlight c# %}

doc.Save( "sample.txt", FormatType.Txt );

{% endhighlight %}

{% highlight vbnet %}

doc.Save( "sample.txt", FormatType.Txt )

{% endhighlight %}


### Supported Document Elements

DocIO supports the following document elements.

_Table_ _136_: _Document Elements_

<table>
<tr>
<th>
Element</th><th>
Support Status</th><th>
Note</th></tr>
<tr>
<td>
Paragraph</td><td>
Yes</td><td>
-</td></tr>
<tr>
<td>
Header/Footer</td><td>
Yes</td><td>
Preserved as normal paragraph</td></tr>
<tr>
<td>
Field</td><td>
Yes</td><td>
Preserved as normal Text</td></tr>
<tr>
<td>
Lists</td><td>
Yes</td><td>
</td></tr>
<tr>
<td>
Symbols</td><td>
Yes</td><td>
Limited support</td></tr>
</table>

### Saving a Word Document as PDF

Essential DocIO allows you to export the word document as PDF document. You can create a word document from scratch or load a template Word document then export the document to PDF using DocIO. 

Essential DocIO lets you to edit the Word document contents without using Microsoft Word and then export the document to PDF. The following steps are involved in the Word to PDF conversion process.

1. Create a Word document from scratch or load a Word document using WordDocument class.
2. Instantiate the DocToPDFConverter class.
3. Convert the Word document to PDF using the ConvertToPDF method of DocToPDFConverter class and assign that to the instance of PdfDocument class.
4. Use the Save method of PdfDocument class to save the PDF document.



Assembly Dependencies for this Conversion

* Syncfusion.DocToPDFConverter.Base.dll
* Syncfusion.DocIO.Base.dll
* Syncfusion.Pdf.Base.dll
* Syncfusion.Core.dll
* Syncfusion.Compression.Base.dll 

N> * You need to have Essential PDF and Essential DocIO installed in your system. Since "Syncfusion.DocToPDFConverter.Base.dll" is conditionally shipped when both DocIO.Base and Pdf.Base is installed. * Layouting the contents of a Word document as pages in Essential DocIO is not exactly the same as layouting of Microsoft Word. So, the total number of pages may vary slightly compared to that of the Microsoft Word. * Currently,_ [Word to PDF](http://docs.syncfusion.com/windowsforms) _conversion is not supported in Silverlight, WinRT and Windows Phone applications.

The following code example lets you to convert a Word document to PDF.

{% highlight c# %}

WordDocument wordDoc = new WordDocument("sample.doc");
DocToPDFConverter converter = new DocToPDFConverter();
//Converts a Word document into a PDF document.PdfDocument pdfDoc = converter.ConvertToPDF(wordDoc);
//Saves the PDF file.pdfDoc.Save("DoctoPDF.pdf");

{% endhighlight %}

{% highlight vbnet %}

Dim wordDoc As New WordDocument("sample.doc")
Dim converter As New DocToPDFConverter()
'Converts a Word document into a PDF document.Dim pdfDoc As PdfDocument = converter.ConvertToPDF(wordDoc)
'Saves the PDF file.pdfDoc.Save("DoctoPDF.pdf")

{% endhighlight %}

### Supported and Unsupported Elements 

Word to PDF conversion feature provides support for the following elements.

_Table_ _137_: _Supported and Unsupported Elements_

<table>
<tr>
<th>
Element</th><th>
Support Description</th><th>
Known limitations</th></tr>
<tr>
<td>
Paragraph and Character formatting</td><td>
* Paragraph and character fonts* Font styles (Bold, Italic, Underline, and Strike through)* Subscript and Superscript* Paragraph and text highlighting* Paragraph Indents and tabs* Line spacing* Left, right, center and justify alignments* Borders around paragraphs</td><td>
<br>Underline – Single underline style is only supported</td></tr>
<tr>
<td>
Multi-Column Texts </td><td>
The word documents containing multi-column text are supported</td><td>
Multi-Column text positions are not calculated dynamically. So there may be some content position differences that occur in the PDF document.</td></tr>
<tr>
<td>
Headers and Footers</td><td>
Full support</td><td>
</td></tr>
<tr>
<td>
Bulleted, Numbered and Multi-level lists</td><td>
The bulleted list, numbered and multi-level list are supported with proper indentation and alignments as represented in the word document</td><td>
In some case, the image bullets preserved in the  document may be replaced by the disc style bullet.</td></tr>
<tr>
<td>
Images </td><td>
The images present in the document are supported along with their corresponding position and size</td><td>
Currently cropped images are not supported </td></tr>
<tr>
<td>
Tables</td><td>
Both simple and nested tables are supported with proper preservation of text formatting and images present inside the table cell. Text directions are also supported</td><td>
Tables making use of patterns and 3D borders are not retained in the output document. AutoFit Contents and AutoFit Window properties of table are not supported</td></tr>
<tr>
<td>
Breaks (page, section, linebreak, etc)</td><td>
Supports all types of breaks</td><td>
Line break is rendered as ordinary break and textwrapping type is not supported.</td></tr>
<tr>
<td>
OLEObject</td><td>
Partially Supported</td><td>
When the OLEObject represents an Image,it is preserved. When instance represents another instance, then that is not converted to PDF document.</td></tr>
<tr>
<td>
Textbox</td><td>
Text box is preserved with it’s content</td><td>
</td></tr>
<tr>
<td>
Page Settings and background image</td><td>
The actual page settings are preserved in the generated PDF documents that includes page size, orientation, page borders and its background image if available.</td><td>
When the input document contains more than one watermark types, then first watermark is considered and that is applied for entire document.</td></tr>
<tr>
<td>
Document Properties</td><td>
The document properties present in the word documents are also preserved in the generated PDF Document.</td><td>
</td></tr>
<tr>
<td>
Table of Contents</td><td>
TOC field is updated with contents and with corresponding page numbers</td><td>
</td></tr>
<tr>
<td>
Bookmarks</td><td>
Bookmarks are preserved as it is in the input document</td><td>
</td></tr>
<tr>
<td>
Hyperlinks</td><td>
Hyperlinks are preserved in the generated PDF document</td><td>
</td></tr>
<tr>
<td>
Footnote and Endnote</td><td>
Footnote and Endnote are supported.</td><td>
Number formats in Roman, Text and Number are supported</td></tr>
<tr>
<td>
Auto shapes </td><td>
Supports the predefined auto shapes.</td><td>
Only Docx format documents are supported</td></tr>
<tr>
<td>
Table Style</td><td>
Table style is supported </td><td>
Only Docx format documents are supported</td></tr>
<tr>
<td>
Comments</td><td>
Not Supported</td><td>
</td></tr>
<tr>
<td>
Shapes</td><td>
Not Supported</td><td>
</td></tr>
<tr>
<td>
Dynamic Fields</td><td>
Not Supported</td><td>
</td></tr>
<tr>
<td>
Charts</td><td>
Not Supported</td><td>
</td></tr>
<tr>
<td>
Pagination</td><td>
</td><td>
Essential DocIO makes sensible decision while layouting the text, and its supported elements while generating the PDF documents. But however, there may not be guaranteed pagination with all the documents.</td></tr>
</table>
### Saving a Word Document as an EPub File

Essential DocIO supports conversion of Microsoft Word documents to EPub v2.0.1. DocIO supports conversion of elements such as Text and Paragraph formatting, Lists, Images, Hyperlinks, Tables and Footnotes to EPub format.

By default, Table of Contents (TOC) is enabled in the EPub document. It is generated based on the built-in heading styles or custom styles mentioned in the TOC field. 


N> You need to have an EPub reader installed in the machine to view the resultant EPub document.



The following platforms support the EPub conversion process:

* Windows Forms
* ASP.NET
* WPF
* ASP.NET MVC



The following code example illustrates how to convert a Word document to EPub file format.

{% highlight c# %}

//Loads any .doc or .docx file.WordDocument document = new WordDocument(filename); 
//Saves the EPub file.document.Save("Sample.epub", FormatType.EPub);

{% endhighlight %}

{% highlight vbnet %}

'Loads any .doc or .docx file.
Dim document As WordDocument = New WordDocument(filename)
'Saves the EPub file.document.Save("Sample.epub", FormatType.EPub)

{% endhighlight %}

The following screenshot illustrates the resultant EPub document.

![](Styles-and-Formatting_images/Styles-and-Formatting_img13.png) 



_Figure_ _54_: Word document converted to EPub File Format_



## EmbeddingFont

Conversion of EPub by using default options does not embed font files. Hence, the targeted device uses its own default font for the texts in the document that may vary depending on the reader being used. To read the texts in the same font as used in the input word document, you should embed the font files into the generated EPub. This is achieved by turning on EPubExportFont property. By default, this property is set to false_,_ since this actually embeds the exact font file from the machine that may increase the size of the EPub document.

The following code example illustrates how to embed font file.

{% highlight c# %}

//Loads any .doc or .docx file.WordDocument document = new WordDocument(filename);
//Turns on embedding font files.document.SaveOptions.EPubExportFont = true;
//Saves the EPub file.document.Save("Sample.epub", FormatType.EPub);

{% endhighlight %}

{% highlight vbnet %}

'Loads any .doc or .docx file.
Dim document As WordDocument = New WordDocument(filename)
'Turns on embedding font files.document.SaveOptions.EPubExportFont = True
'Saves the EPub file.document.Save("Sample.epub", FormatType.EPub)

{% endhighlight %}

The following screenshot illustrates the resultant EPub document.

![](Styles-and-Formatting_images/Styles-and-Formatting_img14.png)



_Figure_ _55_: Embedding fonts in an EPub File_



## Exporting Header and Footer



Header and Footer in the Word document are helpful in placing specific information that is displayed on every page. These headers and footers are exported to the EPub document in such a way that only the first section header appears at the top of the document and the first section footer appears at the end of the document. This is achieved by turning on HtmlExportHeadersFooters property. By default, this property is set to true and hence it always exports header and footer.

The following code example illustrates how to export header and footer.

{% highlight c# %}

//Loads any .doc or .docx file.
WordDocument document = new WordDocument(filename);
//Turns on exporting headers and footers.document.SaveOptions.HtmlExportHeadersFooters = true;
//Saves the EPub file.document.Save("Sample.epub", FormatType.EPub);

{% endhighlight %}

{% highlight vbnet %}

'Loads any .doc or .docx file.
Dim document As WordDocument = New WordDocument(filename)
'Turns on exporting headers and footers.document.SaveOptions.HtmlExportHeadersFooters = True
'Saves the EPub file.   document.Save("Sample.epub", FormatType.EPub)

{% endhighlight %}

The following is the screenshot of the resultant EPub document with the disabled header and footer contents.

![](Styles-and-Formatting_images/Styles-and-Formatting_img15.png) 

_Figure_ _56_: _Exporting Header and Footer_



### Supported Elements

The following are the Supported Elements:

* Text and Paragraph Formatting
* Lists
* Tables
* Images
* Footnote
* Hyperlink
* Styles
* Table of Contents
* Document Properties



### Known Limitations

The following are the known limitations:

* Embedding font files can increase the size of the EPub document
* Embedding font files is not supported in medium trust

N> Currently Doc to EPub conversion is not supported in Silverlight application.

### Saving a Word Document as an Image

DocIO provides support to convert a Word document into an image of type Bitmap or EMF. It enables to easily convert a single specified page, group of pages or a whole document into image format. 

The following overloads of the RenderAsImages method can be used to convert a Word document into an image.

* WordDocument.RenderAsImages(imageType): This is used to convert the whole document into an image.
* WordDocument.RenderAsImages(pageIndex, imageFormat): This is used to render/convert a particular page of the document into an image; it returns the resultant image of type Stream.
* WordDocument.RenderAsImages(pageIndex, imageType): This is used to render/convert a particular page of the document into an image; it returns the resultant image of type Image.
* WordDocument.RenderAsImages(pageIndex, noOfPages, imageType): This is used to render/convert multiple number of pages in the document, starting from the specified page index. It returns the resultant image of type Image[] array.

N>

* Parameter "pageIndex" is a zero based index.
* Layouting the contents of a Word document as pages in the Essential DocIO is not exactly the same as the layouting in Microsoft Word. So, the total number of pages may vary slightly compared to that of the Microsoft Word.
* Currently, Word to Image conversion is not supported in Silverlight, WinRT and Windows Phone applications.
* You can refer to the_ [Word to PDF](http://docs.syncfusion.com/windowsforms) _Conversion for supported and unsupported elements in Word to Image conversion.

The following code example lets you to render a Word document as image.

{% highlight c# %}

Image[] images = document.RenderAsImages(ImageType.Metafile);
Stream stream = document.RenderAsImages(0, ImageFormat.Emf);
Image image = document.RenderAsImages(5, ImageType.Metafile);
//This converts pages 2, 3, 4 in the document into images.Image[] images = document.RenderAsImages(1, 3, ImageType.Metafile);

{% endhighlight %}

{% highlight vbnet %}

Dim images() As Image = document.RenderAsImages(ImageType.Metafile)
Dim stream As Stream = document.RenderAsImages(0, ImageFormat.Emf)
Dim image As Image = document.RenderAsImages(5, ImageType.Metafile)
'This converts pages 2, 3, 4 in the document into images.Dim images() As Image = document.RenderAsImages(1, 3, ImageType.Metafile)

{% endhighlight %}
