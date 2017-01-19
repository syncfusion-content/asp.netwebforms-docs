layout: post
title: View State Syncfusion ASP.NET controls
description: View State of Syncfusion ASP.NET controls
platform: ASP.NET
control: Introduction
documentation: ug
---

# View State 

View State is the method that the ASP.NET page framework uses to preserve page and control values between round trips. When the HTML markup for the page is rendered, the current state of the page and values that must be retained during postback.

Syncfusion controls can maintain theirs values even after form post or browser refresh by using EnablePersistence property. 

Sustain the entire widget model of EJWEB DatePicker even after form post or browser refresh by using EnablePersistence property. So the entire model values such as
•	Selected date
•	Highlighted date
•	Start and depth level

are stored in local storage / cookies of browser before page refreshes and reinitialized with the restored model after refresh.
