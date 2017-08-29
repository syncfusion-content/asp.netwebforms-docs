---
layout: post
title: MVVM | CircularGauge | ASP.NET Webforms | Syncfusion
description: mvvm
platform: aspnet
control: Circular Gauge
documentation: ug
---

# MVVM

## AngularJS

Circular Gauge contains AngularJS support. You can add object as well as array object in the Circular Gauge. The two way binding support is given to the pointer value, minimum scale value and maximum scale value. 

### Rendering the Circular Gauge

ej-CircularGauge is the control tag in which ej is tag prefix and CircularGauge is the control name.The following code example helps you to render Circular Gauge.

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div ng-app="syncApp">

<div ng-controller="CircularGauge">

<ej-CircularGauge id="CircularGauge1" e-backgroundColor="transparent" e-value="50"

e-width="500" e-readOnly="false" e-load= "loadGaugeTheme"

e-enableAnimation="false">

</ej-CircularGauge>

<asp:Content>

</div>

</div>

<script type="text/javascript">



<!—binding the value to the scope variables in application controller-->



angular.module('syncApp', ['ejangular'])

.controller('CircularGauge', function ($scope) {

$scope.value = 50;

$scope.minimum = 0;

$scope.maximum = 120;



});

</script>

{% endhighlight %}



Execute the above code to render the output as follows.

 ![](MVVM_images/MVVM_img1.png)


### Adding Scale Collection

Scale is an array object and you can use the inner tag for it. Object in the array collection (i.e. border) is extended with hyphen in the same tag.

Example: e-border-width and e-border-color. 

{% highlight html %}

<!--To Render the Circular gauge-->



<ej-CircularGauge id="CircularGauge1">



<!--Adding Scale collection to the Circular gauge-->



<e-scales>

<e-scale e-showRanges="true" e-startAngle="122" e-sweepAngle="296"

e-radius="130" e-showScaleBar="true" e-size="1" e-maximum="120"

e-majorIntervalValue="20" e-minorIntervalValue="10"

e-border-width="0.5">



</e-scale>

</e-scales>



</ej-CircularGauge>


{% endhighlight %}


Execute the above code to render the following output.

 ![](MVVM_images/MVVM_img2.png)





### Adding Pointer Collection

Pointer is an array object and you can use the inner tag for it. Object in the array collection (i.e. pointer cap) is extended with hyphen in the same tag.

Example: e-pointerCap-radius. 

{% highlight html %}

<!--To Render the Circular gauge-->



<ej-CircularGauge id="CircularGauge1">



<!--Adding Scale collection to the Circular gauge-->



<e-scales>

<e-scale>

<!--Adding pointer collection to the scale collection-->



<e-pointers>

<e-pointer e-showBackNeedle="true" e-backNeedleLength="20"

e-length="95" e-width="7" e-value="80"

e-pointerCap-radius="12">

</e-pointer>

</e-pointers>



</e-scale>

</e-scales>



</ej-CircularGauge>


{% endhighlight %}


Execute the above code to render the output as follows.

 ![](MVVM_images/MVVM_img3.png)





### Adding Label Collection

Label is also an array object. You can use the inner tag for it. 

{% highlight html %}

<!--To Render the Circular gauge-->



<ej-CircularGauge id="CircularGauge1">



<!--Adding Scale collection to the Circular gauge-->



<e-scales>

<e-scale>

<!--Adding pointer collection to the scale collection-->

<e-pointers>…</e-pointers>

<!--Adding labels collection to the scale collection-->



<e-labels>

<e-label e-color="#8c8c8c">

</e-label>

</e-labels>



</e-scale>

</e-scales>



</ej-CircularGauge>

{% endhighlight %}



Execute the above code to render the following output.

 ![](MVVM_images/MVVM_img4.png)

### Adding Tick Collection

Tick is an array object. You can use the inner tag for it. 

{% highlight html %}

<!--To Render the Circular gauge-->



<ej-CircularGauge id="CircularGauge1">



<!--Adding Scale collection to the Circular gauge-->



<e-scales>

<e-scale>

<!--Adding pointer collection to the scale collection-->

<e-pointers>…</e-pointers>

<!--Adding labels collection to the scale collection-->

<e-labels>…</e-labels>

<!--Adding ticks collection to the scale collection-->



<e-ticks>

<e-tick e-type="major" e-distanceFromScale="2" e-height="16"

e-width="1" e-color="#8c8c8c">

</e-tick>

<e-tick e-type="minor" e-distanceFromScale="2" e-height="8"

e-width="1" e-color="#8c8c8c">

</e-tick>

</e-ticks>



</e-scale>

</e-scales>



</ej-CircularGauge>


{% endhighlight %}


Execute the above code to render the following output.

 ![](MVVM_images/MVVM_img5.png)

### Adding Range Collection

Range is an array object. You can use the inner tag for it. Object in the array collection (i.e. border) is extended with hyphen in the same tag.

Example: e-border-color. 

{% highlight html %}

<!--To Render the Circular gauge-->



<ej-CircularGauge id="CircularGauge1">



<!--Adding Scale collection to the Circular gauge-->



<e-scales>

<e-scale>

<!--Adding pointer collection to the scale collection-->

<e-pointers>…</e-pointers>

<!--Adding labels collection to the scale collection-->

<e-labels>…</e-labels>

<!--Adding ticks collection to the scale collection-->

<e-ticks>…</e-ticks>

<!--Adding ranges collection to the scale collection-->



<e-ranges>

<e-range e-distanceFromScale="-30" e-startValue="0" e-endValue="70">

</e-range>

<e-range e-distanceFromScale="-30" e-startValue="70"

e-endValue="110" e-backgroundColor="#fc0606"

e-border-color="#fc0606">

