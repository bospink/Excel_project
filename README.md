# Online Store Sales Report

## Table of Contents

- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Cleaning](#data-cleaning)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Findings](#findings)
- [Recommendations](#recommendations)

### Project Overview
---

This Data Analysis Excel Dashboard Project aims to provide insights into sales performance of an online store over the past years (2015 - 2023). 

I created a visually appealing, informative and interactive dashboard that showcases important insights and trends within a dataset by using Excel's various tools and features to transform faw data into meaningful and actionable information that stakeholders can easily understand.


![GIF_Dashboard](https://github.com/bospink/Excel_project/assets/126882792/ef6a9b84-c841-450a-8dba-802e31a8f237)


### Data Sources

Sales Data: I got csv files from *Etsy Download Shop Data*, the *"Order Item"* CSV for each year (report of shop sales at an individual item level). Then I combined those CSV files into one Excel workbook named "PinkBau2015_2023", containing detailed information about each sale made by the store.

### Tools

- **Excel** - Data Cleaning - Data Analysis - Pivot Tables - Dashboard

### Data Cleaning

1. Data loading and inspection

To combine multiple csv files into one Excel workbook, these are the steps I followed:

- Put all my CSV files into one folder. 
On the Data tab, in the Get & Transform Data group, I clicked `Get Data > From File > From Folder`

- In the **Combine** drop-down menu I selected *Combine & Load*, which loads the combined data straight into a new worksheet as a table.

![Screenshot 0](https://github.com/bospink/Excel_project/assets/126882792/788cd954-29ac-4a23-8074-b4f2d3e2ce71)


2. Handling missing values and blank rows

I looked for missing values and the dataset doesn't have them, only some empty rows between the merged csv files that I deleted.

3. Data cleaning and formatting

I needed to make sure my data is correct and in the format I need it.

I started with the `Item name` column by using **IF + COUNTIF** formula that matches a value to multiple conditions. This way I classified sold items into product categories like on the store website to make it easier for further analysis and data presentation. Then I created a new column called `Product` which contains only values without formula (Ctrl+V).

I did the same formula with the column `Ship Country` to sort all countries where sales occurred in 5 most important markets for the store: *United States, United Kingdom, Canada, Europe and Other* (all other countries that do not belong to the previous four). I also created a new column called `Country` which contains only values without formula.

<img width="1470" alt="Screenshot 3" src="https://github.com/bospink/Excel_project/assets/126882792/200bf7da-ae99-4874-a58e-545cb21b620b">

I checked for each column data type and changed the `Sale Date` data type to *Date* format: **dd/mm/yy** (`Home > Transform > Data Type`, and then select the *Date* option)

Next, I used **TEXT** Function to Get Year, Month and Weekday from `Sale Date` column: 
- `=TEXT(B2;"YYYY")`
- `=TEXT(B2;"MMMM")` 
- `=TEXT(B2;"DDDD")`

<img width="1470" alt="Screenshot 2" src="https://github.com/bospink/Excel_project/assets/126882792/0502159c-861a-4b61-a017-1502acb2cd7e">

To easily identify trends and patterns I sorted by the oldest `Sale Date` clicking on the **Sort** button in the **Data tab** and select *Sort Oldest to Newest*

Finnaly, I removed some unnecessary columns for further analysis and started creating a pivot table by selecting `Insert > Pivot Table` from the ribbon (**Create Pivot Table**: Select a table or range: *EtsySoldItems* and place the Pivot Table in *New worksheet*). This new sheet I named KPI (*key performance indicator*) where the Pivot Tables will be placed (a quick way to make an interactive summary from many records).


### Exploratory Data Analysis

This is the step where I needed to think about the design of the dashboard and what pivot tables to create.

EDA involved exploring the sales data to answer key questions, such as:

- What is the overall sales trend?
- Which products are top sellers?
- What is the best weekday for sales / the best selling month by year?

I started with making the first pivot table *Total Revenue by Year* by dragging and dropping the fields in the `PivotTable Fields` pane (for example: move fields between the rows, columns, values, and filters areas, or change the order and hierarchy of the fields, choose different layout options such as showing or hiding subtotals, grand totals or field headers). 

Then I presented it using a bar chart (`Table Analyse > PivotChart`).

I styled pivot chart by changing the chart type, adding or removing chart elements, applying different colors and effects by going on `Chart Tools` tabs on the ribbon, or right-click on the chart and select the desired commands (for example: add or remove a title, legend, axis, gridlines, or data labels, or change the fill, outline, or shape of the chart elements).

With the second pivot table, I wanted to show the *Revenue by Markets over Years*, so I decided on a line chart.

<img width="1470" alt="Screenshot 6" src="https://github.com/bospink/Excel_project/assets/126882792/9513d45e-716b-45af-8b89-3d627febd1dc">


For the *Best Selling Products* I used doughnut chart with values shown as percentages to better highlight the product with the largest portion. 

*Best Day of the Week for Sales* is presented in the form of a pie chart with values also in percentages, and for *Number of Products Sold by Month* I decided on a bar chart. 

Finally I wanted to put the **Year** filter for the last three charts so I went to the `Pivot Chart Analyse > Insert Slicer` and then I right-clicked on the slicer made, *Report Connections*, after what I selected these last three Pivot Tables to connect to this filter. 

<img width="1470" alt="Screenshot 7" src="https://github.com/bospink/Excel_project/assets/126882792/31d6cdf0-8d8f-4125-a3b7-f28756490455">



Now it's time to create a new sheet for the **Dashboard**.



In the upper part I will place the logo and title (explanation about the report). 

I chose a theme for my Dashboard `Page Layout > Themes` so that the colors and style were uniform for all elements.

Right below the upper part will go three striking elements that will contain information about **Total Revenue**, **Total Purchases** and **Unique Country** (where the sale took place).

Then I inserted two shapes that I aligned using `Format > Align > Align to Middle` so that everything would be aesthetically pleasing. 
I did the same thing with inserting another four shapes below them.

Then I copy/paste my charts each to its own shape, aligned them a bit and changed what was needed (remove axises or change title).

I also added the **Year** filter to make it easier to see the changes and answer the questions: *Which products are top sellers? What is the best weekday for sales / the best selling month by year?*

My interactive Dashboard is complete.

<img width="1028" alt="Screenshot 9" src="https://github.com/bospink/Excel_project/assets/126882792/d8ae1ee7-5429-4f7b-9bb5-c83f5f63ef8c">


### Findings
---
The anlaysis results are summarized as follows:

1. The store sales have been steadily increasing over the past years reaching a noticable peak during 2022. Then there would be a slight drop caused by the change in the taxation for the store in 2023 and thus the increase in product prices.

2. Product Category *Litter Box Cabinet* is the best-performing category in terms of sales and revenue.

3. Most sales occur during the weekend and the best period for sales is at the end of the year, which is expected due to the holidays, and the month of May stands out as a consistently good month (end of spring). 

### Recommendations
---
- Invest in marketing and brand promotion which will lead to an increase in demand for the product and thus the level of sales will be maintained.
- Focus on expanding and promoting products in *Litter Box Cabinet* category.
- Encourage the purchase of products in the first months of the year with a help of coupons and weekly discounts.
