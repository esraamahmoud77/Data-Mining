# Project Readme:

## Problem Formulation
In this assignment, the objective is to predict the outcome of specific speed dating sessions based on the profiles of two people. The goal is to implement a recommendation system to enhance matching in speed dating events. The dataset used is a clean but feature-rich tabular dataset containing information about each dating session. The assignment focuses on a binary classification task, predicting the probability of a dating session leading to a successful match.

### Input:
- A tabular dataset resembling an online dating dataset (Tinder-like).

### Output:
- Predicting the outcome of a speed dating session (match/unmatch).
- Predicting the probability that the dating session will lead to a successful match.

### Data Mining Function:
- Binary Classification Task.
- Prediction Task.

### Challenges:
- Data cleaning, dealing with missing data.
- Model selection and tuning.
- Feature selection and engineering.
- Dealing with an unbalanced dataset.
- Addressing potential issues like overfitting or underfitting.

### Impact:
The project aims to implement a recommendation system for better matchmaking in speed dating events. Additionally, it seeks to identify the most important attributes contributing to successful matches, providing insights into the customer base of the platform.

### Ideal Solution:
Designing and selecting a machine learning model that suits the data and understanding the crucial features impacting classification and prediction.

## Experimental Protocol:

### Steps:
1. **Data Exploration:**
   - Understand the structure and characteristics of the dataset.
   
2. **Data Preprocessing:**
   - Handle missing values.
   - Convert data types.
   - Drop irrelevant columns.
   - Feature engineering.
   - Data balancing.

3. **Building a Preprocessing Pipeline:**
   - Separate numeric and categorical features.
   - Apply imputation and scaling.

4. **Building Models:**
   - Utilize RandomForestClassifier, XGBClassifier, and AdaBoostClassifier.
   
5. **Hyperparameter Tuning Trials:**
   - Grid Search, Randomized Search, and Bayesian Search for each model.

6. **Performance Evaluation:**
   - Assess the performance of each model using AUROC.

## Model Tuning and Documentation:

### Trial 0:
**Thoughts and Observations:**
- Initial model using RandomForestClassifier with default hyperparameters.
- Establishing a baseline for comparison.

### Trial 1:
**Thoughts and Observations:**
- Switching to XGBClassifier to explore ensemble methods.
- Hyperparameter grid search for parameters like the number of estimators and maximum depth.

### Trial 2:
**Thoughts and Observations:**
- Continuing with XGBClassifier using randomized search.
- Tuning hyperparameters like learning rate and maximum depth.

### Trial 3:
**Thoughts and Observations:**
- Trying AdaBoostClassifier for model diversification.
- Randomized search for hyperparameters like learning rate, number of estimators, and algorithm choice.

### Trial 4:
**Thoughts and Observations:**
- Addressing repeated results by exploring DecisionTreeClassifier.
- Bayesian search for hyperparameters related to the decision tree structure.

### Trial 5:
**Thoughts and Observations:**
- Trying XGBClassifier with Bayesian search to leverage informed search.
- Optimizing hyperparameters like learning rate and maximum depth.

### Trial 6:
**Thoughts and Observations:**
- Exploring DecisionTreeClassifier with Bayesian search.
- Optimizing hyperparameters related to the decision tree structure.

## Questions ❓
1. **Why a simple linear regression model (without any activation function) is not good for a classification task, compared to Perceptron/Logistic regression?**
   - Linear regression models can only model linear functions, while classification tasks require non-linear activation functions, which Perceptron and Logistic regression utilize.

2. **What's a decision tree, and how is it different from a logistic regression model?**
   - A decision tree is a non-linear classifier that can handle both categorical and continuous data, whereas logistic regression is a linear classifier assuming linearly separable data.

3. **What's the difference between grid search and random search?**
   - Grid search tests every unique combination of hyperparameters in the search space, while random search evaluates a specific number of hyperparameter sets at random.

4. **What's the difference between Bayesian search and random search?**
   - Bayesian search is an informed search method that learns from previous iterations, while random search treats iterations independently.

5. **Why Data Mining is a misnomer? What is another preferred name?**
   - Data Mining is a misnomer because it implies extracting valuable information from raw data, whereas a more accurate term is Knowledge Discovery in Databases (KDD).

6. **What is the general knowledge discovery process? What is the difference between a data engineer and data scientist/AI engineer?**
   - The knowledge discovery process involves data selection, data preprocessing, data transformation, data mining, pattern evaluation, and knowledge presentation. A data engineer focuses on building and maintaining data architecture, while a data scientist/AI engineer works on extracting insights and building models.

7. **In data mining, what is the difference between prediction and categorization?**
   - Prediction involves predicting a continuous value, while categorization involves classifying data into predefined categories or classes.

8. **Why is data science/machine learning a bad idea in the context of information security?**
   - Data science/machine learning can pose security risks if models are not adequately secured, leading to privacy breaches and exploitation.

9. **What is the CIA principle, and how can we use it to assess the security/privacy aspect of the AI system/pipelines?**
   - The CIA principle (Confidentiality, Integrity, Availability) is a security model. To assess the security/privacy aspect of AI systems, one can evaluate whether the system ensures confidentiality, integrity, and availability of sensitive information.

