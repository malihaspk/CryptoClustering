# CryptoClustering

In this challenge we are using unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

The analysis can be found in a jupyter note book named Crypto_Clustering.ipynb in the repository.

We imported PCA from sklearn.decomposition import  and also
imported StandardScaler from sklearn.preprocessing for the unsupervised machine learning assigmnet.

# Normalisation od Data
We used  the StandardScaler() module from scikit-learn to normalize the data from the CSV file.
# Finding the Best Value for K
Find the Best Value for k Using the Original Scaled DataFrame

![Alt text](<Elbow Curve_.png>)

The best value for K seems to 4 as the inertia drop between k=4 and k=5 and after that points is less as compared to k = 3 and k = 4. so the elbow is at K=4

# Cluster Cryptocurrencies with K-means Using the Original Data
 Initialize the K-Means model using the best value for k
 Fit the K-Means model using the scaled data
 Predict the clusters to group the cryptocurrencies using the scaled data
# Plotting the clusters
Create a scatter plot using hvPlot by setting 
`x="price_change_percentage_24h"` and `y="price_change_percentage_7d"`


![Alt text](<scatter 1.png>)

# Optimize Clusters with Principal Component Analysis

Using the original scaled DataFrame, perform a PCA and reduced the features to three principal components.
Total Explained Variance of the first three principal components = 89.5%

# Find the Best Value for k Using the PCA Data

![Alt text](<elbow pca.png>)

The best value for k is 4 when using the PCA data
# Cluster Cryptocurrencies with K-means Using the PCA Data
Initialize the K-Means model using the best value for Fit the K-Means model using the PCA data
Predict the clusters to group the cryptocurrencies using the PCA data
# Plotting the clusters using PC1 and PC2
 Create a scatter plot using hvPlot by setting 
`x="PC1"` and `y="PC2"`. 
 Color the graph points with the labels found using K-Means and 
![Alt text](<pca scatter.png>)

# Analysis of Visuals using original data vs PCA
After visually inspecting, we see that the number of optimal clusters, using the elbow method is equal to 4 in both full data and the data after using Principal Componenet Analysis. PCA aims to capture as much variance as possible with fewer components. Clustering in this reduced space may focus on the most informative aspects of the data and that we can see in the visual we obtained by plotting PC1 and PC2, over 70% of the explained variance ratio is shown in the graph. When plotting PC1 vs PC2, clusters 0 and 3 are more in the lower left side of graph and there is only single data point in the cluster 1 and 2. We should also consider there is another dimension PC3 , that is not shown in the visual wheras in the original data graph we can see the whole data set in the visual. Furthermore, the impact of using PCA data resulted in tighter clusters shows the more compact and meaningful groupings of data points.

