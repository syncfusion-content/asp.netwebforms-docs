---
layout: post
title: Localization
description: localization 
platform: aspnet
control: Diagram
documentation: ug
---

# Localization 

Localization is the process of providing controls in different cultures to help you set your own culture easily.

Diagram provides localization support for ContextMenu items.

The following code illustrates how to provide localization support for ContextMenu items.

{% highlight js %}



$("#DiagramContent").ejDiagram("model.locale","es-ES");

ej.datavisualization.Diagram.Locale["es-ES"] = {

            cut: "Corte",

              copy: "Copia",

            paste: "Pasta",

            undo: "Deshacer",

            redo: "Rehacer",

            selectAll: "Seleccionar todo",

            grouping: "Agrupación",

            group: "Grupo",

            ungroup: "Desagrupar",

            order: "Fin",

            bringToFront: "Traer a delante",

            moveForward: "Movimiento adelante",

            sendToBack: "Enviar a espalda",

            sendBackward: "Enviar hacia atrás"



        };  



{% endhighlight %}



![](Localization_images/Localization_img1.png) 

_Localization_

