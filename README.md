# Project Background
PrintPlus Studios, established in 2019, is a growing e-commerce company specialising in personalised print products such as business cards, canvas prints, posters, flyers, photo books, and greeting cards. Operating entirely online, the company serves customers through its website, offering fully customisable design options.

The business generates substantial amounts of data from its daily transactions, customer interactions, and product sales. However, much of this information has been historically underutilised. This project leverages Excel-based analysis to transform raw order data into meaningful insights using an RFM (Recency, Frequency, Monetary) framework. By doing so, it uncovers key customer segments and produces actionable recommendations to guide customer retention strategies, optimise marketing efforts, and improve long-term commercial performance.

The goal is to answer three key business questions:

**1. Who are PrintPlus Studios’ best customers?**  

**2. Which customers should be targeted with a retention campaign?**  

**3. Which customers can PrintPlus Studios safely exclude from paid campaigns?**

The analysis categorises customers using an RFM framework, where customers who purchased most recently, most frequently, and generated the highest monetary value are classified as the best customers, and those who purchased long ago, only once, or spent very little are classified as the lowest-value customers.

All the Excel formulas used for the analysis can be found [here](https://docs.google.com/document/d/11wYtmhPXSS-ClJ5QhHnWWfoReHPZVQd5/edit?usp=sharing&ouid=102165638531054537510&rtpof=true&sd=true).

# Data Overview & Initial Checks
PrintPlus Studios transaction-level dataset contains one year of customer order history with a total row count of 1000 records.

The dataset includes the following fields:

- **OrderID:** Identifies each individual transaction uniquely.

- **CustomerID:** Indicates which customer placed the order.

- **OrderDate:** Indicates the date the purchase was made.

- **ProductType:** Indicates the type of product purchased.

- **OrderValue:** Specifies the total monetary amount of the order, measured in United States Dollar ($).

The image below displays a snippet of the dataset.
<p align="center"><img width="576" height="559" alt="Screenshot 2025-11-19 at 2 57 46 PM" src="https://github.com/user-attachments/assets/383e3b71-30d0-4eb4-b6a6-79ed92c248e1" /></p>

Prior to beginning the analysis, a variety of checks were conducted for quality control and familiarization with the dataset. These included identifying duplicate OrderID values, checking for blanks in critical fields (OrderDate, OrderValue, CustomerID), and verifying the earliest and latest transaction dates to confirm the accuracy of the analysis window.

# Executive Summary
### Overview of Findings

The RFM analysis grouped customers into five categories: Best Customers, Loyal Customers, Potential Loyal Customers, Need Attention, and At Risk.

The analysis revealed a strong top tier of 61 Best Customers, who purchase frequently, have spent the most, and remain highly engaged with the business. This group represents the company’s most valuable customers and contributes the largest share of total revenue. A substantial 57 customers fell into the Need Attention segment, showing noticeable declines in recency, frequency, and spending. A very small group of 13 customers were classified as At Risk, characterised by long periods of inactivity, extremely low purchase frequency, and minimal spend.

Together, these segments highlight where PrintPlus Studios should invest in loyalty-building, where retention efforts should be directed, and where marketing spend can be reduced to improve efficiency and profitability.

### Best Customers:

- There are 61 best customers having an RFM score ≥ 13 out of 15, meaning their combined recency, frequency, and monetary value places them among the highest-value customers.

<p align="center"><img width="770" height="897" alt="Screenshot 2025-11-18 at 3 36 23 PM" src="https://github.com/user-attachments/assets/b956d2f7-3de8-4617-a677-10e6e388237d" /></p>

- On average, they last purchased around 48 days ago, indicating very recent engagement compared with the wider customer base.

- 46% (28 customers) in this segment made purchases more recently than 80% of the entire customer base. 38% (23 customers) purchased more recently than 60% of customers, and 16% (10 customers) purchased more recently than 40% of customers. The best customer segment is composed largely of highly recent purchasers.

- Best customers typically make around 6 purchases per year, demonstrating strong repeat-buying behaviour and strong loyalty.

- 89% (54 customers) in this segment made purchases more frequently than 80% of the customer base, while the remaining 11% (7 customers) purchased more frequently than 60% of customers. The entire best customer segment consistently falls within the highest-frequency tiers.

- They spend an average of $110.88, placing them among the highest contributors to total revenue. They collectively contribute ≈39% of total revenue.

- 74% (45 customers) in this segment spend more than 80% of all customers, 25% (15 customers) spend more than 60% of customers, and 5% (1 customer) spend more than 40% of customers. The best customer segment is largely composed of high-value spenders who generate a significant share of overall revenue.

### Need Attention:

- There are 57 need attention customers with an RFM score between 4 and 6 out of 15, indicating that their combined recency, frequency, and monetary performance places them in a low-engagement tier.

<p align="center"><img width="713" height="822" alt="Screenshot 2025-11-18 at 3 44 33 PM" src="https://github.com/user-attachments/assets/1382b4dd-6835-4fda-a65c-de20b37db224" /></p>

- On average, they last purchased 170 days ago, showing that this group has not interacted with the business for a significant period and is trending toward disengagement.

- 5% (3 customers) in this segment purchased more recently than 60% of the customer base, 16% (9 customers) purchased more recently than 40% of customers, 37% (21 customers) purchased more recently than 20% of customers, and 43% (24 customers) purchased less recently than 80% of customers, placing them in the bottom 20% for recency. The need attention segment is characterised by a substantial share of customers whose last purchase occurred a significant time ago, indicating declining engagement and an elevated risk of churn.

- They typically make around 2 purchases per year, indicating weak repeat-buying behaviour and inconsistent engagement.

- 4% (2 customers) purchase more frequently than 40% of the customer base, 70% (40 customers) purchase more frequently than 20% of customers, and 26% (15 customers)  purchase less frequently than 80% of customers, placing them in the bottom 20% for purchase frequency. The need attention segment is dominated by customers with low purchase frequency, indicating limited repeat-buying behaviour and weaker purchasing consistency.

- They spend an average of $23.65 and collectively contribute ≈8% of total revenue, highlighting their limited financial impact on the business.

- 7% (4 customers) in this segment spend more than 40% of the customer base, 32% (18 customers) spend more than 20% of customers, and 61% (35 customers) spend less than 80% of customers, placing them in the bottom 20% for total spending. The need attention segment is predominantly composed of low-spending customers with limited revenue contribution.

### At Risk:

- There are 13 at risk customers with an RFM score of 3 out of 15, indicating that their combined recency, frequency, and monetary performance places them in the lowest engagement tier, characterised by very infrequent purchases, long periods of inactivity, and minimal spending.

<p align="center"><img width="1052" height="333" alt="Screenshot 2025-11-18 at 3 48 48 PM" src="https://github.com/user-attachments/assets/7f9d04c3-5aa7-45d6-92d0-63affa9fb36c" /></p>

- On average, they last purchased 284 days ago, showing prolonged inactivity.

- 100% (13 customers) in this segment purchased less recently than 80% of the customer base, placing all of them in the bottom 20% for recency. The at risk segment has been inactive for a long period and shows a high likelihood of disengagement.

- At risk customers make an average of 1 purchase per year, indicating extremely limited engagement and minimal repeat-buying behaviour.

- 100% (13 customers) in this segment purchase less frequently than 80% of the customer base, placing them in the bottom 20% for purchase frequency. The at risk segment reflects consistently low repeat-buying behaviour, signalling weak loyalty and limited interaction with the business.

- They spend an average of $10.67 and collectively contribute only ≈0.8% of total revenue, underscoring their very low overall financial impact on the business.

- 100% (13 customers) in this segment spend less than 80% of the customer base, placing them in the bottom 20% for total spending. The at risk segment contributes the lowest revenue levels in the dataset.

# Recommendations

Based on the uncovered insights, the following recommendations have been provided:

- Invest in a VIP loyalty programme exclusively for best customers, offering exclusive benefits such as priority printing and premium templates. This segment generates ≈39% of revenue, so investing in them is highly profitable due to their strong repeat-purchase behaviour.

- Deploy a targeted re-engagement campaign with a limited-time incentive, such as 10% off or free shipping, aimed solely at need attention customers who previously purchased ≈2 times/year and could be reactivated at relatively low cost.

- Exclude at risk customers from all paid marketing campaigns, as they contribute <1% of revenue and show almost no likelihood of reactivation. Excluding them from campaigns prevents marketing waste and ensures budget is focused on profitable segments.
