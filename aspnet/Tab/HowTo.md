---
layout: post
title: How to - Tab control for Syncfusion ASP.NET Webform
description: How To Section in Tab control for Syncfusion ASP.NET Webform
platform: aspnet
control: Tab
documentation: ug
---

# How To

## Validate input controls in active tab alone. 

When clicking the submit button on page, validation is done for all the controls by default, and it is not done based on active tab. This can be customized using EJ Validation and active event of Tab. EJ Validation will be done with jQuery validator, and the jQuery.validate.min.js script file has to be referred in master page for this validation. By default, the jQuery validation ignores all the hidden elements in the form, but for some of our controls, you need to validate hidden elements using specific validator code. Refer to [Validation](https://help.syncfusion.com/aspnet/validation#jquery-validation) document for more details on EJ Validation. You can get the active content of tab through its class name in the create and active events of tab, and you need to add a common class name for all the controls to be validated in active tab. Then, add the ignore value in validator method based on this class name. Include setTimeout in create event to add class name for controls after rendering all the child controls inside tab. Refer to the following code.

{% tabs %}

    {% highlight html %}

        <ej:Tab ID="container" runat="server" ClientSideOnActive="Active" ClientSideOnCreate="Create">
         <Items>
             <ej:TabItem ID="First" Text="Disbursement">
                 <ContentSection>
                     <ej:Autocomplete ID="AutoComplete1" Width="300px" runat="server" DataTextField="Text" DataUniqueKeyField="ID" MultiSelectMode="VisualMode" ShowPopupButton="true">
                         <ValidationRule>
                             <ej:KeyValue Key="required" Value="true" />
                         </ValidationRule>
                         <ValidationMessage>
                             <ej:KeyValue Key="required" Value="* required" />
                         </ValidationMessage>
                     </ej:Autocomplete>
                     <br />
                     <ej:DatePicker runat="server" ID="datepick" Width="100%">
                         <ValidationRule>
                             <ej:KeyValue Key="required" Value="true" />
                         </ValidationRule>
                         <ValidationMessage>
                             <ej:KeyValue Key="required" Value="* required" />
                         </ValidationMessage>
                     </ej:DatePicker>

                 </ContentSection>
             </ej:TabItem>
             <ej:TabItem ID="second" Text="Batch process">
                 <ContentSection>
                     <ej:DatePicker runat="server" ID="DatePicker1" Width="100%">
                         <ValidationRule>
                             <ej:KeyValue Key="required" Value="true" />
                         </ValidationRule>
                         <ValidationMessage>
                             <ej:KeyValue Key="required" Value="* required" />
                         </ValidationMessage>
                     </ej:DatePicker>
                     <br />
                     <ej:DropDownList ID="selectCar" runat="server" WatermarkText="Select a car" Width="100%">
                         <Items>
                             <ej:DropDownListItem Text="Audi A4" Value="Audi A4"></ej:DropDownListItem>
                             <ej:DropDownListItem Text="Audi A5" Value="Audi A5"></ej:DropDownListItem>
                             <ej:DropDownListItem Text="Audi A6" Value="Audi A6"></ej:DropDownListItem>
                             <ej:DropDownListItem Text="Audi A7" Value="Audi A7"></ej:DropDownListItem>
                             <ej:DropDownListItem Text="Audi A8" Value="Audi A8"></ej:DropDownListItem>
                         </Items>
                         <ValidationRule>
                             <ej:KeyValue Key="required" Value="true" />
                         </ValidationRule>
                         <ValidationMessage>
                             <ej:KeyValue Key="required" Value="* required" />
                         </ValidationMessage>
                     </ej:DropDownList>
                 </ContentSection>
             </ej:TabItem>
         </Items>
     </ej:Tab>
          
	{% endhighlight %}

    {% highlight js %}

        <script>
         $.validator.setDefaults({
            ignore: ":hidden:not(input.e-form-validate)",
            errorClass: 'e-validation-error', // to get the error message on jquery validation
            errorPlacement: function (error, element) {
                $(error).insertAfter(element.closest(".e-widget"));
            }
        });
        function Active() {
            $("#MainContent_container").find(".e-form-validate").removeClass("e-form-validate");
            $("#MainContent_container").find(".e-active-content").find("input:hidden").addClass("e-form-validate");
        }

        function Create() {
            setTimeout(function () {
                $("#MainContent_container").find(".e-active-content").find("input:hidden").addClass("e-form-validate");
            }, 0)
        }

    </script>

    {% endhighlight %}
    
    {% highlight c# %}

        protected void Page_Load(object sender, EventArgs e)
         {
            this.AutoComplete1.DataSource = new Data().Items().ToList();       
         }
        public class Data
       {
        public Data(int _id, string _text, string Category)
        {
            this.ID = _id;
            this.Text = _text;
            this.Category = Category;
        }
        public Data() { }
        public int ID
        {
            get;
            set;
        }
        public string Text
        {
            get;
            set;
        }
        public string Category
        {
            get;
            set;
        }
        public List<Data> Items()
        {
            List<Data> data = new List<LocalData>();
            data.Add(new Data(1, "Audi S6", "a"));
            data.Add(new Data(2, "Austin-Healey", "a"));
            data.Add(new Data(3, "Maruti", "a"));
            data.Add(new Data(4, "BMW 7", "b"));
            data.Add(new Data(5, "Honda", "h"));
            return data;
        }
    }
 
    {% endhighlight %}
    
{% endtabs %}

Sample can be downloaded [here](http://www.syncfusion.com/downloads/support/directtrac/228450/ze/SyncfusionEJValidation1538397475 )

