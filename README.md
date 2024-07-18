![Header](./assets/liquor_header.png)

![Static Badge](https://img.shields.io/badge/rows_of_data_analyzed-12%2C523%2C335-red?color=D93F07)
![GitHub commit activity](https://img.shields.io/github/commit-activity/t/dee-wright/liquor-sales-analysis?color=D97D0D)
![GitHub repo size](https://img.shields.io/github/repo-size/dee-wright/liquor-sales-analysis?color=D96B0B)


# Liquor Sales Analysis (2018-2022)
The state is the wholesaler for class E liquor retailers. All alcoholic beverages stocked by class E liquor retailers must be purchased through the state Alcoholic Beverages Department (ABD) portal.  

## Overview
Between 2018 and 2022, 12.5 million orders were placed with the state Alcoholic Beverages Department, for a total of $1.9 billion in sales. These orders were placed by 2,389 stores in 100 counties, from an inventory of 8,117 products from 375 vendors. 

I analyzed overall sales, vendor performance, sales by location, and product performance to provide insights and recommendations to cross-functional departments (marketing, sales, inventory management).

## Summary of Insights
### Overall Sales Analysis
**Year over Year:** Sales have grown year over year, with the biggest jump (13.59%) during the pandemic. Sales growth leveled out from 2021 to 2022 (which saw a growth of only 0.15%), but they held level at approximately $430m a year, rather than dropping.    

![image](https://github.com/user-attachments/assets/759f672b-01f1-4388-a85b-49f76265f649)

**Seasonality:** There are always spikes in October and December, followed by a large drop in January.   

![image](https://github.com/user-attachments/assets/6c59db55-adae-47ee-938a-c3e53398e077)   

![image](https://github.com/user-attachments/assets/b9f47ea7-8bb0-47ea-b118-b51a445d942d)

**Vendor Analysis:** Diageo Americas is our top vendor, with total sales of $394 million. On the other end of the scale, our lowest-selling vendor is Puente International, with total sales of less than $100. Of our bottom 10 vendors, none of them sold more than $200 worth of merchandise.       

![image](https://github.com/user-attachments/assets/ac51dfde-da02-4393-be4c-116b7699daf8)   

![image](https://github.com/user-attachments/assets/68ebab3e-2f41-425d-b4d7-cc6e471b54fc)

**Geospatial Analysis:** Sales are highest in the highest-population county (Polk, with total sales of $450 million), and the top 10 counties population-wise are the top 10 counties for total sales. However, Pottawattamie County is 10th in population and 6th in total sales, and Dallas County is 7th in population and 10th in total sales.

![image](https://github.com/user-attachments/assets/cb3a1a09-3b44-4a9f-b46f-98e7385ce06d)

### K-Means Clustering
We used k-means clustering to identify eight distinct groups within the sales data (Cluster 0 through Cluster 7), allowing us to understand different customer segments. 

![image](https://github.com/user-attachments/assets/fd73bd0f-0f79-4f6a-a3b4-bc73a530fc0b)

Clusters 0 and 3 are large-population clusters with sub-average sales.   
Clusters 2 and 4 small-population clusters with very high sales, likely in affluent areas
Cluster 5 is a high population cluster with average sales. 
Cluster 6 is a very small cluster with specific sales characteristics. 
Cluster 7 is a smaller-population cluster with above-average sales, a small but high value area similiar to Cluster 2. 

### Sales Forecasting
The sales forecast shows a continuing upward trend, and examining our annual sales peaks, predicts October sales of $44 million, and December sales of $45.4 million.   

![image](https://github.com/user-attachments/assets/ab604652-6b4d-420c-ab79-fe682e66b209)

## Recommendations
### Sales Forecasting
The forecasting is showing sales continuing to rise; when 2023 is over, it's essential to check the modeling with the actual data to see if the model is correct or needs to be adjusted. 

### Inventory Management
Recommend a more in-depth analysis of the lowest performing products (for example, if they are a large part of a county's sales, even if that county's sales are small in the overall picture) should be performed to see if they should be kept on hand or removed from the options available. 

### Marketing  
*Cost-effective promotions and discount strategies* for Clusters 0 and 3   
*Premium products and targeted marketing* for Clusters 2 and 4   
*Focusing on driving higher sales* with Cluster 5, as it is high population but only average sales and thus shows the most room for growth   

## APPENDIX - Technical Information (Setup & Data)
### Prep
After filtering the data to the years I needed (2018-2022), I investigated the dataset and discovered a number of null values for store location (latitude, longitude), county number (the FIPS number), categories, and addresses. I extracted the addresses into one CSV and the categories into another CSV, and found the missing data within the main dataset (rows with missing addresses had the store name, and rows with the missing category had the item number and description, allowing me to reverse-engineer the missing data from the dataset). Once that was done, I pulled the latitude and longitude for each store from Geocodio, and obtained the county FIPS information (and population) from the US Census Bureau Iowa data. With that added, my dataset was complete for all further analysis. 

### Codes & Resources Used
<ul><b>Editor Used:</b> Jupyter Notebook</ul>
<ul><b>Python Version:</b> 2.7 </ul>

### Python Packages Used
<ul><b>General Purpose:</b> os</ul>
<ul><b>Data Manipulation:</b> pandas, numpy</ul>
<ul><b>Data Visualization:</b> matplotlib, seaborn, folium, json</ul>
<ul><b>Machine Learning:</b> scipy</ul>

### Source Data
[Liquor Sales Data](https://data.iowa.gov/Sales-Distribution/Iowa-Liquor-Sales/m3tr-qhgy), accessed from the Iowa Open Data Platform on 11/18/2023   
[Iowa County Population Data](https://www.census.gov/data/datasets/time-series/demo/popest/2020s-counties-total.html), accessed from the US Census Bureau on 11/24/2023   
[Geospatial Data](https://geodata.iowa.gov/datasets/8a1c2d500d8847d79aa47d45d44eb133_0/explore), accessed from Iowa Geospatial Data on 11/25/2023

### Procedures Conducted Outside Python   
Verified no duplicate extracted addresses (Excel)   
Added state column prepping for latitude/longitude importing (Excel)   
Cleaned unnecessary information from address column, notated row and what was (temporarily) removed (Excel)   
Uploaded spreadsheet to Geocodio to get latitude/longitude data (Geocodio)   
Saved original Geocodio csv with all data (including accuracy and source)   
Removed unnecessary columns that don't need to be appended into dataset (Excel)   
Saved revised csv as iowa_data_lats_longs 

### Code Structure
Filtering Dataset to the Scope of the Project   
Cleaning & Wrangling Filtered Data   
Descriptive Statistics   
Adding Population Data & Exploring Relationships   
Updating Location Information   
Geospatial Exploratory Analysis    
Regression Analysis    
Clustering & Analysis   
Time Series Analysis (Daily)   
Time Series Analysis (Monthly)   
Time Series Forecasting (Simple, Holt's Linear, Holt-Winter Exponential)

# Acknowledgments/References
Header photo by [CHUTTERSNAP](https://unsplash.com/@chuttersnap?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash) on [Unsplash](https://unsplash.com/photos/close-up-photo-of-liquor-bottles-in-rack-9UD0JHnWyVE?utm_content=creditCopyText&utm_medium=referral&utm_source=unsplash)
