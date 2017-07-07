---
layout: post
title: globalization
description: globalization
platform: aspnet
control: DateRangePicker
documentation: ug
keywords: globalization
---

## Globalization

DateRangePicker, has built in support with Localization so that you can make use of culture specified DateRangePicker component with your application using **locale** API, 

More than 350 culture specific files are available to localize the date. To know more about EJ globalize support, please refer the below link 

[https://help.syncfusion.com/js/localization](https://help.syncfusion.com/js/localization)

Also we have added Localized text files to DateRangePicker for 28 standard culture in below GitHub location,

[https://github.com/syncfusion/ej-global](https://github.com/syncfusion/ej-global)

### Setting different culture to control

By setting another culture other than English we need to set using **locale** API like below code example.

Also it is necessary to add the corresponding culture file with application and it should be referred after the ej.web.all.min.js file reference.

       <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/i18n/ej.culture.de-DE.min.js"></script>

To get the localized text, it is necessary to add localized text file, else you can also set the localized text as your own like below code example. Adding Localized text, will make completely localized UI to DateRangePicker.

{% highlight js %}

        $(function () {
            var dateRangeObj = $('#<%=dateRange.ClientID%>').ejDateRangePicker('instance');


            if (ej.cultureObject.name == "zh-CN") {
                dateRangeObj.option({
                    buttonText: {
                        apply: "应用",
                        cancel: "取消",
                        reset: "重启"
                    },
                    watermarkText: "选择范围"
                })
            }
        });


{% endhighlight %}



