# Online Retail Customer Segmentation

### Overview

This project demonstrates customer segmentation using the **Online Retail II** dataset, which includes transaction histories and customer demographics. The analysis uses **Recency, Frequency, and Monetary (RFM)** metrics to identify distinct customer segments, which can be used to optimize marketing strategies, improve customer targeting, and drive business decisions.

### Objective

The goal of this analysis is to identify distinct customer segments based on their purchasing behavior using unsupervised learning methods, specifically clustering techniques like K-Means. We aim to:

- Understand the different customer segments.
- Identify high-value customers and frequent shoppers.
- Group customers based on their Recency, Frequency, and Monetary (RFM) behavior.

### Dataset

The dataset contains transaction records from a UK-based non-store online retailer, with the following key features:

- Invoice: Unique identifier for each transaction.
- StockCode: Product code for each item purchased.
- Description: Name of the product.
- Quantity: Quantity of each product purchased.
- InvoiceDate: Date and time of the transaction.
- Price: Unit price of each product.
- CustomerID: Unique identifier for each customer.
- Country: The country of the customer (mostly from the United Kingdom).

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
   - The characteristics of each cluster are analyzed by reviewing the mean, median, and standard deviation of RFM features.
   - Cluster centers are visualized to understand customer behavior patterns in each group.

### Results

The clustering model identified four key customer segments:
- **Cluster 1**: High-frequency, mid-range spenders.
- **Cluster 2**: Low-frequency, high-value spenders.
- **Cluster 3**: High-frequency, high-value spenders.
- **Cluster 4**: Low-frequency, low-value spenders.

#### Cluster Counts:
- Cluster 1: 3201 customers
- Cluster 2: 1049 customers
- Cluster 3: 59 customers
- Cluster 4: 5 customers

### Use Cases
- **Customer Engagement**: Tailor marketing campaigns to specific segments (e.g., loyalty programs for high spenders, re-engagement strategies for low-frequency customers).
- **Revenue Optimization**: Focus on retaining high-value customers.
- **Improved Targeting**: Personalize product recommendations based on customer behaviors.

### Sources

https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset
