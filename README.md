<h1 align="center">DS Forum Week 9: Clustering Methods</h1>

### K-Means Clustering:

K-Means is a partitioning method that divides the dataset into K clusters, where each data point belongs to the cluster with the nearest mean. It minimizes the sum of squared distances between data points and their assigned cluster centroids.</br></br>
Pros:
Efficient and scalable for large datasets.
Works well when clusters are spherical and equally sized.</br>
Cons:
Sensitive to the initial choice of centroids.
Assumes clusters are spherical and equally sized, which might not be the case in some datasets.</br></br>

### Hierarchical Clustering:

Hierarchical clustering builds a tree of clusters by recursively merging or splitting them. It results in a hierarchy of clusters, represented as a dendrogram. The number of clusters can be chosen by cutting the dendrogram at a certain height.</br></br>
Pros:
Reveals hierarchical structure in the data.
No need to specify the number of clusters beforehand.</br>
Cons:
Computationally more expensive, especially for large datasets.
Interpretation can be subjective.</br></br>

### DBSCAN (Density-Based Spatial Clustering of Applications with Noise):

DBSCAN is a density-based clustering algorithm that groups together data points that are close to each other and have a sufficient number of neighbors, while marking outliers as noise. It doesn't require specifying the number of clusters.</br></br>
Pros:
Can discover clusters of arbitrary shapes.
Robust to noise and outliers.</br>
Cons:
Sensitive to the choice of distance metric and hyperparameters.
Performance may degrade in high-dimensional spaces.</br></br>

### Gaussian Mixture Model (GMM):

GMM is a probabilistic model that represents a mixture of Gaussian distributions. It assumes that the data points are generated from a mixture of several Gaussian distributions and uses the Expectation-Maximization (EM) algorithm to estimate the parameters.</br></br>
Pros:
Can model clusters with different shapes and sizes.
Provides soft assignments, i.e., the probability of each point belonging to each cluster.</br>
Cons:
Sensitive to the choice of initial parameters.
Computationally more expensive than K-Means.</br></br>

<h2 align="center">Scores and Evaluation</h2>
The following table displays the evaluation metrics for different clustering methods applied to the dataset:
</br></br>

| Method                   | Silhouette Score | Calinski-Harabasz Index | Davies-Bouldin Index |
|--------------------------|------------------:|------------------------:|---------------------:|
| K-Means                  |            0.340733 |                  352.521214 |                1.119195 |
| Hierarchical Clustering  |            0.312203 |                  319.579503 |                1.140937 |
| DBSCAN                   |            -0.335947 |                  9.312032 |                1.968225 |
| Gaussian Mixture Model   |            0.296289 |                  236.613360 |                2.349825 |

The K-Means and Hierarchical Clustering method generally did a better job than the other methods while DBSCAN did the worst. It is important to note that DBSCAN returned a negative Silhouette Score with this dataset, which means that some data points might be assigned to the wrong clusters, indicating potential issues with cluster quality.