</e-range>

<e-range e-distanceFromScale="-30" e-startValue="110"

e-endValue="120" e-backgroundColor="#f5b43f"

e-border-color="#f5b43f">

</e-range>

</e-ranges>


</e-scale>

</e-scales>



</ej-CircularGauge>


{% endhighlight %}


Execute the above code to render the following output.

 ![](MVVM_images/MVVM_img6.png)


### Two Way Binding 

Circular Gauge support the two way binding for the property value, minimum and maximum as mentioned earlier. The following code example explains how to achieve the two way binding in Circular Gauge.

{% highlight html %}

<asp:Content ID="ControlContent" runat="server" ContentPlaceHolderID="ControlsSection">

<div ng-app="syncApp">

<div ng-controller="CircularGauge">

<ej-CircularGauge id="CircularGauge1" e-backgroundColor="transparent" e-value="value" e-width="500" e-readOnly="false" e-load= "loadGaugeTheme" e-enableAnimation="false">

<e-scales>

<e-scale e-showRanges="true" e-startAngle="122" e-sweepAngle="296"

e-radius="130" e-showScaleBar="true" e-size="1"

<!—binding maximum value using AngularJS -->

e-maximum="maximum"

<!—binding minimum value using AngularJS -->

e-minimum="minimum"

e-majorIntervalValue="20"

e-minorIntervalValue="10" e-border-width="0.5">

<e-pointers>

<e-pointer e-showBackNeedle="true" e-backNeedleLength="20"

e-length="95" e-width="7"

<!—binding pointer value using angular JS -->

e-value="value"

e-pointerCap-radius="12">

</e-pointer>

</e-pointers>

<e-labels>

<e-label e-color="#8c8c8c"></e-label>

</e-labels>

<e-ticks>

<e-tick e-type="major" e-distanceFromScale="2" e-height="16"

e-width="1" e-color="#8c8c8c">

</e-tick>

<e-tick e-type="minor" e-distanceFromScale="2" e-height="8"

e-width="1" e-color="#8c8c8c">

</e-tick>

</e-ticks>

<e-ranges>

<e-range e-distanceFromScale="-30" e-startValue="0" e-endValue="70">

</e-range>

<e-range e-distanceFromScale="-30" e-startValue="70"

e-endValue="110" e-backgroundColor="#fc0606"

e-border-color="#fc0606">

</e-range>

<e-range e-distanceFromScale="-30" e-startValue="110"

e-endValue="120" e-backgroundColor="#f5b43f"

e-border-color="#f5b43f">

</e-range>

</e-ranges>

</e-scale>

</e-scales>

</ej-CircularGauge>



<input type="text" id="txtMax" e-value="value" ej-numerictextbox ng-model="value"  e-decimalplaces="2" e-showspinbutton="false" Style="width:110px"/>

</asp:Content>

</div>

</div>



<script type="text/javascript">



<!—binding the value to the scope variables in application controller-->



angular.module('syncApp', ['ejangular'])

.controller('CircularGauge', function ($scope) {

$scope.value = 50;

$scope.minimum = 0;

$scope.maximum = 120;



});

</script>

{% endhighlight %}

Execute the above code to render the following output.

 ![](MVVM_images/MVVM_img7.png)





### KnockoutJS

* KnockoutJS support allows you to bind the HTML elements against any of the available data models.Two types of KnockoutJS binding is supported as of AngularJS,

  1. one-way binding
  
  2. two-way binding
  
* One way binding refers to the process of applying observable values to all the available properties of the Circular Gauge control, but the changes made in gauge control does not reflect and trigger in turn to the observable collection. This kind of binding applies to all the properties of the circular gauge control.

* Two-way binding supports both the processes – it applies the observable values to the Circular Gauge properties as well as the changes made in the Circular Gauge control also reflects back and triggers within the observable collections. Only few of the schedule properties support two-way binding and they are as follows
  
  1. value
  
  2. maximum 
  
  3. minimum
     
{% highlight html %}

        <%--content section to refer script files-- %>



        <%--control section-- %>

        <div id="circularCore" data-bind="ejCircularGauge:({value:samplevalue,minimum:sampleminimum,maximum:samplemaximum,readOnly:false,enableAnimation:false,backgroundColor: 'transparent', width: 500, height:360,

        scales: [{

        showRanges: true,

        startAngle: 122, sweepAngle: 296, radius: 130, showScaleBar: true, size: 1, border: { width: 0.5 }, majorIntervalValue: 20, minorIntervalValue: 10,

        pointers: [{

        showBackNeedle: true,

        backNeedleLength: 20,

        length: 95,

        width: 7,

        pointerCap: { radius: 12 }

        }],

        labels: [{

        Color: '#8c8c8c'

        }],

        ticks: [{

        type: 'major',

        distanceFromScale: 2,

        height: 16,

        width: 1, Color: '#8c8c8c'

        }, { type: 'minor', height: 8, width: 1, distanceFromScale: 2, color: '#8c8c8c' }],

        ranges: [{

        distanceFromScale: -28,

        startValue: 0,

        endValue: 60



        },{

        distanceFromScale: -28,

        backgroundColor: '#fc0606',

        border:{color: '#fc0606'},

        startValue: 60,

        endValue: 120

        }]

        }]})">

        </div>

        <script type="text/javascript">

        window.viewModel = {

        sampleValue: ko.observable(50),

        sampleMinimum: ko.observable(0),

        sampleMaximum: ko.observable(120),

        };

        $(function () {

        ko.applyBindings(viewModel);

        $("#sampleProperties").ejPropertiesPanel();

        });

        </script>

{% endhighlight %}

Execute the above code to render the following output. The following screenshot is the output of ASP.

 ![](MVVM_images/MVVM_img8.png)





