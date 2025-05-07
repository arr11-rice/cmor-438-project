# Image Compression with the Singular Value Decomposition (SVD) 

![Nature](whale_handshake.jpg)

## a. A brief description of the algorithm implemented.

This folder implements image compression using the Singular Value Decomposition (SVD). SVD is a matrix factorization technique that decomposes a matrix A into three components: U, Σ, and V^T, where
- U and V are orthogonal matrices, and
- Σ is a diagonal matrix of singular values sorted in decreasing order.

In the context of images, we treat the pixel intensity matrix as a 2D array and apply SVD to it. By keeping only the top 
k singular values and their corresponding vectors in U and V^T, we can reconstruct an approximation of the original image using significantly fewer data. This compressed representation captures the most important features of the image while discarding less relevant details, reducing file size with minimal loss of quality.

### The math behind Image compression w/ SVD

Given an image matrix A of shape m×n, the SVD is:  
A=UΣV^T
 
To compress:
- Keep only the top k singular values: Σ_k
- Truncate U to m×k, and V^T to k×n
- Reconstruct through the matrix multiplication of 3 matrices:   
A_k =U_k Σ_k V^T_k
​
 
This approximation A_k becomes more accurate as k increases. The goal is to find the smallest k that retains acceptable visual quality.

---

## b. A summary of the dataset(s) used for each algorithm.

I use a .jpg image for compression ('whale_handshake.jpg' inside this folder), which I turn into grayscale for simplicity.



## c. Instructions for reproducing your results

To run the Image Compression w/ SVD algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/2. Unsupervised Learning/4. Image Compression: Singular Value Decomposition
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook SVD.ipynb
```
Simply run the cells in order from top to bottom.