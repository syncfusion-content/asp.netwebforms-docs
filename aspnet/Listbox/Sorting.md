---
layout: post
title: Sorting | ListBox | ASP.NET Webforms | Syncfusion
description: sorting support 
platform: aspnet
control: ListBox
documentation: ug
---

# Sorting

We can change ListBox items rendering order either as ascending or descending, by using "SortOrder" property. By default SortOrder will be "None". Please use code as like in below,
    

 {% tabs %}

    {% highlight html %}    
        <div class="grouplist">
           <span class="txt">Select a skill</span>
            <ej:ListBox ID="skillSetList" runat="server" DataTextField="skill" SortOrder="Descending" ></ej:ListBox>
        </div>
    {% endhighlight %}

{% highlight c# %}
 
        protected void Page_Load(object sender, EventArgs e)
        {

            List<SkillSet> veg = new List<SkillSet>();

            veg.Add(new SkillSet { skill = "F#" });
            veg.Add(new SkillSet { skill = "ActionScript" });
            veg.Add(new SkillSet { skill = "Delphi" });
            veg.Add(new SkillSet { skill = "Basic" });
            veg.Add(new SkillSet { skill = "C++" });
            veg.Add(new SkillSet { skill = "ESPOL" });
            veg.Add(new SkillSet { skill = "C#" });
            veg.Add(new SkillSet { skill = "DBase" });
            veg.Add(new SkillSet { skill = "ASP.NET" });
            skillSetList.DataSource = veg;
            }
    public class SkillSet
    {
        public string skill { get; set; }

    }
{% endhighlight %}
{% endtabs %}

Once you have used this code your output will be shown in like in the given below image,
![Sorting](Sorting-Images\img1.png)
