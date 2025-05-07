# Linear Regression on Car CO2 Emmissions Dataset

## a. A brief description of the algorithm implemented.

This folder implements **Two-Variable Linear Regression**, which predicts one continuous output using two features. This is similar to the previous Perceptron, except the goal is not classification, but regression. Like the perceptron, this model is linear, meaning it fits a straight line to the data by adjusting the slope and y-intercept.

In this case, we aim to predict **CO₂ emissions** of vehicles based on features like engine size, number of cylinders, gasoline type (regular or premium), and fuel consumption. I explore **all possible pairs** of these numerical features to determine which combinations produce the best predictions based on standard regression metrics: MSE and R^2 score.


### This is the math behind Two-Variable Linear Regression like the one I implement

Given two input features `x₁` and `x₂`, the model predicts `ŷ` as:
ŷ = w₁·x₁ + w₂·x₂ + b

Where:
- `x₁`, `x₂` are the input features
- `w₁`, `w₂` are the learned weights
- `b` is the bias (y-intercept)
- `ŷ` is the predicted CO₂ emission

The model is trained to minimize the **Mean Squared Error (MSE)**:
MSE = (1/m) · Σ (yᵢ - ŷᵢ)²

Where:
- `m` is the number of training examples
- `yᵢ` is the actual CO₂ emission
- `ŷᵢ` is the predicted CO₂ emission for the same sample

Two evaluation metrics are used to find the best pairing of inputs:
- **MSE** — measures the average squared error
- **R² score** — tells how well the model explains the variation in the data, with the following formula: R² = 1 - (SS_res / SS_tot).

SS_res = ∑(yᵢ - ŷᵢ)² is the sum of squared differences between actual and predicted values  
SS_tot = ∑(yᵢ - ȳ)² is the total sum of squares, or squared differences between actual values and their mean  
yᵢ = actual value  
ŷᵢ = predicted value  
ȳ = mean of all actual values  


Also, a 20/80 test/train split is used in order to try to avoid overfitting the training data.


## b. A summary of the dataset(s) used for each algorithm.

I use the [Fuel Consumption and CO₂ Emissions dataset](https://www.kaggle.com/datasets/krupadharamshi/fuelconsumption), which contains real-world data for various vehicles manufactured in the year 2000. Some of the features in this data are below:

- `ENGINE SIZE` (in liters)
- `CYLINDERS` (number of cylinders)
- `TRANSMISSION` (e.g., A4 = automatic, M5 = manual)
- `FUEL` type (e.g., X = regular gasoline, Z = premium gasoline)
- `FUEL CONSUMPTION` (combined, in L/100 km)
- `CO2 EMISSIONS` (target, in g/km)

For simplicity and interpretability, only **two input features are used at a time**, such as:

- `ENGINE SIZE` and `FUEL CONSUMPTION`
- `CYLINDERS` and `FUEL` (encoded)
Note: because the rest of the features are not numerical, the four features above are all that are used in this implementation.

The `FUEL` column, which is categorical, is manually encoded:
- `"X"` (regular gasoline) → `0`
- `"Z"` (premium gasoline) → `1`

Only rows with fuel types `"X"` or `"Z"` are kept in the dataset.

## c. Instructions for reproducing your results

To run the Linear Regression algorithm on the car emissions dataset, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/2. Linear Regression
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "2. Linear Regression"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook linear_reg.ipynb
```
Simply run the cells in order from top to bottom.