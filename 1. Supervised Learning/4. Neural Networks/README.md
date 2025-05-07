# Neural Networks on Drug Treatment Dataset

## a. A brief description of the algorithm implemented.

This folder implements a **neural network** (which can also be called a multilayer perceptron) for classification into five categories. As opposed to the perceptron and logistic regression implementations from before, this neural network implementation can classify into more than binary categories. I use a test dataset that gives health information for patients and one of five drugs that worked on them.

Neural networks are machine learning models inspired by the structure of the brain. They consist of layers of nodes (neurons) that transform input data through learned weights and non-linear activation functions. By training on labeled data to adjust weights, the aim is for this neural network to accurately map inputs to outputs (in a sense, make a prediction).


### This model architecture

The neural network used here includes:
- **Input layer**: Accepts 5 preprocessed features (numerical and one-hot encoded categorical variables: age, sex, blood pressure, cholesterol, Na_to_K).
- **One hidden layer**: Uses 10 neurons with **ReLU** activation to introduce non-linearity, f(x) = max(0,x)
- **Output layer**: Uses 5 neurons with **softmax** activation to output a probability distribution across the five drug categories, for turning raw values to probabilities that sum to 1.
- **Loss function**: Categorical cross-entropy, suitable for multi-class classification tasks.
- **Optimizer**: Stochastic Gradient Descent (SGD)  used to minimize the loss over training epochs.

During training, the network learns to associate patterns in patient health features with the drug that was most effective for them using 80% of the data; the other 20% is used for testing. The learning rate remains consistent with other implementations in the 1. Supervised Learning folder: learning rate = 0.01. But I increased the epochs from 1,000 to 30,000 because the loss function did not start decreasing slowly until around epoch 10,000.

---


## b. A summary of the dataset(s) used for each algorithm.

I use the [Drugs A, B, C, X, and Y Dataset](https://www.kaggle.com/datasets/pablomgomez21/drugs-a-b-c-x-y-for-decision-trees). The features are:

- `Age`: Age of the patient
- `Sex`: M or F
- `BP`: Blood pressure (HIGH, NORMAL, or LOW)
- `Cholesterol`: HIGH or NORMAL
- `Na_to_K`: Sodium-to-potassium ratio

The target variable is the **drug type** that worked on the patient, with five possible classifications: **drugA, drugB, drugC, drugX, and drugY**.


## c. Instructions for reproducing your results

To run the Neural Networks algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder

cd cmor-438-project/1. Supervised Learning/4. Neural Networks

### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:

pip install -r requirements.txt

### 4. Finally, run the notebook
jupyter notebook NN.ipynb

Simply run the cells in order from top to bottom.