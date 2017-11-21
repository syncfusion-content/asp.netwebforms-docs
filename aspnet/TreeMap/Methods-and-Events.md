---
layout: post
title: Methods and Events
description: methods and events in treemap
platform: aspnet
control: TreeMap
documentation: ug
---

# Methods and Events

## Method

## Refresh()

`refresh()` method is used to reload the treemap with updated values.

#### Returns: void

{% highlight html %}

  <ej:TreeMap ID="treemap" runat="server">
  </ej:TreeMap>
  <script type="text/javascript">
       $("#treemap").ejTreeMap("refresh");
  </script>

{% endhighlight %}

## Events

## TreeMapItemSelected

`TreeMapItemSelected` event will trigger when treemap item is selected. 

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Returns selected treeMapItem object.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientTreeMapitemsselected="itemSelected">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function itemSelected(sender) { 
        // do something
    }
    </script>

{% endhighlight %}

## DrillStarted

`DrillStarted` event will fire, when the drilldown action is started in the treemap control.

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Returns selected drilled treeMap object.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientDrillStarted="onDrillStarted">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function onDrillStarted(sender) { 
        // do something
    }
    </script>

{% endhighlight %}

## DrillDownItemSelected

If the treemap drilldown item is selected, then `DrillDownItemSelected` event will fire.

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Returns selected drilldown treeMap object.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientDrillDownItemSelected="onDrillDownItemSelected">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function onDrillDownItemSelected(sender) { 
        // do something
    }
    </script>
    
{% endhighlight %}

## HeaderTemplateRendering

`HeaderTemplateRendering` event will fire before rendering the treemap drilldown header template.

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Returns drilldown header.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientHeaderTemplateRendering="loadTemplate">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function loadTemplate(sender) { 
        // do something
    }
    </script>

{% endhighlight %}

## Refreshed

`Refreshed` event will trigger after refreshing the treemap control with updated values.

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Refresh and load the treemap.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientRefreshed="onRefresh">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function onRefresh(sender) { 
        // do something
    }
    </script>

{% endhighlight %}

## TreeMapGroupSelected

`TreeMapGroupSelected` event will fired when the group selection is performed on treemap items.

<table class="params">
    <thead>
        <tr>
            <th>Name</th>
            <th>Type</th>
            <th class="last">Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
           <td class="name">{% highlight html %}originalEvent{% endhighlight %}</td>
            <td class="type"><span class="param-type">object</span></td>
            <td class="description last">Returns the  selected group of treeMapItems as  object.</td>
        </tr>
    </tbody>
</table>

{% highlight html %}

   <ej:TreeMap ID="treemap" runat="server" OnClientTreeMapGroupSelected="onGroupSelected">
   </ej:TreeMap>
   
   <script type="text/javascript">
    function onGroupSelected(sender) { 
        // do something
    }
    </script>

{% endhighlight %}