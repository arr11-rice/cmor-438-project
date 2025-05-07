# Logistic Regression on Diabetes Dataset

## a. A brief description of the algorithm implemented.

This folder implements **Logistic Regression**, a supervised learning algorithm used for binary classification. Because this is a less simple way to do the same task as the perceptron from before, I bring back (a different) part of the Pima Indians Diabetes Database from the National Institute of Diabetes and Digestive and Kidney Diseases. Unlike linear regression, which outputs continuous values, logistic regression predicts the probability that an input belongs to a certain class — in this case, whether a patient has diabetes or not. It does so by applying the sigmoid function to a weighted sum of input features, which is unlike the perceptron, which was purely linear.

This model is trained to find the best weights and bias that separate the two classes (diabetic and non-diabetic), based on multiple health-related features from the data.

### This is the math behind Logistic Regression

Given input features x₁, x₂, ..., xₙ, the model first computes a linear combination:  
z = w₁·x₁ + w₂·x₂ + ... + wₙ·xₙ + b

This z value is passed through the sigmoid function to produce a probability:
σ(z) = 1 / (1 + e^(–z))

The output of the sigmoid function is between 0 and 1, which is interpreted as the probability that the patient has diabetes. If this value is greater than 0.5, the model predicts 1 (diabetic); otherwise, it predicts 0 (non-diabetic).

The model is trained by minimizing the following loss function:

Loss = –(1/m) Σ [yᵢ log(ŷᵢ) + (1 – yᵢ) log(1 – ŷᵢ)]

Where:
yᵢ is the true class label (0 or 1)
ŷᵢ is the predicted probability
m is the number of training examples

The model's performance is evaluated using the same four metrics as the perceptron, as well as the confusion matrix:

1. Accuracy
2. Precision
3. Recall
4. F1-score

We also perform a test/train split (20/80, as with linear regression) to help evaluate how well the model generalizes to unseen data.

## b. A summary of the dataset(s) used for each algorithm.

I use the [Pima Indians Diabetes Dataset](https://www.kaggle.com/datasets/kandij/diabetes-dataset), which contains medical diagnostic measurements for women aged 21 and older of Pima Indian heritage. The original dataset comes from the National Institute of Diabetes and Digestive and Kidney Diseases. The features are:

- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age
- Outcome (1 = has diabetes, 0 = no diabetes)

Only 2 features (e.g., Glucose and BMI) are used at a time for simplicity and 2D plotting, but these can be picked by the user or allow the jupyter notebook, perceptron.ipynb, to run all possible combinations of 2 features out of the 8, only showing a few of the best performing ones.

Some values such as insulin or skin thickness may be missing data, so we optionally handle that via filtering.


## c. Instructions for reproducing your results

To run the Logistic Regression algorithm on the diabetes dataset, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/3. Logistic Regression
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "3. Logistic Regression"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook logistic_reg.ipynb
```
Simply run the cells in order from top to bottom.