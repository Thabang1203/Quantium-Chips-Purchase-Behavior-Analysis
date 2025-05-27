# QUANTIUM CHIPS PURCHASE BEHAVIOR ANALYSIS  
# Overview
You are part of Quantium’s retail analytics team and have been approached by your client, the Category Manager for Chips, who wants to better understand the types of customers who purchase Chips and their purchasing behaviour within the region.

The insights from your analysis will feed into the supermarket’s strategic plan for the chip category in the next half year.

You have received the following email from your manager, Zilinka.

'Hi, 

Welcome again to the team, we love having new graduates join us! 

I just wanted to send a quick follow up from our conversation earlier with a few pointers around the key areas of this task to make sure we set you up for success. 

Below I have outlined your main tasks along with what we should be looking for in the data for each. 

Examine transaction data – look for inconsistencies, missing data across the data set, outliers, correctly identified category items, numeric data across all tables. If you determine any anomalies make the necessary changes in the dataset and save it. Having clean data will help when it comes to your analysis. 

Examine customer data – check for similar issues in the customer data, look for nulls and when you are happy merge the transaction and customer data together so it’s ready for the analysis ensuring you save your files along the way.

Data analysis and customer segments – in your analysis make sure you define the metrics – look at total sales, drivers of sales, where the highest sales are coming from etc. Explore the data, create charts and graphs as well as noting any interesting trends and/or insights you find. These will all form part of our report to Julia. 

Deep dive into customer segments – define your recommendation from your insights, determine which segments we should be targeting, if packet sizes are relative and form an overall conclusion based on your analysis. 

Make sure you save your analysis in the CSV files and your visualisations – we will need them for our report. If you could work on this analysis and send me your initial findings by end of next week that would be great.  

Looking forward to reviewing your work. 

Thanks, 

Zilinka'
# Data Source
I got this dataset from Forage
[download here](https://www.theforage.com/virtual-experience/NkaC7knWtjSbi6aYv/quantium/data-analytics-rqkb/data-preparation-and-customer-analytics)
# Objectives

1. LOAD NECESSARY LIBRARIES  
Imported pandas, numpy, seaborn, matplotlib, re, datetime, and scipy.stats for data manipulation and analysis.

2. LOAD DATA  
Loaded transaction data from "QVI_transaction_data.xlsx" and customer behavior data from "QVI_purchase_behaviour.csv".

3. INITIAL DATA EXPLORATION  
- Previewed first 5 rows of transaction data (264,836 entries) containing columns: DATE, STORE_NBR, LYLTY_CARD_NBR, TXN_ID, PROD_NBR, PROD_NAME, PROD_QTY, TOT_SALES.  
- Previewed customer data with columns: LYLTY_CARD_NBR, LIFESTAGE, PREMIUM_CUSTOMER.

4. CLEAN TRANSACTION DATE COLUMN  
Converted numeric date values to datetime format using pandas (base date: 1899-12-30).

5. REMOVE NON-CHIP PRODUCTS  
Filtered out products containing "salsa" in PROD_NAME to focus on chip purchases.

6. CHECK DATASET FOR OUTLIERS  
- Identified and removed transactions with PROD_QTY ≥ 200 (bulk purchases by a single customer).  
- Removed all records associated with this outlier customer.

7. CHECK FOR MISSING DATES  
Analyzed transaction patterns over time (July 2018 - June 2019) and verified no significant gaps in daily transactions.

8. EXTRACT PACK_SIZE AND BRAND  
- Created PACK_SIZE column by extracting numeric values from PROD_NAME.  
- Created BRAND column using the first word of PROD_NAME, with normalization (e.g., "RED" → "RRD").

9. MERGE WITH CUSTOMER DATA  
Combined transaction and customer datasets using LYLTY_CARD_NBR as the key.

10. ANALYSIS — TOTAL SALES BY SEGMENT  
Performed segmentation analysis focusing on:  
- Customer lifestyle stages (e.g., YOUNG SINGLES/COUPLES, OLDER FAMILIES)  
- Premium customer categories (Premium, Mainstream, Budget)  
- Visualized sales distribution across customer segments  

KEY TECHNICAL STEPS  
- Handled datetime conversion and outlier removal  
- Implemented text parsing for product features  
- Merged transactional and demographic data  
- Performed time-series and segment-based analysis  

FILES
- Transaction data: QVI_transaction_data.xlsx  
- Customer data: QVI_purchase_behaviour.csv  

LIBRARY DEPENDENCIES  
- pandas, numpy, seaborn, matplotlib, re, datetime, scipy.stats
