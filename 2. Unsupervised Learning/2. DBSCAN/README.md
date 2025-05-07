# DBSCAN Clustering on Bird Measurement Dataset

## a. A brief description of the algorithm implemented.

This folder implements **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**, an unsupervised learning algorithm that forms clusters based on **density** rather than distance to a centroid. Unlike K-means, DBSCAN does not require the number of clusters `K` to be specified in advance. It is especially well-suited for identifying clusters of arbitrary shape and handling noise or outliers.

DBSCAN uses two parameters:
- `eps`: the maximum distance between two points to be considered neighbors
- `min_samples`: the minimum number of points needed to form a dense region

Points that belong to a dense region form a cluster. Points in low-density regions are labeled as noise. There are three point types:

- **Core point**: A point with at least `min_samples` points (including itself) within `eps` distance.
- **Border point**: A point within `eps` of a core point but with fewer than `min_samples` neighbors itself.
- **Noise point**: A point that is not a core point and not within `eps` of any core point.

### Algorithm Steps

1. For each unvisited point:
   - If the point has at least `min_samples` neighbors within `eps`, it becomes a **core point** and starts a new cluster.
   - All points within `eps` of that core point are added to the cluster. If any of those are core points, their neighbors are also added.
2. Points that are not reachable from any core point are labeled as noise.
3. Repeat until all points are visited.

---

## b. A summary of the dataset(s) used for each algorithm.

I use the [Birds' Bones and Living Habits Datasets](https://www.kaggle.com/datasets/zhangjuefei/birds-bones-and-living-habits). The dataset was provided by Dr. D. Liu of Beijing Museum of Natural History.

This bird measurement dataset is well-suited for DBSCAN because it involves continuous, multidimensional biological data with potential natural groupings. DBSCAN can reveal clusters of birds with similar proportions and detect outliers that deviate from typical body plans. With 10 continuous features per bird and no labels, this dataset suits DBSCAN. The continuous features are:

- Length and Diameter of Humerus
- Length and Diameter of Ulna
- Length and Diameter of Femur
- Length and Diameter of Tibiotarsus
- Length and Diameter of Tarsometatarsus


The following six groupings are found in the dataset, though I do not use the labels in the running of this implementation:
1. Swimming Birds
2. Wading Birds
3. Terrestrial Birds
4. Raptors
5. Scansorial Birds
6. Singing Birds



## c. Instructions for reproducing your results

To run the DBSCAN algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/2. Unsupervised Learning/1. DBSCAN
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook DBSCAN.ipynb
```
Simply run the cells in order from top to bottom.