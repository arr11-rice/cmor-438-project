# Boosting for Classification on Horse Survival Dataset

## a. A brief description of the algorithm implemented.

This folder implements a Boosting algorithm for binary classification. Boosting is an ensemble technique that builds a strong classifier by combining the outputs of many weak learners. Each learner is trained sequentially, with each one trying to fix the mistakes of the previous one.

The key idea is that observations misclassified by earlier learners are given more weight in subsequent models, so the ensemble can focus more on hard-to-classify examples. The final prediction is a weighted vote (or sum) of all the weak learners. In this notebook, I implement the Adaptive Boosting algorithm.

Boosting is especially powerful for noisy or complex datasets where single models struggle, and it’s widely used in real-world applications due to its high accuracy and interpretability. This is why the data set for Horse Survival, which was run to not great success with the K Nearest Neighbors algorithm, is a good fit for this algorithm.

### The algorithm for Adaptive Boosting:
1. Initialize the sample weights:
- All get equal weights at the start
```bash
w_i = 1 / N   for all i = 1 to N
```

2. For t=1 to t=T (number of boosting rounds)
- Train a weak learner h_t(x) on the starting or current weights w_i
- compute the weighted error
```bash
error_t = sum over i of [w_i * I(h_t(x_i) ≠ y_i)]
```
where I(condition) is 1 if true, 0 if false
- Compute the model weight, alpha
```bash
alpha_t = 0.5 * log((1 - error_t) / error_t)
```
- Update the sample weights
```bash
w_i = w_i * exp(-alpha_t * y_i * h_t(x_i))
```
- Then normalize weights so that
```bash
sum over i of w_i = 1
```

3. Final Prediction
```bash
H(x) = sign(sum over t of [alpha_t * h_t(x)])
```



## b. A summary of the dataset(s) used for each algorithm.

I use the [Horse Survival Dataset](https://www.kaggle.com/datasets/yasserh/horsesurvivalprognostication). The dataset contains real-world veterinary data, including rectal temperature, heart rate, capillary refill time, and other physiological features. The outcome feature, which corresponds to whether a horse survived the sickness or not, allows us to train the model and also check if it is right.

The dataset comes from the UCI Machine Learning Database. 

## c. Instructions for reproducing your results

To run the (adaptive) Boosting algorithm, follow the steps below:

### 1. Clone my repository from the following link: https://github.com/arr11-rice/cmor-438-project

### 2. Navigate to this folder
```bash
cd cmor-438-project/1. Supervised Learning/8. Boosting
```
OR:
You may have to try,
```bash
cd cmor-438-project/   
cd "1. Supervised Learning"
cd "8. Boosting"
```
### 3. Install Dependencies: 

Install the needed Python packages from the `requirements.txt` file:
```bash
pip install -r requirements.txt
```
### 4. Finally, run the notebook
```bash
jupyter notebook boosting.ipynb
```
Simply run the cells in order from top to bottom.