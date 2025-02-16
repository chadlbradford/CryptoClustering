Crypto Clustering - README

Overview

This project applies Principal Component Analysis (PCA) and K-Means Clustering to group cryptocurrencies based on their historical price changes. The goal is to identify patterns in cryptocurrency movements and understand which coins behave similarly over time.

Dataset

The dataset consists of historical percentage changes in cryptocurrency prices over various timeframes:

price_change_percentage_24h

price_change_percentage_7d

price_change_percentage_14d

price_change_percentage_30d

price_change_percentage_60d

price_change_percentage_200d

price_change_percentage_1y

Preprocessing

Data is scaled using StandardScaler to ensure uniformity across features.

PCA (Principal Component Analysis) is applied to reduce the data dimensions while preserving the majority of variance.

The explained variance of the top three principal components is calculated to assess how much information is retained.

Clustering Approach

1. Elbow Method for Optimal k Selection

The Elbow Method is used to determine the optimal number of clusters.

K-Means clustering is applied using the optimal k-value identified.

2. K-Means Clustering

The model is initialized with n_clusters=k, where k is determined from the Elbow Curve.

The model is trained on the PCA-transformed data.

Each cryptocurrency is assigned to a cluster based on the PCA-transformed features.

Results & Visualization

1. Feature Influence on Principal Components

The PCA component weights show the strongest positive and negative influences of each feature on PC1, PC2, and PC3.

Example influences:

PC1: Highest positive: price_change_percentage_200d, Highest negative: price_change_percentage_24h

PC2: Highest positive: price_change_percentage_14d, Highest negative: price_change_percentage_1y

PC3: Highest positive: price_change_percentage_7d, Highest negative: price_change_percentage_60d

2. Scatter Plot of PCA Components

Cryptocurrencies are visualized on a scatter plot of PCA1 vs. PCA2.

Data points are color-coded by their assigned cluster, revealing distinct groups of cryptocurrencies.

How to Run the Code

Ensure all dependencies are installed:

pip install pandas scikit-learn matplotlib

Run the Python script or Jupyter Notebook containing the clustering workflow.

Review the output:

Cluster assignments for each cryptocurrency

PCA weight contributions

Visualizations of the clustered data

Conclusion

This project demonstrates how PCA and K-Means clustering can be used to categorize cryptocurrencies based on price movements. The clustering results help identify groups of cryptocurrencies that behave similarly, providing insights for investors and analysts.

Future Improvements:

Experiment with different numbers of PCA components.

Compare K-Means with other clustering techniques (e.g., Hierarchical Clustering, DBSCAN).

Incorporate additional features, such as market capitalization and trading volume.

Reference

Original self-sourced code vetted and debugged with ChatGPT.

