# Data Science & Machine Learning Final Repository

**Creator:** Arturo Rodriguez Lopez   
**Semester**: Spring 2025

![Machine Learning](cmor438_repo_pic.jpg)

## Overview

This repository is a collection of machine learning algorithms developed as part of a project on supervised and unsupervised learning. It walks through the end-to-end stages of a machine learning workflow: data preprocessing, model training, evaluation, and algorithm performance visualization.

The project is organized into two main categories:

- **Supervised Learning**: Models trained on labeled datasets (classification and regression).
- **Unsupervised Learning**: Models that find patterns in data without explicit labels (e.g. clustering).

Python is used throughout, with the main libraries used throughout being `scikit-learn`, `numpy`, `pandas`, and `matplotlib`.

---

## Project Structure

├── 1. Supervised Learning/  
│ ├── 1. Perceptron/  
│ ├── 2. Linear Regression/  
│ ├── 3. Logistic Regression/  
│ └── ...  
├── 2. Unsupervised Learning/  
│ └── 1. K-Means Clustering/  
│ └── ...  
├── .gitignore   
├── cmor438_repo_pic.jpg  
├── README.md  
└── requirements.txt  


## Supervised Learning

Supervised learning uses input-output pairs to learn a function that maps inputs to labels.

### Classification

- **Perceptron**: A basic binary classifier using a linear decision boundary.
- **Logistic Regression**: A probabilistic classifier for binary or multiclass classification.
- **Neural Networks**: Flexible models capable of learning complex patterns; I apply one here to a makeshift clinical problem.
- **K Nearest Neighbor**: An algorithm that classifies based on the majority class among the k-nearest neighbors
- **Boosting**: Ensemble method (meaning, it combines predictions from various other, usually weaker, models) to improve prediction of continuous variables.

### Regression

- **Linear Regression**: Predicts continuous outputs from input features using a best-fit line.
- **Regression trees**: Decision tree models adapted for predicting continuous values.  
Note: Decision trees are models that split input data using feature thresholds to make decisions; can be used for both classification and regression.  
- **Random forest**: Combines multiple decision trees to improve accuracy and reduce overfitting.



---

## Unsupervised Learning 

Unsupervised learning analyzes structure in unlabeled data.

### Unsupervised Learning Algorithms
- **K-Means Clustering**: Partitions data into k clusters based on feature similarity.
- **PCA (Principal Component Analysis)**: A dimensionality reduction technique that projects the data onto directions of greatest variance, thereby attempting to preserve as much information as possible.
- **DBSCAN** (Density-Based Spatial Clustering of Applications with Noise): Identifies clusters of varying shapes and densities while marking outliers.
- **Image Compression** with the **Singular Value Decomposition (SVD)**: Uses matrix factorization to reduce image data size while preserving essential structure.

---

## Getting Started

### Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

### Run an Algorithm
To run a specific script, navigate to the appropriate directory. For example,  do
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"  
```
Navigate further to the desired subfolder, such as by doing the following:  
```bash
cd "3. Logistic Regression"
```
Finally, run the notebook by, for instance, writting
```bash
jupyter notebook file.ipynb
```
And simply run the cells in order from top to bottom.