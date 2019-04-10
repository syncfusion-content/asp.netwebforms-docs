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

{% highlight html %}

<ej:DateRangePicker ID="dateRange" runat="server" Locale="zh-CN"></ej:DateRangePicker>

{% endhighlight %}

Also it is necessary to add the corresponding culture file with application and it should be referred after the ej.web.all.min.js file reference.

       <script src="http://cdn.syncfusion.com/js/assets/i18n/ej.culture.zh-CN.min.js"></script>

Then, add Localized text for including localization content. 

To get the localized text, it is necessary to add localized text file which is given below,

       <script src="http://cdn.syncfusion.com/{{ site.releaseversion }}/js/l10n/ej.localetexts.zh-CN.min.js"></script>

 Or else you can also set the localized text as your own like given in below code example. Adding localization content will make the DateRangePicker completely localized.

{% highlight js %}

        ej.DateRangePicker.Locale['zh-CN'] = {
            ButtonText: {
                        apply: "应用",
                        cancel: "取消",
                        reset: "重启"
                    },
                    watermarkText: "选择范围"
        };


{% endhighlight %}

Please find [sample](http://www.syncfusion.com/downloads/support/directtrac/general/ze/locale-599937872) for your reference.

