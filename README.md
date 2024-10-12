# ☕ Project Overview
---
This project is a sales dashboard for a coffee shop chain with three locations in New York City, United States. To better understand purchase behavior and streamline operations, the dataset includes transactional data from January to June 2023. The goal is to transform the data into a dynamic dashboard that franchise owners can use to identify patterns, trends and opportunities for the business. 

The project is composed of 3 main steps:
1. Profile and prepare the raw data for analysis
2. Explore the data with Pivot Tables
3. Build a dynamic dashboard to visualize patterns and trends

I will explain a little bit of the process I went through in each of the steps of the project.

# Prepare the Data for Analysis
---
So, the first step in any project always is to get familiarized with the data we will be working with. I explored the different columns included in the dataset (data points) as well as what type of data is included and identified if there were any cleaning or transformation required. The dataset has 149.116 records of transactional data of coffee shop sales. It includes a unique identifier for each transaction, a date and a time column of when the transaction occurred, the number of transaction included in the same record, the store identifier, the store location, the product identifier, the price of a unit of that product, and a breakdown of the product type ordered in 3 columns: first, general product category; product type, which becomes more granular and finally the product detail, which is the actual specific product that was ordered in the transaction. 

Highlighted in a different colors are the calculated columns that I added to the dataset for the purpose of this project, which are:
1. **Revenue:** (unit_price * transaction_qty)
2. **Month:** extracted the month number from the date column using Excel's `MONTH` function
3. **Month Name:** transformed the date column into a month name column using Excel's `TEXT` function
4. **Day of Week:** extracted the day of the week number from the date column using Excel's `WEEKDAY` function
5. **Day of Week Name:**  transformed the date column into a day of week name (Sunday, Monday, etc...) column using Excel's `TEXT` function
6. **Hour of Day:** extracted the hour of the day in number format from the time column using Excel's `HOUR` function

*Sample Data:*

![[1446-04-08 11_42_11-Coffee Shop Sales.xlsx - Excel.png]]
*NOTE:* *please note that in the "Transactions" sheet you might see the 'month_name' and 'day_of_week_name' column records written in Arabic. This is due to the regional formatting I use. However, this has been corrected to the English names of the months and weekdays in the final Dashboard and Pivot Tables.*
# Explore the Data with Pivot Tables
---
In this second step I created 5 Pivot Tables that summarize the data we have. I have hidden the Pivot Tables from the worksheet for aesthetic purposes, but if you wish to view them you can right click on the edge of the A column and select "Unhide" These Pivot Tables are as follows:
###### **Revenue by Month:** sums up the calculated 'revenue' column by month
![[1446-04-08 18_12_08-Coffee Shop Sales.xlsx - Excel.png]]
###### **Number of Transactions by Day of Week**
![[1446-04-08 18_15_18-Coffee Shop Sales.xlsx - Excel.png]]
###### **Number of Transactions by Hour of Day**
![[1446-04-08 18_15_36-Coffee Shop Sales.xlsx - Excel.png]]
###### **Number of Transactions by Product Category**
![[1446-04-08 18_15_51-Coffee Shop Sales.xlsx - Excel.png]]
###### **Top 15 by Number of Transactions, Revenue and Product Type:** this Pivot Table was included as part of the visualization dashboard 
![[1446-04-08 18_35_24-Coffee Shop Sales.xlsx - Excel.png]]

# Build Dashboard
---
The visual dashboard is composed of 5 visualizations: 1 line chart, 2 column charts, 1 bar charts and 1 table. The dashboard has a common design in regards to color and formatting throughout all charts. Clutter was removed and the area where I intend the viewer to focus on is highlighted in each chart title. The visualizations are as follows:

###### **Total Revenue by Month:** revenue evolution by each month in timeseries-like line chart
![[1446-04-08 18_35_51-Coffee Shop Sales.xlsx - Excel.png]]

###### **Transactions by Day of Week:** column chart displaying the total number of transactions by each day of the week (Tuesday, Wednesday, etc...)
![[1446-04-08 18_36_53-Coffee Shop Sales.xlsx - Excel.png]]

###### **Transactions by Hour of Day:** column chart displaying the total number of transactions by each hour of the day. Keep in mind that the shops open at 6:00 and close at 20:00
![[1446-04-08 18_42_18-Coffee Shop Sales.xlsx - Excel 1.png]]

###### **Transactions by Product Category:** bar chart displaying the total number of transactions by each product category (Coffee, Tea, Bakery, etc...)
![[1446-04-08 18_42_54-Coffee Shop Sales.xlsx - Excel.png]]

