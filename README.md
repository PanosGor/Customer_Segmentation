# Customer_Segmentation
This is a Customer Segmentation model made in Python 

## Goal

The goal of the first part of this project is to create segments of wholesale customers and then try to characterize those segments based on their content. 
For the clusters-segments to be created multiple clustering methods were used.

## The dataset

The dataset used contains 440 wholesale customers and their spendings on the following goods: Fresh, Milk, Grocery, Frozen, Detergents_Paper and Delicassen. 
Also, there are two more features in the dataset: Channel and Region. 
All the spendings in products are counted in dollars. 
The dataset is free of missing values.

*Figure 1: Dataset representation*

![image](https://user-images.githubusercontent.com/82097084/165760684-44948037-798e-472a-8e47-623b47e8a3a7.png)

The following visualization offers a better understanding on how the different features are related with one another:

*Figure 2: Dataset Visualization*

![image](https://user-images.githubusercontent.com/82097084/165761254-6005a01e-d475-4888-b719-5bf2c2b54bee.png)

**Preprocessing Phase**

The preprocessing phase contains the following steps:
-	Removing features Channel and Region
-	Scale data
-	Reduce dimensions
The decision to remove features Channel and Region was made since there was no information on what those represent. 
This lack of information could be misleading and distorting for the analysis to follow. 
As a second step, the data were scaled based on logarithm with base 10 to give all values equal weighting and produce trustworthy and unbiased clusters.
The last step was to reduce the dimensions of the dataset using PCA. The decision was based on the following graph:

*Figure 3: Explained variance ratio – Number of Components*

![image](https://user-images.githubusercontent.com/82097084/165761395-05f38a4a-d976-43ae-b827-c9d8a7729337.png)

As one can observe in Figure 3, 4 dimensions still explain about the 94% of the variance of the dataset. Also, fewer dimensions are easier to handle.

## Unsupervised Machine Learning (Clustering)

To create cluster-segments out of the dataset multiple clustering techniques were used:
-	K – Means Clustering
-	Agglomerative Clustering
-	Gaussian Mixture Clustering
-	DBSCAN Clustering

**K – Means Clustering**

The first technique used to segment the customers was K – Means. 
To decide the optimal number of clusters – segments of costumers to create, a combination of two metrics was used: 
Sum of Squares for Errors (SSE) and Silhouette Coefficients. 

Both metrics were plotted against the number of clusters and the results were the following:

*Figure 4: SSE values – Number of Clusters (Elbow Method)*

![image](https://user-images.githubusercontent.com/82097084/165761661-fc6ae108-d7e2-4923-82e2-e166284f8260.png)

*Figure 5: Silhouette Coefficients – Number of Clusters*

![image](https://user-images.githubusercontent.com/82097084/165761727-d4dcc301-95d2-474a-a37d-e1ed4b420ac3.png)

Based on those graphs, the best combination of SSE and Silhouette Score seems to be realized at three (3) clusters.
-SSE: 2986
-Silhouette Score: 0.28

After deciding the number of clusters to be created, the clusters were formed with the K – Means algorithm. 
To be able to understand what kind of customers each cluster contains and characterize those segments, box - plots were used. 

*Figure 6: Box – plots for Cluster #0*

![image](https://user-images.githubusercontent.com/82097084/165761865-85d92d99-a407-4bb9-989a-c3e0c93818da.png)

The first cluster (Figure 6) created seems to contain customers that on average spend more on Fresh, Grocery and Milk products while their spending on other categories is relatively low.

*Figure 7: Box – plots for Cluster #1*

![image](https://user-images.githubusercontent.com/82097084/165761977-f1b8dad4-d2c6-4ac0-b137-a79928de5d9b.png)




