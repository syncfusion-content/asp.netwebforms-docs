---
layout: post
title: MVVM | DigitalGauge | ASP.NET Webforms | Syncfusion
description: mvvm
platform: aspnet
control: Digital Gauge
documentation: ug
---

# MVVM

## AngularJS

Digital Gauge contains AngularJS support. It is possible to add object as well as array object in the Digital Gauge. The two way binding support is given to the value for displaying the text. 



### Rendering the Digital Gauge

ej-DigitalGauge is the control tag, where ej is tag prefix and DigitalGauge is the control name.Digital Gauge is rendered with the following code example.

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div ng-app="syncApp">

<div ng-controller="DigitalGauge">

<ej-DigitalGauge id="digitalCore" e-height="500" e-load="loadGaugeTheme">

</ej-DigitalGauge>

</asp:Content>

</div>

</div>

<script type="text/javascript">



<!—binding the value to the scope variables in application controller-->



angular.module('syncApp', ['ejangular'])

.controller('DigitalGauge', function ($scope) {

$scope.value = "text";

});

</script>

{% endhighlight %}

Execute the above code to render the following output.

![](MVVM_images/MVVM_img1.png)

Default Digital Gauge in AngularJS
{:.caption} 

### Adding the Digital Gauge Items

Digital Gauge is rendered with the following code example. You can extend the Object in the array collection such as, position, characterSetting, segmentSetting, etc. with hyphen in the same tag.

Example: e-position-x. 

{% highlight html %}

<!--To Render the Digital gauge-->



<ej-DigitalGauge id="digitalCore">



<!--Adding Item collection to the digital gauge-->



<e-items>

<e-item e-segmentSettings-width="1" e-segmentSettings-spacing="0"

e-value="Syncfusion" e-characterSetting-opacity="0.8"

e-position-x="52" e-position-y="52">

</e-item>

</e-items>



</ej-DigitalGauge>

{% endhighlight %}

Finally while running the above codes, the following output will be rendered.

![](MVVM_images/MVVM_img2.png) 

Digital Gauge Rendered in AngularJS
{:.caption} 



### Two Way Binding

Digital Gauge supports the two way biding for the property value as mentioned earlier. Following code example explains how to achieve the two way binding to the Digital Gauge.

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div ng-app="syncApp">

<div ng-controller="DigitalGauge">

<ej-DigitalGauge id="digitalCore" e-height="200" e-load="loadGaugeTheme">

<e-items>

<e-item e-segmentSettings-width="1" e-segmentSettings-spacing="0"

e-characterSetting-opacity="0.8" e-position-x="52"

e-value="value" e-position-y="52">

</e-item>

</e-items>

</ej-DigitalGauge>

Type here <input type="text" id="txtValue" ng-model="value" Style="width:110px"/>

<asp:Content>

</div>

</div>



<script type="text/javascript">



<!—binding the value to the scope variables in application controller-->



angular.module('syncApp', ['ejangular'])

.controller('DigitalGauge', function ($scope) {

$scope.value = "Syncfusion";

});

</script>


{% endhighlight %}


Execute the above code to render the following output.

![](MVVM_images/MVVM_img3.png)

Digital Gauge with two way binding in AngularJS
{:.caption} 

### KnockoutJS Binding



* KnockoutJS support allows you to bind the HTML elements against any of the available data models.Two types of KnockoutJS binding is supported as of AngularJS,
  
  1. one-way binding
  
  2. two-way binding
  
  
* One way binding refers to the process of applying observable values to all the available properties of the Digital Gauge control, but the changes made in it does not reflect and trigger in turn to the observable collection. This kind of binding applies to all the properties of the Digital Gauge control.
* Two-way binding supports both the processes – it applies the observable values to the Digital Gauge properties as well as the changes made in it is also reflected back and triggered within the observable collections. Only Value of the schedule properties support two-way binding.





{% highlight html %}
        <%--For Linear Gauge rendering-- %>

        <asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

        <div align="center">

        <div id="digitalCore" style="width:100%" data-bind="ejDigitalGauge:({value:samplevalue,width:510,height:300,load:'loadGaugeTheme',items: [{ segmentSettings:{width: 2, spacing: 0},characterSettings:{opacity: 0.8}, value: 'Syncfusion', position: { x: 52, y: 52 } }]

        })"></div>

        </div>

        </asp:Content> <script type="text/javascript">

        window.viewModel = {

        sampleValue: ko.observable(“Syncfusion”),

        };

        $(function () {

        ko.applyBindings(viewModel);

        $("#sampleProperties").ejPropertiesPanel();

        });

        </script>

{% endhighlight %}

Execute the above code to render the following output.



![](MVVM_images/MVVM_img4.png)


Digital Gauge with KnockoutJS binding
{:.caption} 



