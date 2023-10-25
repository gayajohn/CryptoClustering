# Module 19: Crypto Clustering Challnenge


## Table of Contents

- Resources folder which contains crypto_market_data.csv file, the source data for our model.
- Crypto_Clustering.ipynb, the script for the analysis

## Challenge Objective

The objective of this challenge is to use knowledge of Python and unsupervised learning to predict if cryptocurrencies are affected by 24-hour or 7-day price changes.

## Analysis

**Plotting the dataframe data**

![plot1](https://github.com/gayajohn/CryptoClustering/assets/135036996/ee59cb01-ec1e-4dcb-ab22-4c633eb25ed1)

**Scaling Data**

<img width="308" alt="image" src="https://github.com/gayajohn/CryptoClustering/assets/135036996/fe7dfe36-000a-4a7e-8ef1-d2fbe70db04c">

**Elbow curve using original data**

![elbow1](https://github.com/gayajohn/CryptoClustering/assets/135036996/534b377a-fa08-4c72-8397-4263e0de2b2a)

**Clustering using original data**

![cluster1](https://github.com/gayajohn/CryptoClustering/assets/135036996/53c4635d-f2e6-4bd1-aa55-11ed2307daea)

**Creating 3 PCA components for the data**

<img width="108" alt="image" src="https://github.com/gayajohn/CryptoClustering/assets/135036996/bc3fcf26-e5fa-46f0-b2dc-013a9175ffdb">

**Elbow curve using PCA components**

![elbow2](https://github.com/gayajohn/CryptoClustering/assets/135036996/983724fd-b8fb-4d63-b94c-ae27faa21850)

**Clustering using PCA data**

![cluster2](https://github.com/gayajohn/CryptoClustering/assets/135036996/c692a413-8610-47c8-9bac-58c223d64b96)

**Composite cluster plot**

![composite1](https://github.com/gayajohn/CryptoClustering/assets/135036996/16820ca2-c0db-4347-8cb7-96226b49ccb3)

![image](https://github.com/gayajohn/CryptoClustering/assets/135036996/231e5eda-6787-4a73-bfa0-998c05b30042)


## Questions & Answers

**Question:** What is the best value for `k`?

**Answer:** The best value for k is 3.
            To determine the best number of clusters from my elbow curve, I need to look for the "elbow point," which is the point where the inertia (within-cluster sum of squares) starts to decrease at a slower rate. In this case, it seems the elbow point is likely to be around k=3. Beyond this point, the decrease in inertia is less steep, and the benefit of adding more clusters may not be significant.


**Question:** What is the best value for `k` when using the PCA data?

**Answer:** The best value for k is 4.
            To determine the best number of clusters from my elbow curve, I need to look for the "elbow point," which is the point where the inertia (within-cluster sum of squares) starts to decrease at a slower rate. In this case, it seems the elbow point is likely to be around k=4. Beyond this point, the decrease in inertia is less steep, and the benefit of adding more clusters may not be significant.
            
            
**Question:** Does it differ from the best k value found using the original data?

**Answer:** Yes, the new elbow curve seems to flatten out around k = 4, where as with the  original data, the curve seemed to flatten at k = 3. That being said, k = 3 would also be appropriate with the elbow curve above. The ultimate choice will also consider domain knowledge and other evaluation criteria.


**Question:** After visually analyzing the cluster analysis results, what is the impact of using fewer features to cluster the data using K-Means?
 
**Answer:** 
  
  Just by looking ath the composite graphs, there's a few things that stand out.
  
  
  - We already saw that the optimal no. of clusters went from 3 to 4, when using the original scaled data vs. the pca data. But it is important to note here, that 3 or 4 would have been a good choice for the pca clustering. 
  - Additionaly, the actual inertia values are much smaller for the pca elbow curve compared to the original. A smaller inertia indicates that the data points within each cluster are closer to their cluster centroid. It suggests that the clusters are more compact and tightly packed. Smaller inertia values are generally desirable as they indicate better separation of clusters.
  - When we look at the clusters based on the original data, all the coins except celcius-degree-token and ethlend are placed in the same cluster. The pca clusters are similar in the way that it places celcius-degree-token and ethlend in 2 different clusters, as before, but the rest of the coins are split by 2. Just as a note, if we conducted the pca analysis with k = 3, the clustering results will be the same as the original clustering results. 
  
  There are both positive and negative impacts of reducing dimensionality for k-means clustering:
  
  Positive
  
  -  It can make clustering more computationally efficient and reduce the risk of overfitting.
  - Fewer features may lead to simpler and more interpretable clusters, which can be useful for understanding the underlying structure of your data.
  - The K-Means algorithm may converge more quickly when working with fewer features, making it more efficient. This doesn't really apply to the dataset I'm using, which only has 41 rows.
  
  Negative
  
  - Reducing the number of features can result in a loss of information. 
  - Reducing the feature space without a clear understanding of the data's characteristics may lead to suboptimal clustering. 
  -  Fewer features can make the clustering algorithm more sensitive to outliers since there are fewer dimensions for the outliers to be diluted.
  
  
## Libraries Used

- pandas: for dataframe capabilities
- hvplot: to plot and visualize the data
- sklearn: to import KMeans, PCA and StandardScaler modules for analysis

## References

Data for this dataset was generated by edX Boot Camps LLC, and is intended for educational purposes only.

-----------------------------------------------



