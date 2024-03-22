 
# Cryptocurrency Clustering with K-Means and PCA

In this project, I applied my understanding of the K-means algorithm and principal component analysis (PCA) to classify cryptocurrencies according to their price fluctuations across various timeframes. Specifically, I examined price changes over intervals spanning 24 hours, 7 days, 30 days, 60 days, 200 days, and 1 year. Our goal was to group similar cryptocurrencies based on their price change patterns.

## 1. Prepare the Data

To prepare the data, we followed these steps:

1. **Normalize the Data**: We used `StandardScaler()` from scikit-learn to normalize the data from the CSV file. This step ensures that all features have the same scale, which is essential for K-Means and PCA.

2. **Create a Scaled DataFrame**: We created a new DataFrame with the scaled data. Additionally, we set the "coin_id" index from the original DataFrame as the index for the new DataFrame.

### Scaled DataFrame Preview

The first five rows of the scaled DataFrame looked like this:

| coin_id | feature_1_scaled | feature_2_scaled | ... | feature_n_scaled |
|---------|------------------|------------------|-----|------------------|
| 1       | 0.123            | 0.456            | ... | 0.789            |
| 2       | 0.234            | 0.567            | ... | 0.890            |
| 3       | 0.345            | 0.678            | ... | 0.901            |
| 4       | 0.456            | 0.789            | ... | 0.012            |
| 5       | 0.567            | 0.890            | ... | 0.123            |

## 2. Find the Best Value for k Using the Original Scaled DataFrame

To determine the optimal value for k (the number of clusters), we followed these steps:

1. **Elbow Method**: We created a list of k values from 1 to 11 and computed the inertia (within-cluster sum of squares) for each k.

2. **Elbow Curve**: We plotted an elbow curve to visually identify the best k.

**Answer**: The best value for k.

## 3. Cluster Cryptocurrencies with K-Means Using the Original Scaled Data

Next, we clustered the cryptocurrencies using K-Means:

1. **Model Initialization**: We initialized the K-means model with the best value for k.

2. **Model Fitting**: We fit the model using the original scaled DataFrame.

3. **Predict Clusters**: We predicted the clusters and added a new column with the predicted cluster labels.

4. **Scatterplot Visualization**: We created a scatterplot with "price_change_percentage_24h" on the x-axis and "price_change_percentage_7d" on the y-axis.

## 4. Optimize Clusters with Principal Component Analysis (PCA)

To further optimize the clusters, we performed PCA:

1. **Reduce Features**: We applied PCA on the original scaled DataFrame to reduce features to three principal components.

2. **Explained Variance**: We retrieved the explained variance for each component.

**Answer**: Total explained variance of the three principal components.

3. **Create a New DataFrame**: We created a new DataFrame with the PCA data.

### PCA DataFrame Preview

The first five rows of the PCA DataFrame looked like this:

| coin_id | PC1              | PC2              | PC3              |
|---------|------------------|------------------|------------------|
| 1       | 0.123            | 0.456            | 0.789            |
| 2       | 0.234            | 0.567            | 0.890            |
| 3       | 0.345            | 0.678            | 0.901            |
| 4       | 0.456            | 0.789            | 0.012            |
| 5       | 0.567            | 0.890            | 0.123            |

## 5. Find the Best Value for k Using the PCA Data

We repeated the elbow method, this time using the PCA data:

1. **Create a List of k-values**: We created a list of k-values from 1 to 11.

2. **Compute Inertia**: We computed inertia for each k.

3. **Plot Elbow Curve**: We plotted an elbow curve.

**Answer**: Best value for k using PCA data.

## 6. Cluster Cryptocurrencies with K-Means Using the PCA Data

Finally, we clustered the cryptocurrencies using K-Means with the optimal k value from PCA:

1. **Model Initialization**: We initialized K-means with the best value for k.

2. **Model Fitting**: We fit the model using the PCA data.

3. **Predict Clusters**: We predicted clusters and added a new column.

4. **Scatterplot Visualization**: We created a scatterplot with "PC1" on the x-axis and "PC2" on the y-axis
