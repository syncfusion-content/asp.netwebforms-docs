---
layout: post
title: Bitwise Operations | Diagram | ASP.NET Webforms | Syncfusion
description: bitwise operations
platform: aspnet
control: Diagram
documentation: ug
---

# Bitwise Operations

### Bitwise Operation

Bitwise Operations are used to manipulate the flagged enumerations [enum]. In this section, Bitwise Operations are illustrated by using Graph Constraints. The same is applicable while working with Node Constraints, Connector Constraints, or Port Constraints.

#### Add Operation

You can add or enable multiple values at a time by using Bitwise ‘|’ (OR) operator.

{% highlight c# %}

node.Constraints = NodeConstraints.Select | NodeConstraints.Rotate;



{% endhighlight %}



In the above example, you can do both selection and rotation.

#### Remove Operation

You can remove or disable values by using Bitwise ‘&~’ (XOR) operator.

{% highlight c# %}

node.Constraints = node.Constraints &~ NodeConstraints.Rotate;



{% endhighlight %}



In the above example, Rotation is disabled, but other constraints are enabled.

#### Check Operation 

You can check any value by using Bitwise ‘&’ (AND) operator.

{% highlight c# %}

if ((node.constraints & (NodeConstraints.Rotate)) == (NodeConstraints.Rotate));



{% endhighlight %}



In the above example, you can check whether the rotate constraints are enabled in a Node or not. When Node constraints have rotate constraints, the expression returns a rotate constraint.

