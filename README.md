
# Introduction

This is the fourth of four project meant to showcase my knowledge of GitHub and various data science tools, such as PowerBI. For this project, I worked with relational database documenting customers, products and sales for a store that sells bicycles and related accessories. Utilizing PowerBI I created an interable dashboard for exploring the dataset and revenue by three major aspects:

1. Territory
2. Customer demographics
3. Product category

Below you can see screenshots of the three dashboards. At the bottom of the README there is also a gif of each showcasing them being used.

<p align="center">
  <img src="assets/territories_dashboard.png" width="800">
</p>

<p align="center">
  <img src="assets/customers_dashboard.png" width="800">
</p>

<p align="center">
  <img src="assets/products_dashboard.png" width="800">
</p>

# Tools Used

- **PowerBI**
    - Power Query: Used to load and transform the dataset.
    - DAX: Used to create measures to further analyze the data model.
    - Charts: Used to visualize the dataset and allow filter via interacting with the charts.
    - Buttons: Used to allow navigation between pages and clearing of slicers.
    - Slicers: Used to allow user interaction in filters the dataset.
    - Parameters: Used to allow the swapping of labels/axis measurements via slicers.
    
# Dataset

To make the PowerBI file function on your computer you may need to update the filepaths for the dataset files. Follow these steps:

- Download the AdventureWorks_project.pbix file and all six csv/xlsx files from the dataset folder.
- Open the PowerBI (.pbix) file.
- Open the Get transform data dropdown on the home ribbon and click Data Source Settings.
- Go through each of the six listed data sources and click the "Change Source" option in the bottom left, updating the source files to where they are locally stored on your computer (make sure you select the correct file).

<p align="center">
  <img src="assets/data_model.png" width="800">
</p>

The dataset is sourced from a simplified version of the [AdventureWorks](https://dataedo.com/samples/html/AdventureWorks/doc/AdventureWorks_2/home.html) dataset found on [Kaggle](https://www.kaggle.com/datasets/sprasad018/adventureworks-dataset?resource=download).

The dataset, as visualized above, cointains 5 tables. The most important tables is the Sales table which documents orders over the course of multiple years for the business. The other tables all store relevant data to those orders.

The Customer table stores data on customers with some demographic data such as birth date, education level, gender, and more.

The territories table stores data on the multiple territories of operations and some of their sub divisions.

The Product tabel stores data on all the offered products with details such as price, and category. The categories are assigned from the product's relationship with the Product_Subcategories and Product_Categories tables.

Once loaded I cleaned the dataset with power query, removing uneeded columns and fixing the auto-assigned data types. For more in depth usage, check out my Excel project which used power query significantly more.


# Homepage
<p align="center">
  <img src="assets/homepage.png" width="800">
</p>

For the dashboard there are 3 pages, focusing on the territories, customers, and products. To navigate between these pages I created a homepage with navigations buttons. Each of the dashboards also include a back button in the top left which navigates back to the homepage.

On the homepage and other pages are cards that highlight singular key takeaway values. In the above example the total revenue, count of unique customers, and total orders placed are highlighted. These were created utilizing a card visual. Some of these values are simple aggregation such as the toal orders placed which was a count distinct aggregation on the OrderNumber (ID) in the sales table. The revenue caluclations we more complex because I needed to calculate the revenue for each order which requires using values from multiple tables. I created a calculated column in the sales table which calculated the revenue of an order with the following DAX code:
```
OrderRevenue = Sales[OrderQuantity] * RELATED(Products[ProductPrice]) 
``` 
With the calculated column, the rest was simple using a sum aggregation on said column. OrderRevenue is later used as the base for calculation other values such as the total revenue from a territory or a single customer. 

# Territories

<p align="center">
  <img src="assets/territories_dashboard.png" width="800">
</p>

In addtional to cards and charts, I used parameters to allow the user to customize the unit of an axis or the labels. In the territories dashboard the user can swap between looking at contient values and region values. Additonally, they can swap between a y-axis measurement of revenue, orders, or items sold.

<p align="center">
  <img src="assets/parameter_table.png" width="800">
</p>

Using the parameter section of the modeling tab, I created parameters for territory/region, and revenue/orders/items. This creates a table which can then be used in axis section of building a visual.

<p align="center">
  <img src="assets/visual_building.png" width="175">
</p>

# Customers


# Products


# Showcase

<p align="center">
  <img src="assets/territories.gif" width="800">
</p>

<p align="center">
  <img src="assets/customers.gif" width="800">
</p>

<p align="center">
  <img src="assets/products.gif" width="800">
</p>