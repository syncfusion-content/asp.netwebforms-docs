---
layout: post
title: MVVM
description: mvvm
platform: common
control: Linear Gauge
documentation: ug
---

# MVVM

Angular JS

Linear Gauge contains angular support. It is possible to add object as well as array object in the Linear Gauge. The two way binding support is given to the pointer value, minimum scale value and maximum scale value. 









## Rendering the Linear gauge

ej-LinearGauge is the control tag, where ej is tag prefix and LinearGauge is the control name.

Linear Gauge is rendered with the following code example. 



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div ng-app="syncApp"&gt;

&lt;div ng-controller="LinearGauge"&gt;

<ej-LinearGauge id="linearCore" e-readOnly="false" e-load="loadGaugeTheme"

e-enableAnimation="false" e-labelColor="#8c8c8c">

&lt;/ej-LinearGauge&gt;

&lt;/asp:Content&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;script type="text/javascript"&gt;

&lt;!—binding the value to the scope variables in application controller--&gt;

angular.module('syncApp', ['ejangular'])

.controller('LinearGauge', function ($scope) {

$scope.nvalue = 0;

});

&lt;/script&gt;



Execute the above code to render the following output.







![](MVVM_images/MVVM_img1.png)
{:.image }


## Adding Scale collection

Scale is an array object and the inner tag is used for it. You can extend the Object in the array collection such as, position with hyphen in the same tag.

Example: e-position-x and e-position-y. 



&lt;!--To Render the Linear gauge--&gt;

&lt;ej-LinearGauge id="linearCore"&gt;

&lt;!--Adding Scale collection to the Linear gauge--&gt;

&lt;e-scales&gt;

<e-scale e-width="4" e-border-color="transparent" e-border-width="0"

e-showBarPointers="false" e-showRanges="true" e-length="310"

e-position-x="52" e-position-y="50" e-maximum="120">

&lt;/e-scale&gt;

&lt;/e-scales&gt;

&lt;/ej-LinearGauge&gt;



Execute the above code to render the following output.

![](MVVM_images/MVVM_img2.png)
{:.image }


## Adding Marker Pointer collection

Marker Pointer is an array object and the inner tag is used for it. You can extend the Object in the array collection such as, border with hyphen in the same tag.

Example: e-border-color. 

&lt;!--To Render the Linear gauge--&gt;

&lt;ej-LinearGauge id="linearCore"&gt;

&lt;!--Adding Scale collection to the Linear gauge--&gt;

&lt;e-scales&gt;

&lt;e-scale&gt;

&lt;!--Adding marker pointer collection to the Scale collection--&gt;

&lt;e-markerPointers&gt;

<e-markerPointer e-length="10" e-width="10" e-value="50"

e-backgrouundColor="#4D4D4D"

e-border-color="#4D4D4D">

&lt;/e-markerPointer&gt;

&lt;/e-markerPointers&gt;

&lt;/e-scale&gt;

&lt;/e-scales&gt;

&lt;/ej-LinearGauge&gt;



Execute the above code to render the following output.

![](MVVM_images/MVVM_img3.png)
{:.image }


## Adding label collection

Label is also an array object and the inner tag is used for it. You can extend the Object in the array collection such as, font with hyphen in the same tag.

Example: e-font-size. 

&lt;!--To Render the Linear gauge--&gt;

&lt;ej-LinearGauge id="linearCore"&gt;

&lt;!--Adding Scale collection to the Linear gauge--&gt;

&lt;e-scales&gt;

&lt;e-scale&gt;

&lt;!--Adding marker pointer collection to the Scale collection--&gt;

&lt;e-markerPointers&gt;…&lt;/e-markerPointers&gt;

&lt;!--Adding label collection to the Scale collection--&gt;

&lt;e-labels&gt;

<e-label  e-distanceFromScale-x="-10" e-distanceFromScale-y="0"

e-font-fontFamily="Segoe UI" e-font-fontStyle="bold"

e-font-size="11px">

&lt;/e-label&gt;

&lt;/e-labels&gt;

&lt;/e-scale&gt;

&lt;/e-scales&gt;

&lt;/ej-LinearGauge&gt;



Execute the above code to render the following output.

![](MVVM_images/MVVM_img4.png)
{:.image }


## Adding Tick collection

Tick is an array object and the inner tag is used for it.

&lt;!--To Render the Linear gauge--&gt;

&lt;ej-LinearGauge id="linearCore"&gt;

&lt;!--Adding Scale collection to the Linear gauge--&gt;

&lt;e-scales&gt;

&lt;e-scale&gt;

&lt;!--Adding marker pointer collection to the Scale collection--&gt;

&lt;e-markerPointers&gt;…&lt;/e-markerPointers&gt;

&lt;!--Adding label collection to the Scale collection--&gt;

&lt;e-labels&gt;…&lt;/e-labels&gt;

&lt;!--Adding tick collection to the Scale collection--&gt;

&lt;e-ticks&gt;

&lt;e-tick e-type="majorinterval" e-width="2" e-color="#8c8c8c"&gt;

&lt;/e-tick&gt;

&lt;/e-ticks&gt;

&lt;/e-scale&gt;

&lt;/e-scales&gt;

&lt;/ej-LinearGauge&gt;



Execute the above code to render the following output.

![](MVVM_images/MVVM_img5.png)
{:.image }


## Adding Range collection

