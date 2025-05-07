# Regression Trees on ______ Dataset

## a. A brief description of the algorithm implemented.

This folder implements a **K-Nearest Neighbors (KNN)** algorithm for classification. Unlike other models such as perceptrons or logistic regression, KNN does not build a predictive equation during training. Instead, it memorizes the training data and makes predictions by comparing new points to their closest neighbors in the feature space. I test this implementation on a dataset that includes vitals and medical history of sick horses to predict whether they will survive or not.

KNN is a non-parametric, lazy learning algorithm. Non-parametric means that it does not learn parameters during training (like weights in NNs, for instance). Instead, KNN simple stores the training set. Lazy learning means that the KNN algorithm defers all computation until it needs to make a prediction. When a new point needs to be classified, KNN finds the most common label among the K nearest labeled points in the dataset.

### The algorithm:
1. Compute Distance to All Training Points
- For each training point x_i in X_train, compute the Euclidean distance to x_test:

d_i = sqrt( sum_over_j (x_test[j] - x_i[j])^2 )
2. Sort by Distance
- Create a list of all distances d_i and their corresponding labels y_i.
- Sort this list by ascending distance.
3. Select the K Nearest Neighbors
- Take the first K items from the sorted list (the K closest training points).
4. Vote (Classification)
- Count the frequency of each class label among the K neighbors.
- Predict the most frequent label:

y_hat = most_common([y_1, y_2, ..., y_K])

5. Repeat for All Test Points
- If you have multiple test points, repeat the steps above for each one.


## b. A summary of the dataset(s) used for each algorithm.

I use the [ Dataset]( link ). The dataset contains ...

The dataset comes from ...

Like in previous notebooks, I use a train/test split of 80/20 here.

## c. Instructions for reproducing your results

To run the Regression Trees algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/6. Regression Trees
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "6. Regression Trees"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook RT.ipynb
```
Simply run the cells in order from top to bottom.