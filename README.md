# LITA_CAPSTONE_PROJECT-2
### Project Tittle: Customer Segmentation For A Subscription Service

### Project overview
This data Analysis Project is done to analyse the customer data for a subscription service to identify segments and trends

#### Data Sources
The primary Source of Data used here is LITA Capstone Dataset.xlsx

### Tools Used
- Microsoft Excel
 1. For Data Cleaning
 2. For Analysis
 3. For Data Visualization
 
- SQL- Structured Query Language for Querying of Data
- Power Bi- for creating Dashboard
- Github for portfolio Building

### Data Cleaning and Praparation
 In this process,duplicates were Removed, the Data was filtered and sorted

 ### Exploratory Data Analysis
 The data was explored to deduce the following:
 - Track subcription types
 - Identify key trends in cancellations and renewals

  ### Excel
 Excel was used to find subscription pattern, the average subsription duration and the most popular subscription type
 The subsription patterns are shown in this visual and they are the customers in each region, the customers and the subscription type and the sum of revenue gotten from each region

![pivot 2](https://github.com/user-attachments/assets/ecd492e5-d935-4c29-8639-85e6a3b0a068)

### Sql
These are the Queries used to retrieve information 

### The total number of customers for each region
select Region, count(customerID) as Total_No_Of_Customers
from[dbo].[Customer data 2]
group by region


### Most popular subscription type by number of Customers
select subscriptiontype, count (customerid) as no_of_customers
from[dbo].[Customer data 2]
group by subscriptiontype

### Customers who canceled their subscription within 6 months
select customername,canceled,subscriptionstart
from[dbo].[Customer data 2]
where canceled =0 and Month(subscriptionstart)between 1 and 6

### Average subscription duration
Select count (customerid)as all_customers,
Select count(customerid) as ALL_Customers,
avg(datediff(day,subcriptionstart,suubscriptionend)
as Average_Subscription_Duration from [dbo].[Customer data 2]
where subscriptionend is not null

### Customers with subscription longer than 12 months
Select customername, subscriptionstart, subscriptionend
from [dbo].[Customer data 2]
where datediff(month,subscriptionstart,subscriptionend)>=12

### Total revenue by subcription type
select subscriptiontype,sum(revenue) as Total_Revenue
from[dbo].[Customer data 2]
group by subscriptiontype


### Top 3 region by subsription cancellations
select top 3 region canceled from[dbo].[Customer data 2]

### Total number of active and canceled subscription
select
sum(case when canceled = 0 then 1 else 0 end) as activesubscriptions
sum (case when canceled = 1 then 1 else 0 end) as canceledsubscriptions
from[dbo].[Customer data 2]
group by customerid

### Dashboard
This dashboard shows the Customers in each Region, the Customers and their subsription type, the sum of Revenue by subscription type, cancellations,and the slicer used was the Subscription type

![Customer Subscription dashboard](https://github.com/user-attachments/assets/8f31afe7-4c79-4dd9-96b4-69c64b2a9335)

