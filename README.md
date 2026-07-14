
## Introduction

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

## Tools Used

- **PowerBI**
    - Power Query: Used to load and transform the dataset.
    - Dax: Used to create measures to further analyze the data model.
    - Charts: Used to visualize the dataset and allow filter via interacting with the charts.
    - Slicers: Used to allow user interaction in filters the dataset.
    - Parameters: Used to allow the swapping of labels/axis measurements via slicers.
    
## Dataset

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


## Territories
<p align="center">
  <img src="assets/homepage.png" width="800">
</p>

For the dashboard there are 3 pages, focusing on the territories, customers, and products. To navigate between these pages I created a homepage with navigations buttons. Each of the dashboards also include a back button in the top left which navigates back to the homepage.
## Customers


## Products