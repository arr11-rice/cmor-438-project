# Unsupervised Learning Algorithms

## a. A brief description of the algorithms implemented.

This repository implements four unsupervised learning algorithms from scratch:

- **K-Means Clustering**: Partitions data into k clusters based on feature similarity.
- **PCA (Principal Component Analysis)**: A dimensionality reduction technique that transforms data into a set of linearly uncorrelated components.
- **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise): Identifies clusters of varying shapes and densities while marking outliers.
- **Image Compression** with the **Singular Value Decomposition (SVD)**: Uses matrix factorization to reduce image data size while preserving essential structure.

## b. A summary of the datasets used for each algorithm.

- **K-Means Clustering**: A dataset of popular spotify songs, I restricted it to the top 40 most popular for the implementation, which formed K clusters based on each song's danceability, key, and energy.
- **PCA**: 
- **DBSCAN**: A dataset of bird physical measurements (10 total measurements, length and diameter of five differnt bones). 
- **Image Compression** with **SVD**: 


## c. Instructions for reproducing your results

To run any algorithm in the Unsupervised Learning folder, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/2. Unsupervised Learning/
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "2. Unsupervised Learning"
```
### 3. Navigate further to the desired subfolder
For example,
```bash
cd "1. K-Means Clustering"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
For example, 
```bash
jupyter notebook KMC.ipynb
```
Simply run the cells in order from top to bottom.