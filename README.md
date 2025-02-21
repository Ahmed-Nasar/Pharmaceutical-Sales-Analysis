# Pharmaceutical Sales Analysis

[![Open In Power Bi](https://img.shields.io/badge/open_in_power_bi-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://app.powerbi.com/view?r=eyJrIjoiYzg3YzU2ZTUtZjRlNS00OWQ2LWFiM2ItYjM1OTNkOWI4ODA5IiwidCI6IjI1Y2UwMjYxLWJiZDYtNDljZC1hMWUyLTU0MjYwODg2ZDE1OSJ9)

In this ‘Data Analysis’ project, we’ll analyze a global Pharmaceutical Manufacturing Company's raw sales data and draw meaningful insights.

![Image](https://github.com/user-attachments/assets/e62b3373-bb26-4b28-b16f-36fcdf322103)

## Project Overview:

* This company is one of the leading Pharmaceutical Manufacturing companies with a global presence. 
* Their Markets are divided into different regions across the world. One of those regions manages the German and Poland Markets. 
* Company does not sell directly to customers. Instead, they work with a couple of Distributors in all their regions. 
* They have an agreement with each distributor to share their Sales Data. This is to enable them to gain insights up to the retail level. This data is made available to them in CSV format.

## Dataset Description:

The dataset is sourced from each distributor. It contains Pharmaceutical Manufacturing Company’s, Wholesale-Retail Data. The field description of the raw data is given below. The raw dataset `pharma-data.csv` can be downloaded from [Kaggle](https://www.kaggle.com/datasets/akanksha995579/pharma-data-analysis)

## Columns Description:

|Field|Description|
|:---|:--|
|Distributor| Name of Wholesaler|
|Customer Name| Name of customer|
|City| Customer's city|
|Country| Customer's country|
|Latitude| Customer's Geo Latitude|
|Longitude| Customer's Geo Longitude|
|Channel|Class of buyer (Hospital, Pharmacy)|
|Sub-channel|Sector of the buyer (Government, Private, etc.)|
|Product Name|Name of Drug|
|Product Class|Class of Drug (Antibiotics, etc.)|
|Quantity|Quantity purchased|
|Price|Price product was sold for|
|Sales|Amount made from sale|
|Month|Month sale was made|
|Year|Year sale was made|
|Name of Sales Rep|Name of the Sales rep who facilitated the sale|
|Manager|Sales rep's Manager Name|
|Sales Team|Sale rep's team|

### Exploratory Data Analysis (EDA) [pandas]
To understand, be familiar with and check the sanity of the given data, the first step is EDA. This project's initial data exploration has been carried out using the `pandas` python package. Here, in general, we are checking... 
 * Presence of any missing values 
 * Any unusual value (outliers) 
 * Incorrect values (e.g., sales column, we see -ve numbers)
 * Determine `categorical` and `numeric` columns
 * Determine dimensions of categorical columns and range of numeric columns
Note that these steps can be performed using `PowerQuery Editor` and/or excel; however, `pandas` makes it much easier and faster; on top of that, `pandas` can handle massive datasets.

EDA steps can be found in the `data-exploration.ipynb` notebook.

### Data Cleaning and Transform [PowerQuery Editor]
The provided dataset was relatively clean and well organized; hence only a little work was required in this step; the following steps were carried out...
* Correct column heading provided
* Correct data type is assigned to columns

### Data Model Creation [PowerBI Desktop]
* The provided data is in a single table format. The exploration revealed that it contains both categorical (`dimensions`) and numeric (`facts`) data. 
* We build a data model where dimensions and facts are separated, then they are linked together by logical relationship to form a `star schema.` The resultant data model is shown below...

<img src="https://github.com/sssingh/pharmaceutical-sales-analysis-powerbi/blob/main/images/data-model.png?raw=true"/>

The tables with the prefix `DIM` are dimension tables, and `FACT` is the fact table.
