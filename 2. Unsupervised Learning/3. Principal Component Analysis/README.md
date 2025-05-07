# Principal Component Analysis (PCA) on Leukemia Gene Expression

## a. A brief description of the algorithm implemented.

Principal Component Analysis (PCA) is an unsupervised learning technique used to reduce the dimensionality of a dataset while preserving as much variance as possible. It does this by finding the orthogonal axes (principal components) that capture the directions of maximum variance in the data. The original high-dimensional data is then projected onto a lower-dimensional space defined by the top principal components, retaining the most important structure of the dataset.

### The math behind PCA: algorithm steps
We want to reduce from N dimensions to k, where N>k \in integers

1. Standardize the dataset to center it around zero (by subtracting each feature by its mean)    
- I also scale each feature by dividing by the standard deviation:   
```bash
X_standardized = (X - mean(X)) / std(X)  
```
2. Compute covariance matrix   
```bash
cov_matrix = (1 / (n - 1)) * X_standardized.T @ X_standardized
```     
where, n is the number of data points and @ is matrix mult.   

**Note: the covariance matrix for my data set of over 2,000 genes per entry was too long, so I used the smaller covariance matrix, which is only as big as the number of entries:**
```bash
small_cov_matrix = (1 / (n - 1)) * X_standardized @ X_standardized.T
```    

3. Compute Eigenvectors and Eigenvalues (of the covariance matrix)    
```bash
eigvals, eigvecs = eig(cov_matrix)
```

4. Sort Eigenvectors
- Eigenvectors associated with the largest eigenvalues are the directions of most importance (i.e., variance is captured the most)
```bash
sorted_indices = argsort(eigvals)[::-1]
eigvecs_sorted = eigvecs[:, sorted_indices]
```
5. Form Projection Matrix out of the top k eigenvectors
```bash
W = eigvecs_sorted[:, :k]
```
6. Project Data onto new Subspace (by multiplying by projection matrix)
```bash
X_reduced = X_standardized @ W
```



---

## b. A summary of the dataset(s) used for each algorithm.

I use the [Leukemia Gene Expression - CuMiDa Dataset](https://www.kaggle.com/datasets/brunogrisci/leukemia-gene-expression-cumida). The dataset was provided by CuMiDa, on their official website under the id GSE9476.

This dataset is composed of gene expression levels for 22,284 genes across 64 tissue samples, each labeled with one of five different types of leukemia. Each row represents a sample (patient or tissue), and each column corresponds to the expression level of a specific gene.

This dataset is particularly well-suited for Principal Component Analysis (PCA) because it is so high-dimensional—the number of features (genes: 22,284) greatly exceeds the number of samples (64). This makes it ideal for dimensionality reduction, as PCA can help reveal the most important directions of variance in the data, reduce noise, and visualize sample groupings based on leukemia type. Additionally, PCA can help prepare the data for other tasks such as clustering or classification by reducing complexity while preserving the most informative structure. This is how we have been using the imported PCA libraries in other jupyter notebooks; but here, we build the PCA from scratch.



## c. Instructions for reproducing your results

To run the PCA algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/2. Unsupervised Learning/3. Principal Component Analysis
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook PCA.ipynb
```
Simply run the cells in order from top to bottom.