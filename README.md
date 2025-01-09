# Online Retail Customer Segmentation

### Overview

This project focuses on analyzing customer purchasing patterns using the Online Retail II dataset, which contains transaction records from a UK-based online retailer. The goal is to perform unsupervised learning to identify different customer segments based on purchasing behaviors, using clustering techniques.

### Quality Issues:

- Missing values in transaction histories or demographics.
- Outliers in purchasing frequency or monetary spend.

Cleaning/Transformation:
- Impute missing values and scale monetary features.
- Use dimensionality reduction (e.g., PCA) to simplify features.

Model Evaluation:
- Evaluate clustering results qualitatively (e.g., cluster profiles) and quantitatively (e.g., silhouette score).

Dataset Limitations:
- Limited to a specific retailer or region, reducing generalizability.

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

### Steps in the Project

Data Preprocessing
- Loaded the dataset and checked for missing values and data types.
- Cleaned the data by handling missing customer IDs and cancellations (transactions starting with 'C').
- Created a new feature for TotalSpent (calculated as Quantity * Price).

Feature Engineering
- Derived three important features for customer segmentation:
- Recency: Days since the last purchase.
- Frequency: The number of transactions per customer.
- Monetary: The total amount spent per customer.

 Scaling the Data
 - Scaled the RFM features using StandardScaler to ensure that all features contribute equally to the clustering model.

 Clustering with K-Means
 - Used the Elbow Method to determine the optimal number of clusters for K-Means clustering.
 - Applied K-Means with the optimal number of clusters to categorize customers into different segments.

 Dimensionality Reduction and Visualization
- Used PCA (Principal Component Analysis) to reduce the dimensions of the RFM features to 2D for visualization purposes.
- Visualized the customer clusters on a 2D plot using seaborn and matplotlib.

Cluster Analysis
- Analyzed the cluster centers to interpret the characteristics of each segment.
- Provided insights into the average Recency, Frequency, and Monetary values for each cluster.
- Investigated the characteristics of each customer segment to identify the different types of customers.

### Cluster Analysis Insights

Based on the clustering results, the customer base was divided into 4 distinct clusters with the following characteristics:

- Cluster 0: Customers who have high recency and frequent high-value transactions.
- Cluster 1: Customers with relatively low recency and lower frequency, but higher spending.
- Cluster 2: Customers with very low recency and minimal transactions, but very high spending.
- Cluster 3: Customers with high recency and frequency but moderate spending.

The analysis shows the distribution of customers across the clusters, where Cluster 1 contains the highest number of customers, while Cluster 2 has the fewest.

### Source

https://www.kaggle.com/datasets/lakshmi25npathi/online-retail-dataset