Range is an array object and the inner tag is used for it. You can extend the Object in the array collection such as, border with hyphen in the same tag.

Example: e-border-color. 

&lt;!--To Render the Linear gauge--&gt;

&lt;ej-LinearGauge id="linearCore"&gt;

&lt;!--Adding Scale collection to the Linear gauge--&gt;

&lt;e-scales&gt;

&lt;e-scale&gt;



&lt;!--Adding marker pointer collection to the Scale collection--&gt;

&lt;e-markerPointers&gt;…&lt;/e-markerPointers&gt;



&lt;!--Adding label collection to the Scale collection--&gt;

&lt;e-labels&gt;…&lt;/e-labels&gt;



&lt;!--Adding tick collection to the Scale collection--&gt;

&lt;e-ticks&gt;…&lt;/e-ticks&gt;



&lt;!--Adding range collection to the Scale collection--&gt;



&lt;e-ranges&gt;

<e-range e-startValue="0" e-endValue="60" e-startWidth="4"

e-endWidth="4" e-backgroundColor="#F6B53F"

e-border-color="#F6B53F">

&lt;/e-range&gt;

<e-range e-startValue="60" e-endValue="120" e-startWidth="4"

e-endWidth="4" e-backgroundColor="#E94649"

e-border-color="#E94649">

&lt;/e-range&gt;

&lt;/e-ranges&gt;

&lt;/e-scale&gt;

&lt;/e-scales&gt;

&lt;/ej-LinearGauge&gt;



Finally while running the above codes, the resultant gauge appears as follows.

![](MVVM_images/MVVM_img6.png)
{:.image }


## Two Way Binding 

Linear Gauge support the two way binding for the property value, minimum and maximum as mentioned earlier. Following code example explains how to achieve the two way binding to the Linear Gauge.



&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div ng-app="syncApp"&gt;

&lt;div ng-controller="LinearGauge"&gt;

&lt;div id="linearframe"&gt;

&lt;ej-LinearGauge id="linearCore" e-value="nvalue" e-readOnly="false" e-load="loadGaugeTheme" e-enableAnimation="false" e-labelColor="#8c8c8c"&gt;

&lt;/ej-LinearGauge&gt;

&lt;/div&gt;

&lt;input type="text" id="txtMax" e-value="nvalue" ej-numerictextbox ng-model="nvalue"  e-decimalplaces="2" e-showspinbutton="false" Style="width:110px"/&gt;

&lt;/asp:Content&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;script type="text/javascript"&gt;

&lt;!—binding the value to the scope variables in application controller--&gt;

angular.module('syncApp', ['ejangular'])

.controller('LinearGauge', function ($scope) {

$scope.nvalue = 50;

});

&lt;/script&gt;



Execute the above code to render the following output.

![](MVVM_images/MVVM_img7.png)
{:.image }


## Knockout JS

* Knockout support allows you to bind the html elements against any of the available data models.Two types of knockout binding is supported as of angular,
* one-way binding
* two-way binding
* One way binding refers to the process of applying observable values to all the available properties of the Linear Gauge control, but the changes made in it does not reflect and trigger in turn to the observable collection. This kind of binding applies to all the properties of the Linear Gauge control.
* Two-way binding supports both the processes – it applies the observable values to the Linear Gauge properties as well as the changes made in it is also reflected back and triggered within the observable collections. Only few of the schedule properties support two-way binding and they are as follows
* value
* maximum 
* minimum



[ASPX]

&lt;%--For Linear Gauge rendering-- %&gt;

&lt;asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection"&gt;

&lt;div ng-app="syncApp"&gt;

&lt;div ng-controller="LinearGauge"&gt;

<div id="linearCore" style="width:100%" data-bind="ejLinearGauge:({value:samplevalue,minimum:sampleminimum,maximum:samplemaximum,readOnly:false,enableAnimation: false,labelColor: '#8c8c8c', width: 500, load:'loadGaugeTheme',

scales: [{

width: 4, border: { color: 'transparent', width: 0 }, showBarPointers: false, showRanges: true, length: 310,

position: { x: 52, y: 50 }, markerPointers: [{

length: 10, width: 10, backgroundColor: '#4D4D4D', border: { color: '#4D4D4D' }

}],

labels: [{ font: { size: '11px', fontFamily: 'Segoe UI', fontStyle: 'bold' }, distanceFromScale: { x: -13 } }],

ticks: [{ type: 'majorinterval', width: 1, color: '#8c8c8c' }],

ranges: [{

endValue: 60,

startValue: 0,

backgroundColor: '#F6B53F',

border: { color: '#F6B53F' }, startWidth: 4, endWidth: 4

}, {

endValue: 100,

startValue: 60,

backgroundColor: '#E94649',

border: { color: '#E94649' }, startWidth: 4, endWidth: 4

}]

}]})">&lt;/div&gt;

&lt;/asp:Content&gt;

&lt;/div&gt;

&lt;/div&gt;

&lt;script type="text/javascript"&gt;

window.viewModel = {

samplevalue: ko.observable(50),

sampleminimum: ko.observable(0),

samplemaximum: ko.observable(100),

};

$(function () {

ko.applyBindings(viewModel);

$("#sampleProperties").ejPropertiesPanel();

});

&lt;/script&gt;


Execute the above code to render the following output.

![](MVVM_images/MVVM_img8.png)
{:.image }






























_Linear Gauge with Knockout binding_

