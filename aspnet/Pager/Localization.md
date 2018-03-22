---
layout: post
title: localization
description: localization
platform: aspnet
control: Pager
documentation: ug

---

# Localization

Pager has been provided with built in localization support with different culture.

## Setting different culture to control

We can set different culture to **Pager** control using **Locale** API. While we change the culture of the control from default culture (English), the Pager information text will be change accordingly. You can get the localized text by specifying the localized text file in your application and should be referred after ej.web.all.min.js file reference.

<script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/l10n/ej.localetexts.es-ES.min.js"></script>

Also, you can set localizes text of your as shown below code snippet.

{% highlight javascript %}

ej.Pager.Locale["es-ES"] = {

        PagerInfo: "{0} de {1} páginas ({2} artículos)",

        firstPageTooltip: "Ir a la primera página",

        lastPageTooltip: "Ir a la última página",

        nextPageTooltip: "Ir a la página siguiente",

        previousPageTooltip: "Ir a la página anterior",

        nextPagerTooltip: "Ir al siguiente Pager",

        previousPagerTooltip: "Ir a Pager anterior"
     };

ej.Pager.Locale["de-DE"] = {

        PagerInfo: "{0} von {1} Seiten ({2} Beiträge)",

        firstPageTooltip: "Zur ersten Seite",

        lastPageTooltip: "Zur letzten Seite",

        nextPageTooltip: "Zur nächsten Seite",

        previousPageTooltip: "Zurück zur letzten Seite",

        nextPagerTooltip: "Zum nächsten Pager",

        previousPagerTooltip: "Zum vorherigen Pager"
     };

{% endhighlight %}



