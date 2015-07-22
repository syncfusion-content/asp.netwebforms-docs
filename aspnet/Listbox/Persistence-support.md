---
layout: post
title: Persistence-support
description: persistence support 
platform: aspnet
control: Control Name undefined
documentation: ug
---

# Persistence support 

This feature enables you to save current model value to browser cookies for state maintains. When you refresh the ListBox control page, it retains the model value apply from browser cookies. The date type of EnablePersistence is Boolean type. 

The following steps explains you the configuration of EnablePersistence property in ListBox.

In an ASPX page, add an elementto configure ListBox.

{% highlight html %}

<div id="control">

    <div class="ctrllabel">

        Select a skill</div>

<ej:listbox id="listboxsample" DataTextField="Name"  runat="server" EnablePersistence= "true" Width ="240"></ej:listbox>

</div> 





{% endhighlight %}



{% highlight c# %}

     protected void Page_Load(object sender, EventArgs e)

        {

            listboxsample.DataSource = GetData();

        }

        private List<Languages> GetData()

        {

            List<Languages> data = new List<Languages>();

            data.Add(new Languages() { Name = "ASP.NET" });

            data.Add(new Languages() { Name = "ActionScript" });

            data.Add(new Languages() { Name = "Basic" });

            data.Add(new Languages() { Name = "C++" });

            data.Add(new Languages() { Name = "C#" });

            data.Add(new Languages() { Name = "dBase" });

            data.Add(new Languages() { Name = "Delphi" });

            data.Add(new Languages() { Name = "ESPOL" });

            data.Add(new Languages() { Name = "F#" });

            data.Add(new Languages() { Name = "FoxPro" });

            data.Add(new Languages() { Name = "Java" });

            data.Add(new Languages() { Name = "J#" });

            data.Add(new Languages() { Name = "Lisp" });

            data.Add(new Languages() { Name = "Logo" });

            data.Add(new Languages() { Name = "PHP" });

            return data;

        }



        public class Languages

        {

            public string Name;

        }





{% endhighlight %}



