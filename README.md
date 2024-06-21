# CryptoClustering

![CryptoClusteringImage](https://www.europeanbusinessreview.com/wp-content/uploads/2021/03/bitcoinrising.png)
## Project Overview

This project utilizes Python and unsupervised learning techniques to analyze and cluster cryptocurrency data. By examining the effects of 24-hour and 7-day price changes, we aim to identify patterns and group cryptocurrencies into meaningful clusters. The primary steps include data preprocessing, dimensionality reduction, and K-means clustering, both with the original data and data transformed via Principal Component Analysis (PCA).


## Findings

### Optimal Number of Clusters:
The elbow curve analysis indicated that the best value for 
𝑘
 is 4, suggesting that 4 clusters are optimal for both the original and PCA-transformed data.

### Explained Variance of PCA:
The three principal components account for a total explained variance of 0.895, indicating that these components capture a significant portion of the data's variance.

### Impact of Using PCA for Clustering:
The elbow curve for the PCA data showed a lower inertia value compared to the original data, indicating improved clustering performance with tighter groupings of data points. Visual analysis of the clusters revealed that using PCA resulted in more distinct and non-overlapping clusters, effectively highlighting clearer patterns in the data. This suggests that reducing the number of features through PCA helps in achieving more meaningful and separable clusters.


## Data 
![Data](https://static.bc-edx.com/data/dl-1-2/m19/lms/img/scaled_DataFrame.png)



The data used in this project can be found in the `Resources` directory of this repository. 


# **Instructions**

Rename the Crypto_Clustering_starter_code.ipynb file as Crypto_Clustering.ipynb.

Load the crypto_market_data.csv into a DataFrame.
Get the summary statistics and plot the data to see what the data looks like before proceeding.
Prepare the Data

Use the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
Create a DataFrame with the scaled data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
The first five rows of the scaled DataFrame should appear as follows:
The first five rows of the scaled DataFrame

Find the Best Value for k Using the Original Scaled DataFrame

Use the elbow method to find the best value for k using the following steps:
Create a list with the number of k values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook: What is the best value for k?
Cluster Cryptocurrencies with K-means Using the Original Scaled Data

Use the following steps to cluster the cryptocurrencies for the best value for k on the original scaled data:
Initialize the K-means model with the best value for k.
Fit the K-means model using the original scaled DataFrame.
Predict the clusters to group the cryptocurrencies using the original scaled DataFrame.
Create a copy of the original data and add a new column with the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Optimize Clusters with Principal Component Analysis

Using the original scaled DataFrame, perform a PCA and reduce the features to three principal components.
Retrieve the explained variance to determine how much information can be attributed to each principal component and then answer the following question in your notebook:
What is the total explained variance of the three principal components?
Create a new DataFrame with the PCA data and set the "coin_id" index from the original DataFrame as the index for the new DataFrame.
The first five rows of the PCA DataFrame should appear as follows:
The first five rows of the PCA DataFrame

Find the Best Value for k Using the PCA Data

Use the elbow method on the PCA data to find the best value for k using the following steps:
Create a list with the number of k-values from 1 to 11.
Create an empty list to store the inertia values.
Create a for loop to compute the inertia with each possible value of k.
Create a dictionary with the data to plot the Elbow curve.
Plot a line chart with all the inertia values computed with the different values of k to visually identify the optimal value for k.
Answer the following question in your notebook:
What is the best value for k when using the PCA data?
Does it differ from the best k value found using the original data?
Cluster Cryptocurrencies with K-means Using the PCA Data

Use the following steps to cluster the cryptocurrencies for the best value for k on the PCA data:
Initialize the K-means model with the best value for k.
Fit the K-means model using the PCA data.
Predict the clusters to group the cryptocurrencies using the PCA data.
Create a copy of the DataFrame with the PCA data and add a new column to store the predicted clusters.
Create a scatter plot using hvPlot as follows:
Set the x-axis as "PC1" and the y-axis as "PC2".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Answer the following question:
What is the impact of using fewer features to cluster the data using K-Means?
REWIND
Recall that you learned how to create composite plots in a previous module. If you need a refresher on how to create these plots, review that module. You can also check Composing Plots Links to an external site. in the hvPlot documentation.
