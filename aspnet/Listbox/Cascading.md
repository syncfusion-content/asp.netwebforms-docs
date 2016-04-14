---
layout: post
title: Cascading | ListBox | ASP.NET Webforms | Syncfusion
description: cascading support 
platform: aspnet
control: ListBox
documentation: ug
---

# Cascading 

We can dynamically populate data of a list box while selecting an item in another list box i.e. rendering child list box based on the item selection in parent list box. This can be achieved using “CascadeTo” property.

In the design page, add two list boxes and in code behind create data sources and assign it. The parent child relationship should be defined in data sources of both the list boxes. I.e. both data sources should contain a common field for mapping (just like [primary key and foreign key definitions](https://msdn.microsoft.com/en-IN/library/ms179610.aspx)).

The parent ListBox widget’s “CascadeTo” property should point to its child ListBox widget by specifying the id of the child ListBox widget. The child ListBox widget can be displayed with empty data on initialize by setting its “LoadDataOnInit” property as false.

N> In the above data source definition, the “CategoryId” column is act as a primary key to define the parent-child relationship.


{% tabs %}

{% highlight html %}

<div class="parentlistbox">
        <!--parent listbox element-->
        <ej:ListBox ID="maincategory" runat="server"></ej:ListBox>
    </div>
    <div class="childlistbox">
        <!-- child listbox element-->
        <ej:ListBox ID="subcategoryList" runat="server"></ej:ListBox>
    </div>
    <style>
        .parentlistbox, .childlistbox {
            padding: 10px;
            float: left;
        }
    </style>

{% endhighlight %}

{% highlight c# %}

 protected void Page_Load(object sender, EventArgs e)
            {

                List<MainCategory> category = new List<MainCategory>();
                category.Add(new MainCategory { CategoryId = 'a', Text = "Clothing" });
                category.Add(new MainCategory { CategoryId = 'b', Text = "Furniture" });


                List<SubCategory> scategory = new List<SubCategory>();
                scategory.Add(new SubCategory { SubCategoryId = 11, CategoryId = 'a', Text = "Men" });
                scategory.Add(new SubCategory { SubCategoryId = 12, CategoryId = 'a', Text = "Women" });
                scategory.Add(new SubCategory { SubCategoryId = 13, CategoryId = 'b', Text = "Home furniture" });
                scategory.Add(new SubCategory { SubCategoryId = 14, CategoryId = 'b', Text = "Bedding" });


                maincategory.DataSource = category;
                maincategory.DataValueField = "CategoryId";
                maincategory.CascadeTo = "LayoutSection_subcategoryList";

                subcategoryList.DataSource = scategory;
                subcategoryList.LoadDataOnInit = false;
            }
        }
        public class MainCategory
        {
            public string Text;
            public char CategoryId;
        }
        public class SubCategory
        {
            public string Text;
            public char CategoryId;
            public int SubCategoryId;
        }
   
{% endhighlight %}

{% endtabs %}

![](Cascading_images/Cascading_img1.png)

## Multilevel cascading

Please refer the below code snippets which is expanded from the above example, to achieve multi-level (three level here) cascading of the ListBox widgets.

In the design page, add four list boxes and create the data sources for the list boxes and assign it.

In the code behind add the below codes.

{% tabs %}

{% highlight html %}


<div class="listboxcontrol">
        <!--parent listbox element-->
        <ej:ListBox ID="maincategory" runat="server"></ej:ListBox>
    </div>
    <div class="listboxcontrol">
        <!-- First level child listbox element-->
        <ej:ListBox ID="subcategoryList" runat="server"></ej:ListBox>
    </div>
    <div class="listboxcontrol">
        <!-- second level child listbox element-->
        <ej:ListBox ID="productList" runat="server"></ej:ListBox>
    </div>
    <div class="listboxcontrol">
        <!-- second level child listbox element-->
        <ej:ListBox ID="subproductList" runat="server"></ej:ListBox>
    </div>
    <style>
        .listboxcontrol {
            padding: 10px;
            float: left;
        }
    </style>



{% endhighlight %}

{% highlight c# %}

public partial class Cascading : System.Web.UI.Page
    {
        protected void Page_Load(object sender, EventArgs e)
        {

            List<MainCategory> category = new List<MainCategory>();

            category.Add(new MainCategory { CategoryId = 'a', Text = "Clothing" });
            category.Add(new MainCategory { CategoryId = 'b', Text = "Furniture" });

            List<SubCategory> scategory = new List<SubCategory>();
            scategory.Add(new SubCategory { SubCategoryId = 11, CategoryId = 'a', Text = "Men" });
            scategory.Add(new SubCategory { SubCategoryId = 12, CategoryId = 'a', Text = "Women" });
            scategory.Add(new SubCategory { SubCategoryId = 13, CategoryId = 'b', Text = "Home furniture" });
            scategory.Add(new SubCategory { SubCategoryId = 14, CategoryId = 'b', Text = "Bedding" });

            List<ProductList> productlist = new List<ProductList>();
            productlist.Add(new ProductList { SubCategoryId = 11, ProductId = 101, Text = "men shirts" });
            productlist.Add(new ProductList { SubCategoryId = 11, ProductId = 102, Text = "men pants" });
            productlist.Add(new ProductList { SubCategoryId = 12, ProductId = 103, Text = "Women shirts" });
            productlist.Add(new ProductList { SubCategoryId = 12, ProductId = 104, Text = "Women pants" });
            productlist.Add(new ProductList { SubCategoryId = 13, ProductId = 105, Text = "sofa" });
            productlist.Add(new ProductList { SubCategoryId = 13, ProductId = 106, Text = "chairs" });
            productlist.Add(new ProductList { SubCategoryId = 14, ProductId = 107, Text = "bedsheets" });
            productlist.Add(new ProductList { SubCategoryId = 14, ProductId = 108, Text = "pillows" });


            List<SubProductList> subproductlist = new List<SubProductList>();
            subproductlist.Add(new SubProductList { ProductId = 101, Text = "red men shirts" });
            subproductlist.Add(new SubProductList { ProductId = 101, Text = "blue men shirts" });
            subproductlist.Add(new SubProductList { ProductId = 102, Text = "red men pants" });
            subproductlist.Add(new SubProductList { ProductId = 102, Text = "blue men pants" });
            subproductlist.Add(new SubProductList { ProductId = 103, Text = "red Women shirts" });
            subproductlist.Add(new SubProductList { ProductId = 103, Text = "blue Women shirts" });
            subproductlist.Add(new SubProductList { ProductId = 104, Text = "red Women pants" });
            subproductlist.Add(new SubProductList { ProductId = 104, Text = "blue Women pants" });
            subproductlist.Add(new SubProductList { ProductId = 105, Text = "red sofa" });
            subproductlist.Add(new SubProductList { ProductId = 105, Text = "blue sofa" });
            subproductlist.Add(new SubProductList { ProductId = 106, Text = "red chairs" });
            subproductlist.Add(new SubProductList { ProductId = 106, Text = "blue chairs" });
            subproductlist.Add(new SubProductList { ProductId = 107, Text = "blue bedsheets" });
            subproductlist.Add(new SubProductList { ProductId = 107, Text = "red bedsheets" });
            subproductlist.Add(new SubProductList { ProductId = 108, Text = "red pillows" });
            subproductlist.Add(new SubProductList { ProductId = 108, Text = "blue pillows" });


            maincategory.DataSource = category;
            maincategory.DataValueField = "CategoryId";
            maincategory.CascadeTo = "LayoutSection_subcategoryList";

            subcategoryList.DataSource = scategory;
            subcategoryList.LoadDataOnInit = false;
            subcategoryList.DataValueField = "SubCategoryId";
            subcategoryList.CascadeTo = "LayoutSection_productList";

            productList.DataSource = productlist;
            productList.LoadDataOnInit = false;
            productList.DataValueField = "ProductId";
            productList.CascadeTo = "LayoutSection_subproductList";

            subproductList.DataSource = subproductlist;
            subproductList.LoadDataOnInit = false;
        }
    }
    public class MainCategory
    {
        public string Text;
        public char CategoryId;
    }
    public class SubCategory
    {
        public string Text;
        public char CategoryId;
        public int SubCategoryId;
    }
    public class ProductList
    {
        public string Text;
        public int ProductId;
        public int SubCategoryId;
    }
    public class SubProductList
    {
        public string Text;
        public int ProductId;
    }


{% endhighlight %}

{% endtabs %}


![](Cascading_images\Cascading_img2.png)


