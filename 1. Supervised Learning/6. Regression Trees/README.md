# Regression Trees on Housing Dataset

## a. A brief description of the algorithm implemented.

This folder implements a **Regression Tree** model for predicting house prices. Unlike linear regression, which attempts to fit a single equation across the entire dataset, regression trees split the data recursively into regions where the response variable (in this case, house price) is more homogeneous. Each split is based on the feature that best reduces prediction error, and within each region, the prediction is simply the average price of the training samples in that region.

Regression trees are easy to visualize and can handle both linear and non-linear relationships well. They also naturally capture interactions between features (e.g., square footage matters more in one neighborhood than another). However, they can easily overfit, too.


### The algorithm:
1. **At each node**, the algorithm finds the best feature and value to split on, minimizing the **mean squared error (MSE)** in the resulting child nodes:

   MSE = (1/n) * Σ(yᵢ - ȳ)²

2. **Split recursively**:
   - Continue splitting each node until a stopping criterion is reached (e.g., max depth, min samples per leaf, or zero MSE).

3. **Prediction**:
   - For a new data point, traverse the tree according to its feature values until reaching a leaf.
   - The prediction is the average of the training targets in that leaf.

4. **(Optional) Pruning or limiting tree depth**:
   - This is used to prevent overfitting by simplifying the model.


## b. A summary of the dataset(s) used for each algorithm.

I use the [HOUSE PRICE PREDICTION - SEATTLE Dataset](https://www.kaggle.com/datasets/samuelcortinhas/house-price-prediction-seattle) , which includes records of homes sold in Seattle, Washington, between August and December 2022. 

The target variable is `price`, which we aim to predict based on the home’s other features, like number of bathrooms, zip code, and so on.

Like in previous notebooks, I use a train/test split of 80/20 to evaluate performance. 

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