# Supervised Learning Algorithms

## a. A brief description of the algorithms implemented.

This repository implements eight supervised learning algorithms from scratch:

- **Perceptron**: A binary classifier that updates weights based on misclassified samples using a step function. Implemented in 2D to visually demonstrate classification boundaries.

- **Linear Regression**: A model that predicts a continuous output by minimizing mean squared error. I implemented a two-variable linear regression to model relationships between numerical features of a dataset (datasets explained below).

- **Logistic Regression**: A probabilistic binary classifier that uses the sigmoid activation function and minimizes categorical cross-entropy loss. I implemented both a 2D and 1D logistic regression model.

- **Neural Networks**: A  neural network with one hidden layer and non-linear activation functions, capable of multiclass classification. 

- **K Nearest Neighbors**: 
- **Regression Trees**:
- **Random Forests**:
- **Boosting**:


## b. A summary of the datasets used for each algorithm.

- **Perceptron**: Applied on a subset of a dataset with health data and diabetes diagnoses, allowing the perceptron to use other health features to categorize patients as having or not having diabeter.

- **Linear Regression**: Implemented on a dataset of car data for cars manufactured in 2000. Used the features that were, or could become encoded as, numerical to make the linear regression that best modelled a function for the CO2 emissions of each car.

- **Logistic Regression**: Used the same Diabetes dataset, only a different subset, and tested all the different 2-feature combinations to evaluate model performance based on features that were used. 

- **Neural Network**: Trained on a Drug Treatment dataset, which includes features like age, sex, blood pressure, cholesterol, and Na_to_K to predict one of five drug categories.

- **K Nearest Neighbors**:
- **Regression Trees**:
- **Random Forests**:
- **Boosting**:


## c. Instructions for reproducing your results

To run any algorithm in the Supervised Learning folder, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
```
### 3. Navigate further to the desired subfolder
For example,
```bash
cd "3. Logistic Regression"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
For example, 
```bash
jupyter notebook .ipynb
```
Simply run the cells in order from top to bottom.