# K-means Clustering on Unlabeled Data

## a. A brief description of the algorithm implemented.

This folder implements **K-means clustering**, a classic unsupervised machine learning algorithm. Unlike supervised learning methods (such as logistic regression or neural networks), K-means does not rely on labeled data. Instead, it attempts to discover structure in a dataset by **partitioning the data into K distinct clusters** based on similarity.

The core idea is to assign each data point to the cluster whose center is nearest, then update the centers to be the mean of all points assigned to that cluster. The algorithm iteratively refines these cluster assignments to minimize overall distortion or spread.


### The math behind the algorithm

Let:
- **K** be the number of clusters, a parameter which the user can pick
- **X = {x₁, x₂, ..., xₙ}** be the dataset with n data points
- **μ₁, μ₂, ..., μₖ** be the centers of the K clusters

The algorithm seeks to minimize the **total within-cluster sum of squares**, also called the **inertia** or distortion:

Inertia = sum over i=1 to K of sum over all x in C_i of ||x - μ_i||²
(the first sum is over all clusters, the second sum is over each point in a cluster)  

Where:
||x - μ_i|| is the Euclidean distance between point x and center μ_i  
C_i is the set of points assigned to cluster i   

### Algorithm Steps:

1. **Initialization**: Choose K initial centers

2. **Assignment Step**:
   Assign each point to the nearest center:
  c_i = argmin_{j in {1, ..., K}} || x_i - μ_j ||

3. **Update Step**:
   Update each center to be the mean of the points assigned to it:
   μ_j = (1 / |C_j|) * Σ_{x ∈ C_j} x

4. **Repeat** until centers stop changing significantly or a max number of iterations is reached.

---


## b. A summary of the dataset(s) used for each algorithm.

I use the [Spotify Most Popular Songs Dataset](https://www.kaggle.com/datasets/rishabhpancholi1302/spotify-most-popular-songs-dataset). This data set has features for song name and artist and release date, but I only use three features: danceability, energy, and key, since these are already numerical and relate to the musical experience, which is what we are trying to cluster the songs based on.

For ease of identifying good clusters, I use the feature track_popularity to restrict my dataset to the top 40 most popular songs on the file. These are what I cluster.

## c. Instructions for reproducing your results

To run the K-means cluster algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/2. Unsupervised Learning/1. K-Means Clustering
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook KMC.ipynb
```
Simply run the cells in order from top to bottom.