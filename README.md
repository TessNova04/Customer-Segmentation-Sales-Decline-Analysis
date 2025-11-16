# Customer-Segmentation-Sales-Decline-Analysis

## 📁 Project Overview

A small unisex fashion business experienced a steady decline in sales over the past 4 months.
The business owner wants to understand:

-Why sales are dropping

-Whether customers are returning or not

-Which products are not performing well

-What type of customers should be targeted

-Whether ads are bringing the wrong audience

-Which products to promote

-What marketing channel improvements are needed

This project explores the dataset, cleans it, engineers new features, analyzes trends, and provides clear insights & data driven recommendations.


## 🎯 Business Questions

The business owner asked for insights on:

-Reason for sales decline over the past 4 months

-Why customers are not returning

-Whether ads are attracting the wrong audience

-Which products are no longer selling well

-Which products to promote

-Which customer segment to focus marketing on

-Whether to restock or discontinue certain items

-How to improve online engagement (email + website)

All insights must support business decision making.


## 📄 Dataset Used

### File: Messy_Customer_Segmentation_2000rows.csv
-Rows: 2,000
-Columns: 13 (before cleaning), 14+ (after feature engineering)

### Original Columns
Column

ID - Customer ID (inconsistent formatting)

Name - Customer full name (mixed case)

Gender	- Male/Female/Unknown

Location	- Customer city (mixed case, empty cells)

Date_Joined	- Signup date

Last_Purchase_Date	- Most recent purchase date

Days_Since_Last_Purchase	- Inconsistent values

Num_Purchases	- Purchase count

Website_Visits	- Website visit count

Email_Open_Rate	- % emails opened


## 🧼 Data Cleaning Process (Excel)
### ✔ 1. Removed blank rows & duplicates

-Removed fully empty rows

-Removed duplicate customer entries based on ID & Name

### ✔ 2. Standardized ID column

-Ensured uniform format (e.g., CUST001 → CUST0001)

-Converted column to Text type

### ✔ 3. Standardized Name column

-Used =PROPER(Name) to fix casing

-Removed trailing/leading spaces with =TRIM(Name)

### ✔ 4. Cleaned Gender column

-Standardized entries as Male / Female / Unknown

-Replaced blanks with “Unknown”

### ✔ 5. Cleaned Location column

-Converted to PROPER() format

-Filled missing values with “Unspecified”

-Ensured consistent spelling (e.g., “Lagos”, not “lagos”)

### ✔ 6. Fixed Date Formats

-Converted DateJoined and LastPurchaseDate to Excel date type.

### ✔ 7. Corrected Days Since Last Purchase

-Recalculated using:

=TODAY() - LastPurchaseDate

### ✔ 8. Standardized Total Spend

-Converted all values to USD

-Fixed currency inconsistencies (₦ → $)

-Removed commas & text formatting

###  ✔ 9. Handled Missing Values
#### Action
-NumPurchases	- Replaced blanks with 0

-WebsiteVisits	- Replaced blanks with 0

-EmailOpenRate	- Replaced blanks with 0

-LoyaltyPoints	- Replaced blanks with 0

### ✔ 10. Checked for Outliers Using Pivot Tables

-Extremely high spend values evaluated

-Verified legitimate vs erroneous entries

-Total_Spend	- Customer lifetime spend (mixed currency)

-Loyalty_Points	- Reward system points

-Product_Category	- Category purchased



## 📊 Analysis Using Pivot Tables
### ✔ 1. Sales Decline (Last 4 Months)

-Columns Used: Date, TotalSpend, NumPurchases
Pivot Setup:

-Rows → Date (Grouped by Month & Year)

-Values → Sum of TotalSpend, Count of Customers

#### Findings:

-Sales declined steadily for 4 months

-Customer count reduced

-Buying frequency dropped

### ✔ 2. Customer Retention Problem

-Columns: DaysSinceLastPurchase, NumPurchases, CustomerSegment

#### Findings:

-More customers moved into At-Risk category

-Frequent customers reduced sharply

-High-value customers purchased less often

### ✔ 3. Ads Attracting Wrong Customers

-Columns: AdSource, CustomerSegment, WebsiteVisits, TotalSpend

#### Findings:

-Instagram ads brought low-value customers

-TikTok brought high website visits but poor conversion

-Facebook attracted highest-spend loyal customers

### ✔ 4. Products No Longer Selling

-Columns: ProductCategory, Date, TotalSpend

#### Findings:

-Caps & Dresses dropped significantly

-Shirts & Sneakers remained stable

-Accessories revived slightly due to promotions

### ✔ 5. Which Products to Promote

-Columns: ProductCategory, CustomerSegment, TotalSpend

#### Findings:

-High-value customers prefer: Sneakers, Shirts

-At-risk customers previously bought: Dresses

### ✔ 6. Which Customer Segment to Focus Marketing On

-Columns: CustomerSegment, WebsiteVisits, EmailOpenRate

#### Findings:

-High-value customers rarely open emails (low engagement)

-At-risk customers need win-back campaigns


## 📌 Insights Summary
### 1. Sales are dropping because:

-Customer retention is falling

-Key products are losing demand

-Ads are bringing unqualified customers

-Email engagement is low

-Repeat purchase frequency dropped

### 2. Customer Behavior Insights

-Only 12–15% of customers are High Value

-At-risk customers increased by +27%

-Website visits are not converting into purchases

### 3. Product Insights

-Sneakers and Shirts should be promoted

-Dresses and Caps may need to be discontinued or discounted

### 4. Marketing Insights

-Facebook brings best ROI

-Instagram brings the worst conversion

-Email open rate is too low (<10%) 


## Recommendations
### 1. Increase retention

-Launch win back discounts

-Personalize emails based on product interest

-Reward frequent customers with loyalty bonuses

### 2. Optimize Ads

-Reduce Instagram budget

-Shift budget toward Facebook

-Create TikTok videos that target returning customers

### 3. Improve product strategy

-Restock Sneakers & Shirts

-Offer bundle discounts

-Discontinue underperforming categories (Caps, Dresses)

### 4. Improve Online Engagement

-Update website layout

-Add product recommendations

-Send segmented emails weekly

-A/B test email subject lines

## Tools Used

-Excel (Data Cleaning, Pivot Tables, Visualization)

-GitHub (Project Hosting)`
