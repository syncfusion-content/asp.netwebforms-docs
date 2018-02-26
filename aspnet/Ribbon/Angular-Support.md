---
layout: post
title: Angular Support | Ribbon | ASP.NET Webforms | Syncfusion
description: angular support
platform: aspnet
control: Ribbon
documentation: ug
---

# AngularJS-Support

It is possible to add object, array collection in the Ribbon control with AngularJS. The one way binding support is provided for Ribbon control.

`ej-ribbon` is the control tag where, `ej` is tag prefix and `Ribbon` is the control name.

## Tabs and Contextual Tabs

Ribbon Tabs and Contextual Tabs are Array Collections and the inner tag is used for them.

Objects with in these Array Collections can be extended by using hyphen. E.g. `e-applicationTab-menuItemId="menu"`

{% highlight html %}

	<div ng-app="ribbonApp">
		<div ng-controller="RibbonCtrl">
		<div id="defaultRibbon" ej-ribbon e-width="400" e-applicationtab-menuItemid="menu" e-applicationtab-applicationTabType="ApplicationMenu">
			
				<!-- Tabs array collection-->
				<div e-tabs>
					<div e-tab e-id="home" e-text="HOME">
						<div e-groups>
							<div e-group e-text="New" e-aligntype="rows">
								<div e-content>
									<div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
										<div e-groups>
							
											<!-- group object-->
											<div e-group e-id="new" e-text="New" e-buttonsettings-prefixicon="e-icon e-new" e-buttonsettings-contenttype="imageonly">
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
				<div e-contextualtabs>
					<div e-contextualtab e-backgroundcolor="#FCFBEB" e-bordercolor="#F2CC1C">
						<div e-tabs>
							<div e-tab e-id="Design" e-text="DESIGN">
								<div e-groups>
									<div e-group e-text="New" e-aligntype="rows">
										<div e-content>
											<div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
												<div e-groups>
													<div e-group e-id="Design" e-text="Design" e-buttonsettings-prefixicon="e-icon e-shape" e-buttonsettings-contenttype="textandimage" e-buttonsettings-imageposition="imagetop">
													</div>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		<ul id="menu">
			<li>
			<a>FILE</a>
			<ul>
				<li><a>Save</a></li>
			</ul>
			</li>
		</ul>
		</div>
	</div>
	<script type="text/javascript">
		angular.module('ribbonApp', ['ejangular']).controller('RibbonCtrl', function ($scope) {
		});
	</script>

{% endhighlight %}

![](Angular_images/Angular_img1.png)

## Gallery and Custom Tooltip                

GalleryItems is an Array Collection and the inner tag is used for it inside the Ribbon Groups. Object of this Array Collection can be extended by using hyphen. 

Custom Tooltip is an Object of Ribbon Groups and can extend it by using hyphen. E.g. `e-customToolTip-title`.

{% highlight html %}
	
	<div ng-app="ribbonApp">
			<div ng-controller="RibbonCtrl">
				<div id="defaultRibbon" ej-ribbon e-width="400" e-applicationtab-menuitemid="ribbonmenu" e-applicationtab-applicationtabtype="ApplicationMenu" e-allowresizing="true">
					<div e-tabs>
						<div e-tab e-id="home" e-text="HOME">
							<div e-groups>
								<div e-group e-text="New" e-aligntype="rows">
									<div e-content>
										<div e-content e-defaults-type="button" e-defaults-width="60" e-defaults-height="70">
											<div e-groups>
												<div e-group e-id="paste" e-text="Paste" e-customtooltip-title="Paste" e-customtooltip-content="<h6>Paste the content.<br/><br/>Add content on the Clipboard to your document.</h6>" e-customtooltip-prefixicon="e-icon e-pastetip">
												</div>
											</div>
										</div>
									</div>
								</div>
								<div e-group e-text="Gallery" e-aligntype="rows">
									<div e-content>
										<div e-content>
											<div e-groups>
												<div e-group e-id="Gallery" e-columns="3" e-itemheight="54" e-itemwidth="70" e-expandedcolumns="4" e-type="gallery">
													<div e-galleryitems>
														<div e-galleryitem e-text="Content1" e-tooltip="GalleryContent1" e-buttonsettings-contenttype="textonly"></div>
														<div e-galleryitem e-text="Content2" e-tooltip="GalleryContent2" e-buttonsettings-contenttype="textonly"></div>
														<div e-galleryitem e-text="Content3" e-tooltip="GalleryContent3" e-buttonsettings-contenttype="textonly"></div>
														<div e-galleryitem e-text="Content4" e-tooltip="GalleryContent4" e-buttonsettings-contenttype="textonly" ></div>
														<div e-galleryitem e-text="Content5" e-tooltip="GalleryContent5" e-buttonsettings-contenttype="textonly" ></div>
													</div>
													<div e-customgalleryitems>
														<div e-customgalleryitem e-customitemtype="menu" e-menuid="extramenu" e-menusettings-openonclick="false"></div>
													</div>
												</div>
											</div>
										</div>
									</div>
								</div>
							</div>
						</div>
					</div>
				</div>
			</div>
	<script type="text/javascript">
		angular.module('ribbonApp', ['ejangular']).controller('RibbonCtrl', function($scope) {});
	</script>

{% endhighlight %}

![](Angular_images/Angular_img2.png)
