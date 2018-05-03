---
layout: post
title: Localization in ComboBox widget for Syncfusion ASP.NET WebForm
description: Describes about the localization in ComboBox widget for Syncfusion ASP.NET WebForm
platform: aspnet
control: ComboBox
documentation: ug
keywords: ComboBox, ComboBox, Localization
---

# Localization

The Localization library allows you to localize static text content of the `NoRecordsTemplate` and `ActionFailureTemplate` properties according to the culture currently assigned to the ComboBox.

| Locale key | en-US (default)  |
|------|------|-------------|
| NoRecordsTemplate |  No records found |
| ActionFailureTemplate | The request failed |

## Loading translations

In the following sample, French culture is set to the ComboBox and no data is loaded. Hence, the `NoRecordsTemplate` property displays its text in French culture initially, and if the sample is run offline, the `ActionFailureTemplate` property displays its text appropriately.

N> The culture name has to be specified in a standard format such as [Language Code]-[County/Region Code].

To localize the ComboBox's strings with your own localization, copy the default language informations and localize the strings in the values column. For example, to localize the ComboBox in French language (“fr-BE”).

{% highlight javascript %}

ej.ComboBox.Locale["fr-BE"] = {
    'noRecordsTemplate': "Aucun enregistrement trouvé",
    'actionFailureTemplate': "Modèle d'échec d'action" 
};
    
{% endhighlight %}

Set the locale property of the ComboBox to the new language.

{% tabs %}
	
{% highlight html %}
	
 <ej:ComboBox ID="groupingCountry" runat="server" DataTextField="text" DataGroupByField="category" Locale="fr-BE" Placeholder="Choisissez un pays" Width="100%"></ej:ComboBox>
		
{% endhighlight %}
    
{% highlight c# %}

protected void Page_Load(object sender, EventArgs e)
{
	this.groupingCountry.DataSource = Countries.GetCountries();
}

{% endhighlight %}

{% endtabs %}
	
![](localization_images/localization_image1.png)