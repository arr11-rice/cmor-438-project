# Perceptron Classifier on Diabetes Dataset

## a. A brief description of the algorithm implemented.

This folder implements a **Perceptron**, a simple machine learning algorithm. A perceptron classifies data into two bins. Though it can be extended to higher dimensions, I implemented a 2D Perceptron, meaning it uses only two features of a data point to sort it into the two categories.

### This is the math behind an n-dimensional perceptron implementation like mine 

#### Step 1
Let:

- **x** = [x₁, x₂, ..., xₙ]ᵀ: input feature vector
- **w** = [w₁, w₂, ..., wₙ]ᵀ: weight vector
- **b**: bias term  
- **y** ∈ {0, 1}: true label  
- **ŷ** ∈ {0, 1}: predicted label  

The perceptron computes a **linear combination**:
z = wᵀx + b = ∑ (wᵢ · xᵢ) + b

Or: append 1 to each input to capture the the bias term \(b\) within x and w:

- Augmented input: x̃ = [1, x₁, x₂, ..., xₙ]ᵀ 
- Augmented weights: w̃ = [b, w₁, w₂, ..., wₙ]ᵀ

Then the computation becomes:
z = wᵀx = ∑ (wᵢ · xᵢ)

#### Step 2
Apply a **step function** (activation):
ŷ = 1 if z ≥ 0
ŷ = 0 if z < 0

#### Step 3
For each training sample \((x^{(j)}, y^{(j)})\), the perceptron updates its weights if there's an error:
error = y - ŷ

How much the weight is updated depends on the  **learning rate**, η.
In my implementation, this was set to 0.1 (though inside the Perceptron class the default is 0.01), but it can be modified.
Then, the weights and bias are updated according to the following rule:
w + η · error · x -> w 
b + η · error -> b

This process repeats for a set number of epochs, or until there is not any error. In my implementation, the number of epochs is set to 1000.


## b. A summary of the dataset(s) used for each algorithm.

I use the [Pima Indians Diabetes Dataset](https://www.kaggle.com/datasets/uciml/pima-indians-diabetes-database), which contains medical diagnostic measurements for women aged 21 and older of Pima Indian heritage. The original dataset comes from the National Institute of Diabetes and Digestive and Kidney Diseases. The features are:

- Pregnancies
- Glucose
- BloodPressure
- SkinThickness
- Insulin
- BMI
- DiabetesPedigreeFunction
- Age
- Outcome (1 = has diabetes, 0 = no diabetes)

For visualization and testing purposes, I extract a small subset of the rows available:
- 20 samples with `Outcome = 1`
- 20 samples with `Outcome = 0`
- Only 2 features (e.g., Glucose and BMI) are used at a time for simplicity and 2D plotting, but these can be picked by the user or allow the jupyter notebook, perceptron.ipynb, to run all possible combinations of 2 features out of the 8, only showing a few of the best performing ones.

## c. Instructions for reproducing your results

To run the Perceptron algorithm on a subset of the diabetes dataset, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/1. Perceptron
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "1. Perceptron"
```

### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook perceptron.ipynb
```
Simply run the cells in order from top to bottom.