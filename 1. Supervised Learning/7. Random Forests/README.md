# Random Forest on Housing Dataset

## a. A brief description of the algorithm implemented.

This folder implements a Random Forest Regressor to predict house prices. A random forest is an ensemble method that builds multiple regression trees and combines their predictions to improve accuracy and generalization.

Instead of relying on a single decision tree—which can overfit—random forests grow many trees using bootstrapped samples of the training data and random subsets of features at each split. During prediction, the final output is the average prediction across all trees.

This approach helps reduce variance, makes the model more robust to noise and outliers, and typically results in significantly better performance than a standalone regression tree. Random forests also provide useful tools like feature importance, helping identify which variables most influence the target.


### The algorithm:
1. Bootstrap Sampling
- randomly sample from the training data to create multiple datasets—one for each tree.
2. Grow a Regression Tree on Each Sample
- at each split in the tree, choose the best split from a random subset of features.
3. Make Predictions by Averaging
- each tree outputs a predicted value for a test input. The final prediction is the mean of these predictions across all trees.


## b. A summary of the dataset(s) used for each algorithm.

The same as the Regression Trees notebook, I use the [HOUSE PRICE PREDICTION - SEATTLE Dataset](https://www.kaggle.com/datasets/samuelcortinhas/house-price-prediction-seattle) , which includes records of homes sold in Seattle, Washington, between August and December 2022. 

Each record includes:

- Home attributes (e.g., number of beds, baths, square footage)
- Lot characteristics (e.g., lot size, ZIP code)
- Sale price

The target variable is price, and the goal is to predict it using the other features. As with the regression tree model, I apply a log transformation to the target variable to reduce skew and stabilize variance. The hope is that Random Forest, by leveraging an ensemble of models, will yield a higher R² score and better predictive power than a single tree.

## c. Instructions for reproducing your results

To run the Random Forest algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/7. Random Forests
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "7. Random Forests"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook RF.ipynb
```
Simply run the cells in order from top to bottom.