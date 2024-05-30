# iowa_liquor
Multi-faceted analysis of Iowa liquor sales, 2018-2022 (Python)

### Project Brief
Looking at sales geographically and over time, searching for seasonal trends, economic recovery post-pandemic, and what products are performing the best/worst.   

I chose this dataset because I have prior experience in store management and an interest in the sales/marketing sphere of data analytics. This data let me investigate sales prior to, during, and after the pandemic, looking at if sales have recovered as well as what seems to be the most popular in different areas of Iowa, as well as if there are places in the state where sales seem to be higher than their population might suggest. It also let me utilize a number of different techniques and skills within Python and Tableau.  

### Key Questions & Objectives
#### Sales Volume   
Which stores have the highest/lowest sales?    
Which counties have the highest/lowest sales?    
Which product have the highest/lowest sales?    
#### Pandemic Recovery   
Have sales recovered to pre-pandemic levels? If not, when is that estimated to happen?    
#### Seasonality & Trends   
When are the largest purchases made?    
Are there seasonal trends to liquor purchases in the state?    
#### Sales & Population   
Are there any locations that have purchases beyond what their population would suggest?    

### Datasets
[Liquor Sales Data](https://data.iowa.gov/Sales-Distribution/Iowa-Liquor-Sales/m3tr-qhgy), accessed from the Iowa Open Data Platform on 11/18/2023   
[Iowa County Population Data](https://www.census.gov/data/datasets/time-series/demo/popest/2020s-counties-total.html), accessed from the US Census Bureau on 11/24/2023   
[Geospatial Data](https://geodata.iowa.gov/datasets/8a1c2d500d8847d79aa47d45d44eb133_0/explore), accessed from Iowa Geospatial Data on 11/25/2023

### Scripts
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
Time Series Forecasting   

### Procedures Conducted Outside Python   
Verified no duplicate extracted addresses (Excel)   
Added state column prepping for latitude/longitude importing (Excel)   
Cleaned unnecessary information from address column, notated row and what was (temporarily) removed (Excel)   
Uploaded spreadsheet to Geocodio to get latitude/longitude data (Geocodio)   
Saved original Geocodio csv with all data (including accuracy and source)   
Removed unnecessary columns that don't need to be appended into dataset (Excel)   
Saved revised csv as iowa_data_lats_longs   

### Final Presentation
[Tableau Story](https://public.tableau.com/app/profile/therightwright/viz/IowaLiquorSalesAnalysis_17022462743500/IowaLiquorSalesAnalysis2018-2022)       
[Case Study](https://sway.office.com/yueqcrJi38Lr4JXE?ref=Link)