###### **Top 15 Products:** table chart displaying the highest 15 products in terms of revenue and total number of transactions. This chart is sorted in descending order based on the transactions
![[1446-04-08 18_35_24-Coffee Shop Sales.xlsx - Excel 1.png]]

In addition to these charts, I've added a slicer that filters the data in all charts based on the store location:
![[1446-04-08 18_36_26-Coffee Shop Sales.xlsx - Excel.png]]

# Observations and Actions
---
## OVERALL
---
- Most sold product categories are Coffee and Tea, with a total of 103.865 or about 70% of total transactions. This is expected as it is a coffee shop and of course coffee and tea are the main products and the main drivers for success. This means that we need to focus on providing the best quality in these beverages.
- Revenue has been gradually increasing month by month, except for a small dip in February noticed across all store locations and probably caused by February being a shorter month (28-29 days). The highest revenue per month was generated in June
- The most productive days of the week are Mondays, Thursdays and Fridays
- The most productive hours of the day are from 7:00 to 10:00. This is the breakfast time and it's when we got the highest number of customers. The number of transactions of 20:00 is extremely low, so perhaps it would be a good decision to close the coffee shops sooner, at 19:00 for example, to avoid low productivity.
- All our store locations generate similar revenues, ranging from 230k to 236k per store, that means we're maintaining a good quality standard among all our stores

Now let's look at some observations we can derive from our dashboard broken down by each store location.

## ASTORIA
---
- Total revenue generated by store is <font color="#fac08f">230.057$</font> and total of number of transactions is <font color="#b2a2c7">50.599</font>
- The Astoria store location only gets orders from 7:00 to 19:00, so it makes sense to have those as the opening and closing times.
- Days of the week with the most transactions are Mondays, Wednesdays, Thursdays and Fridays. No interesting pattern here other than they are work days and there are less transactions on weekends.
- The most sold product categories are Coffee and Tea with a total of <font color="#b2a2c7">36.285</font> transactions, which makes up 72% of store transactions; followed by Bakery with <font color="#b2a2c7">7.289</font> transactions, which makes up 14% of store transactions.
- The 3 most sold products at this store are "Brewed Chai tea", "Gourmet brewed coffee" and "Barista Espresso" with a total of <font color="#b2a2c7">17.276</font> transactions (34% of total store transactions) and a total of <font color="#fac08f">79.186$</font> in revenue (34% of total store revenue).

## HELL'S KITCHEN
---
- Total revenue generated by store is <font color="#fac08f">230.057$</font> and total of number of transactions is <font color="#b2a2c7">50.735</font>
- The Hell's Kitchen store location, similar to the Astoria location, does not get many orders past 19:00, so it would make sense to open the store from 6:00 to 19:00.
- Days of the week with the most transactions are Sundays, Tuesdays and Fridays.
- The most sold product categories are Coffee and Tea with a total of <font color="#b2a2c7">35.464</font> transactions, which makes up 70% of store transactions; followed by Bakery with <font color="#b2a2c7">7.617</font> transactions, which makes up 15% of store transactions.
- The 3 most sold products at this store are "Barista Espresso", "Brewed Chai tea" and "Gourmet brewed coffee" with a total of <font color="#b2a2c7">17.619</font> transactions (35% of total store transactions) and a total of <font color="#fac08f">81.075$</font> in revenue (34% of total store revenue)

## LOWER MANHATTAN
---
- Total revenue generated by store is <font color="#fac08f">230.057$</font> and total of number of transactions is <font color="#b2a2c7">47.782</font>
- The Lower Manhattan store location gets a very low amount of orders after 18:00, so it would be better in order to avoid low productivity and not lose money on keeping the store open unnecessarily to open at 6:00 and close at 18:00
- Days of the week with the most transactions are Mondays with some difference, followed by Thursdays. Mondays are the top likely due to the start of the work week and people coming to the coffee shop to have breakfast during their commute, especially since Lower Manhattan is a business district.
- The most sold product categories are Coffee and Tea with a total of <font color="#b2a2c7">32.116</font> transactions, which makes up 67% of total store transactions; followed by Bakery with <font color="#b2a2c7">7.890</font> transactions, which makes up 17% of store transactions.
- The 3 most sold products at this store are "Barista Espresso", "Gourmet brewed coffee" and "Brewed Chai tea" with a total of <font color="#b2a2c7">15.603</font> transactions (33% of total store transactions) and a total of <font color="#fac08f">78.261$</font> in revenue (34% of total store revenue)