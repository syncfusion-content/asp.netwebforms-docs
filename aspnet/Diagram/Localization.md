---
layout: post
title: Localization | Diagram | ASP.NET Webform | Syncfusion
description: This section explains the process of providing controls in different cultures to help you set your own culture easily.
platform: aspnet
control: Diagram
documentation: ug
---

# Localization

* Localization is the process of providing controls in different cultures to help you set your own culture easily. Diagram provides localization support for Context Menu items.
* The Diagram model’s `Locale` property is used to define the culture code. 

The following code illustrates how to provide localization support for Context Menu items.

{% highlight aspx-cs %}

  // Defines the context menu items with Spanish language
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

   <ej:Diagram runat="server" ClientIDMode="Static" ID="DiagramWebControl" Width="100%" Height="600px" Locale="es-Es">
         <Nodes>
             <ej:BasicShape Name="rectangle1" OffsetX="100" OffsetY="100" Width="100" Height="100" 
                 FillColor="darkcyan" BorderColor="#1BA0E2">
                 <Labels>
                     <ej:DiagramLabel Text="Rectangle1" FontColor="white"></ej:DiagramLabel>
                 </Labels>
             </ej:BasicShape>
             <ej:BasicShape Name="rectangle2" OffsetX="300" OffsetY="100" Width="100" Height="100"
                 FillColor="darkcyan" BorderColor="#1BA0E2">
                 <Labels>
                     <ej:DiagramLabel Text="Rectangle2" FontColor="white"></ej:DiagramLabel>
                 </Labels>
             </ej:BasicShape>
         </Nodes>
         <Connectors>
             <ej:DiagramConnector SourceNode="rectangle1" TargetNode="rectangle2"></ej:DiagramConnector>
         </Connectors>
     </ej:Diagram>

{% endhighlight %}

![provide localization support for Context Menu items](/aspnet/Diagram/Localization_images/Localization_img1.png)

N> You have to define the textual descriptions of the context menu items for your custom cultures.