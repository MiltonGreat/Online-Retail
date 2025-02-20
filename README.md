# Online Retail Customer Segmentation

### Overview

This project demonstrates customer segmentation using the **Online Retail II** dataset, which includes transaction histories and customer demographics. The analysis uses **Recency, Frequency, and Monetary (RFM)** metrics  to segment customers based on their purchasing behavior. By using clustering techniques like K-Means, we identify distinct customer groups that can be used to enhance marketing strategies, improve customer targeting, and drive business decisions.

### Objective

The goal of this analysis is to identify distinct customer segments based on their purchasing behavior using unsupervised learning methods, specifically clustering techniques like K-Means. We aim to:

- Understand the different customer segments.
- Identify high-value customers and frequent shoppers.
- Group customers based on their Recency, Frequency, and Monetary (RFM) behavior.

### Dataset

The dataset contains transaction records from a UK-based non-store online retailer, with the following key features:

- **Invoice**: Unique identifier for each transaction.
- **StockCode**: Product code for each item purchased.
- **Description**: Name of the product.
- **Quantity**: Quantity of each product purchased.
- **InvoiceDate**: Date and time of the transaction.
- **Price**: Unit price of each product.
- **CustomerID**: Unique identifier for each customer.
- **Country**: The country of the customer (mostly from the United Kingdom).

The dataset contains over 400,000 transaction entries.

### Key Steps

1. **Data Loading and Cleaning**: 
   - The dataset is loaded and missing values are handled.
   - Cancellations and irrelevant data (e.g., rows with missing `Customer ID`) are removed.
   - **Description** column missing values are imputed.

2. **Feature Engineering**:
   - **Recency**: Number of days since the last purchase.
   - **Frequency**: Total number of transactions per customer.
   - **Monetary**: Total spend per customer.

3. **Scaling Data**: 
   - The RFM metrics are scaled to standardize values for clustering.

4. **Clustering (K-Means)**:
   - The optimal number of clusters is determined using the **Elbow Method**.
   - K-Means clustering is applied to segment customers into groups based on their RFM scores.

5. **Dimensionality Reduction**:
   - **PCA (Principal Component Analysis)** is used to visualize customer clusters in 2D space.

6. **Cluster Analysis**:
   - The characteristics of each cluster are analyzed by reviewing the mean, median, and standard deviation of RFM metrics. The cluster centers are visualized to understand the behavioral patterns of each group.

### Results

The clustering analysis identified four distinct customer segments with the following key characteristics:

- **Cluster 0 (High-frequency, High-value Spend)**: This group contains loyal, high-value customers who frequently make purchases. They contribute significantly to revenue.
- **Cluster 1 (Occasional Low-Spenders)**: This segment represents a large proportion of customers who make infrequent purchases and have low spending.
- **Cluster 2 (Recent, Big Spenders)**: This group consists of high-value customers with very recent purchase activity. Although small, they contribute significantly to revenue.
- **Cluster 3 (Infrequent, Low-Spending Customers)**: This segment includes customers who rarely purchase and spend very little, representing potential churn or one-time buyers.

#### Cluster Distribution:

- **Cluster 0**: 59 customers (High-frequency, high-value spenders)
- **Cluster 1**: 3201 customers (Moderate-frequency, low spenders)
- **Cluster 2**: 1049 customers (Recent, big spenders)
- **Cluster 3**: 5 customers (Infrequent, low spenders)

#### Retention Rates:

- **Cluster 0** shows a very low retention rate, suggesting high churn and the need for targeted retention strategies.
- **Cluster 3** has the highest retention rate, indicating that although customers in this group are infrequent, they tend to remain loyal once engaged.
- **Cluster 1** and **Cluster 2** display varying levels of retention, highlighting opportunities for improvement in customer re-engagement.

#### Monetary Insights:

- **Cluster 2** has the highest average spending, averaging £215,543.67 per customer, indicating that this small group plays a major role in the business’s revenue.
- **Cluster 1** and **Cluster 3** represent low spenders, with **Cluster 1** showing moderate spending and **Cluster 3** showing very low monetary value.

#### Recency and Frequency Insights:

- **Cluster 0** has recent purchase behavior but also exhibits high variance, indicating a mix of frequent but inconsistent customers.
- **Cluster 1** shows the highest recency, meaning most customers in this group made their last purchase a long time ago.
- **Cluster 3** has the highest recency, indicating that customers in this group have not purchased in a long time.

### Actionable Insights:

- **Loyalty Programs**: Focus on Cluster 0, which represents high-value and frequent customers, to ensure they remain engaged and loyal.
- **Targeted Promotions**: For Cluster 1, create promotional strategies to increase purchase frequency and customer engagement.
- **Exclusive Offers**: Target Cluster 2 with premium or high-ticket items, as they represent a high-value segment with the potential for significant contribution to revenue.
- **Re-engagement Campaigns**: For Cluster 3, consider re-engagement campaigns to win back infrequent customers, possibly with discounts or special offers to encourage purchases.

### Sources

Dataset: [Online Retail II Dataset on Kaggle](https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset)
