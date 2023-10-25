# CryptoClustering
Module 19 Challenge

## Summary

I begin by employing the elbow curve technique, utilizing normalized data, to determine the most suitable 'k' value for the K-Means model, which will incorporate all the original features of the dataset.
![Original Elbow](https://github.com/Nicole-Ham/CryptoClustering/assets/134648078/db0ad030-8715-441a-ad7d-4a17e983f0d9)

Subsequently, leveraging the ideal 'k' value, I train and apply the K-Means model to create four clusters of cryptocurrencies. The inertia of each cluster was substantial, prompting consideration for feature dimensionality reduction.
![Original Scatter](https://github.com/Nicole-Ham/CryptoClustering/assets/134648078/84bc329d-f914-4b8c-90dc-c00fe4af0cd8)

In an effort to further streamline the feature set, I employed Principal Component Analysis (PCA) to establish three primary clusters. Subsequently, I leveraged the PCA-derived data to once more determine the optimal 'k' value for the K-Means model.
![PCA Elbow](https://github.com/Nicole-Ham/CryptoClustering/assets/134648078/6f57f9a1-7b08-46b5-adb5-a190a4304242)


Finally, having identified the optimal 'k' value for the PCA-derived features, I visualize the resulting clusters in a plot.
![PCA Scatter](https://github.com/Nicole-Ham/CryptoClustering/assets/134648078/71925a8c-d2ea-42e7-9adc-3c27063c2b2a)

## Requirements

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
Set the x-axis as "PC1" and the y-axis as "PC2".
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
Set the x-axis as "price_change_percentage_24h" and the y-axis as "price_change_percentage_7d".
Color the graph points with the labels found using K-means.
Add the "coin_id" column in the hover_cols parameter to identify the cryptocurrency represented by each data point.
Answer the following question:
What is the impact of using fewer features to cluster the data using K-Means?


