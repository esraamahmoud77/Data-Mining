# Wish.com Product Rating Prediction

This repository contains code for predicting product ratings on Wish.com. The goal is to estimate the likelihood of customers liking a product based on its features. The dataset used for training and testing the models is the Wish.com product dataset, which includes noisy and unclean data.

## Problem Formulation

The problem is to predict the product ratings given the other features known for a product on Wish.com. The input to the model is a set of product features, such as price, description, and category, and the output is the predicted rating of the product. The data mining function required is supervised learning, as we have labeled data with product ratings. The challenges include dealing with noisy and unclean data, feature engineering, and selecting appropriate models for prediction. The impact of solving this problem is that it allows estimating the potential success of a product on Wish.com before listing it, and helps understand the factors that contribute to high product ratings.

## Experimental Protocol and Preprocessing

The experimental protocol consists of the following steps:

1. Data Loading: Load the Wish.com product dataset.
2. Data Cleaning: Remove duplicate entries, handle missing values, and perform data validation checks.
3. Feature Engineering: Extract relevant features from the dataset, such as price, description length, and product category.
4. Data Preprocessing: Normalize numerical features, handle categorical variables using one-hot encoding or label encoding, and split the data into training and testing sets.
5. Model Training and Evaluation: Train different models using the training data and evaluate their performance using appropriate evaluation metrics, such as accuracy or mean squared error.
6. Model Tuning: Experiment with different models, hyperparameters, and feature sets to improve the model's performance on the public leaderboard.
7. Documentation: Document the code with detailed comments, describe the experimental protocol, preprocessing steps, and record thoughts, observations, and performance results for each trial.

## Model Tuning and Documentation

The model tuning process involves experimenting with different configurations, hyperparameters, and models. The following trials were performed:

Trial 0:
- Model: Decision Tree
- Hyperparameters: Default
- Features: All available features
- Observations: High bias, underfitting observed in testing set

Trial 1:
- Model: Decision Tree
- Hyperparameters: Increased max depth, decreased min samples leaf
- Features: Selected relevant features (price, description length, category)
- Observations: Improved performance in testing set, reduced bias

Trial 2:
- Model: Support Vector Machine (SVM)
- Hyperparameters: Default
- Features: All available features
- Observations: High bias, underfitting observed in testing set

Trial 3:
- Model: Support Vector Machine (SVM)
- Hyperparameters: Increased C (regularization parameter), changed kernel to 'rbf'
- Features: Selected relevant features (price, description length, category)
- Observations: Improved performance in testing set, reduced bias

Trial 4:
- Model: Naive Bayes
- Features: Selected relevant features (price, description length, category)
- Observations: Moderate performance in testing set, slightly higher bias compared to decision tree and SVM models

## Answering the Questions

🌈 Why Data Mining is a misnomer? What is another preferred name?
Data Mining is considered a misnomer because it implies the extraction of data from various sources. However, the process of Data Mining involves more than just data extraction; it also involves analyzing and interpreting the data to discover meaningful patterns and insights. Another preferred name for Data Mining is Knowledge Discovery in Databases (KDD).

🌈 What is the general knowledge discovery process? What is the difference

 between a data engineer and data scientist/AI engineer?
The general knowledge discovery process involves several steps: data selection, data preprocessing, data transformation, data mining, pattern evaluation, and knowledge presentation. It is an iterative process that involves understanding the problem, exploring the data, applying suitable data mining techniques, and evaluating the discovered patterns.

A data engineer is responsible for designing, building, and maintaining the infrastructure required to process and store large volumes of data. They focus on data pipeline development, data warehousing, and data integration.

A data scientist/AI engineer, on the other hand, focuses on analyzing and interpreting the data to extract meaningful insights and build predictive models. They have expertise in statistical analysis, machine learning, and algorithm development.

🌈 In data mining, what is the difference between prediction and categorization?
In data mining, prediction refers to the process of estimating a continuous or numerical value for a given input, such as predicting product ratings. Categorization, also known as classification, involves assigning predefined categories or labels to the input data based on their characteristics. For example, categorizing emails as spam or non-spam based on their content.

🌈 Why data science/machine learning is a bad idea in the context of information security?
Data science and machine learning can pose risks in the context of information security because they rely on analyzing and processing large amounts of sensitive data. If not implemented properly, it can lead to privacy breaches, unauthorized access, and exposure of confidential information. The models developed using machine learning can also be vulnerable to adversarial attacks, where malicious actors exploit vulnerabilities to manipulate the system's behavior.

🌈 What is CIA principle, and how can we use it to access the security/privacy aspect of the AI system/pipelines?
CIA principle stands for Confidentiality, Integrity, and Availability. It is a fundamental concept in information security. Confidentiality ensures that data is accessed only by authorized individuals. Integrity ensures that data remains accurate and unaltered. Availability ensures that data and systems are accessible when needed.

To assess the security and privacy aspect of an AI system or pipeline, the CIA principle can be applied as follows:
- Confidentiality: Ensure that sensitive data used in AI models is properly encrypted and access is restricted to authorized individuals.
- Integrity: Implement mechanisms to detect and prevent unauthorized modifications or tampering of data and models.
- Availability: Ensure that AI systems and data are available and accessible to authorized users when required, while protecting against denial-of-service attacks and system failures.

By applying the CIA principle, organizations can maintain the security and privacy of their AI systems and protect against potential threats and vulnerabilities.
