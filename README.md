# RFM-Analysis
Utilize the RFM model created with Python to segment customers and propose appropriate marketing campaigns.
Link: https://colab.research.google.com/drive/1p9g7QV61Xasod2L_pjFsMdJgX7AcJiPv


## I. Introduction
### 1. Business question
SuperStore is a global retail company with a vast number of customers. For the upcoming Christmas and New Year season, the Marketing department wants to run marketing campaigns to show appreciation to loyal customers who have supported the company over time, as well as target potential customers who could become loyal clients.

However, the Marketing department has not yet segmented the customers for this year due to the large dataset, which cannot be manually processed as in previous years. Therefore, they have requested support from the Data Analytics department to implement a customer segmentation solution to tailor specific marketing programs for each customer group.

The Marketing Director has proposed using the RFM model as a solution. In the past, when the company was smaller, the team could calculate and classify segments using Excel. However, given the current large volume of data, they are seeking assistance from the Data department to develop a workflow for segmentation analysis through Python programming.

### 2. Proposed Approach
- Prepare a dataset suitable for the RFM model.
- Define the calculation method and compute the R, F, M scores for each customer. (Note: The recency score (R) should be calculated as of December 31, 2011)
- Determine the scoring method, assigning scores from 1 to 5, using the statistical quintile method.
- Based on the classification table, group customers into segments.
- Visualize the number of segments across different dimensions, analyze the company's current situation and provide insights for the Marketing team.
- Provide recommendations to the Marketing and Sales teams on which of the three RFM metrics should be prioritized for SuperStore’s retail model.

### 3. Dataset
Dataset includes 3 different related tables including: retail transactions, returned orders and RFM segmentation of customers purchasing products in 2011 and RFM classification

- **Transaction information dataframe**: cancelled and returned orders must be filtered out before conducting the analysis. Those are orders with "C" at the beginning of InvoiceNo

    ![retail](https://github.com/user-attachments/assets/df2ed1c4-1ce6-48af-9903-06bc896c6e44)

- **Segmentation dataframe**:

  ![segmentation](https://github.com/user-attachments/assets/d9fe716e-8f5f-4322-a540-740924abc4be)

- **Segmentation dataframe**: This is the table after merging information from the Segmentation dataframe with the Transactions dataframe, grouped by CustomerID.

   ![retail_segementation](https://github.com/user-attachments/assets/925d76f7-e7ac-4a75-b104-72f90fb69df5)

### 3. RFM model
- RFM is a method used for analyzing customer value. It is commonly used in database marketing and direct marketing and has received particular attention in retail and professional services industries
- RFM stands for the three dimensions:
    1. Recency – How recently did the customer purchase?
    2. Frequency – How often do they purchase?
    3. Monetary Value – How much do they spend?
- RFM analysis numerically ranks a customer in each of these three categories, generally on a scale of 1 to 5 (the higher the number, the better the result). The “best” customer would receive a top score in every category.


## II. Data Visualization with Python

### 1. Business Report

**- Revenue by Month** 
  
   ![revenuebymonth](https://github.com/user-attachments/assets/919dd972-4b2b-4e3e-8ab3-70df0f666792)

- The peak months of the year are September, October, and November 2011. Note: The report's last date is 09.12.2011, so the data for December is not accurate.

**- Top 5 Best Sellers by Revenue**
  
 ![top5product](https://github.com/user-attachments/assets/d0524e4d-fc34-4ddf-93e0-0ccb229cf4db)

 ![top5product2](https://github.com/user-attachments/assets/26cbb4fd-1daa-4e00-b54c-fd1802e727d0)

- These are the top 5 bestselling products. However, from the pie chart, we can see that they do not contribute a significant portion of the total revenue. This suggests that SuperStore has a wide range of product lines, and we will not analyze further using the Product dimension.


**- Total Revenue by Geography**

  ![countryrevenue](https://github.com/user-attachments/assets/c4108cbc-f662-498c-9089-1300777db1ee)

  ![countryrevenue2](https://github.com/user-attachments/assets/95084718-a2af-4eca-bd2b-1ab8f83e7e44)


- The UK continues to dominate with a revenue share of 82.06%, contributing over 7 million USD.

### 2. Customer Segment Report 

**- Total Customer by Segment** 

![segmentcount](https://github.com/user-attachments/assets/07b2fc4f-db65-4775-8983-a09abbf5d835)

![segment](https://github.com/user-attachments/assets/a6ca19d1-b981-42b6-b7a0-c2f7b97d4a28)

Among the 4338 customers, nearly 20% are in “Champions” group. The Tier 1 customer group also holds a significant share. On the other hand, Hibernating Customers, ranking second in size, will be a key focus in the upcoming analyses.

**- Average RFM rate by Segment** 

![f_segment](https://github.com/user-attachments/assets/8d93e15c-1e1a-4766-a015-755f621c26eb)

![m_segment](https://github.com/user-attachments/assets/0efcea98-a9b0-4ed9-a0d6-be58ba8a0dc1)

![r_segment](https://github.com/user-attachments/assets/10861ef1-2708-4235-a9f8-e5c1ee610c2a)

The RFM analysis indicates that SuperStore has a stable base of “Champion" customers, contributing a dominant share of the total revenue. While the “Hibernating Customers” group represent a large portion of the overall customer base, they do not generate significant revenue. In contrast, the “Cannot Lose Them” group, though small in number, contributes a substantial amount of revenue and should be prioritized for attention.


### III. Insights

- The largest market remains the UK, along with neighboring countries and those within the EU.

- The peak months are September to November 2011, with the highest sales in November. Hypothesis: This surge could be due to the year-end shopping season and Black Friday.

- SuperStore has a stable base of  “Champion” customers, who contribute the majority of the revenue. These customers tend to make large purchases and have a high purchase frequency, making them key drivers of the company's sales.

- Even within Tier 1, the “Loyalist” and “Potential Loyalist” groups have not generated as much revenue as expected. In particular, the “Potential Loyalist ”group, which accounts for nearly 10% of the total customers, contributes only around 5% of the total revenue.

- Hibernating Customers, while ranking second in number, contribute very little to the total revenue.

- Conversely, there are few customers in the “Cannot Lose Them” group, but they generate a substantial portion of the revenue.

## IV. Recommendations
**- Retaining “Champions”**: SuperStore currently generates significant revenue from its loyal customers, especially the Champions. The key to the success of this group is their high purchase frequency, consistently buying in large quantities, with their Frequency (F) score standing out compared to other groups. It is crucial to focus on this customer segment to maintain their loyalty.

**- Focusing on “Loyalist” and “Potential Loyalist”**: The next marketing strategy should focus on the two remaining Tier 1 groups: Loyalist and Potential Loyalist. For these groups, the priority is to improve Frequency to elevate them to the next tier. Particularly for B2B customers, boosting Frequency should be a priority. Suggestions: Loyalty Programs, Personalized Solutions, and offering supplementary products or expanded service packages.

**- Promoting “Cannot Lose Them” Customers: Suggestions**: Win-back Programs, Win-back Emails. Offer a special discount or promotion personalized based on their past purchases. For customers who have not made a purchase in a while, send a personalized email or offer that highlights new products or services that may be of interest to them, along with a special discount or promotion tailored to their purchase history.


