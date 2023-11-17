# Airbnb Price Category Prediction Project

## Overview

This project focuses on predicting the price category of Airbnb listings in Montreal during 2019. The goal is to assist hosts in determining an optimal price for their listings, simplifying the process and enhancing user experience. The project utilizes a multi-objective, multi-modal classification approach, incorporating both text and image data to make predictions.

## Problem Statement

Airbnb hosts often face challenges in pricing their listings effectively, requiring extensive research. This project aims to address this issue by predicting the price category of a listing based on its characteristics. Additionally, it recommends a pricing range to new hosts, streamlining the listing process.

## Dataset

The dataset used contains listings from different areas in Montreal during 2019, providing rich information for each listing, including text descriptions and images.

## Challenges and Solutions

The project involves addressing several challenges, including data cleaning, dealing with missing data, selecting suitable model architectures, handling multimodal representation, and managing class imbalances. Solutions involve experimenting with various neural network architectures, including LSTM, GRU, and Bidirectional models. Additionally, transfer learning with VGG16 for computer vision tasks is explored.

## Project Structure

1. **Data Exploration**: Initial exploration of the dataset, handling missing values, and language detection for text descriptions.

2. **Data Preprocessing**: Cleaning and preprocessing the data, converting labels to categorical codes, and handling image data.

3. **Model Implementations**: Various model architectures are implemented, including fully connected, LSTM, GRU, Bidirectional, and simplified NLP and computer vision models.

4. **Transfer Learning**: Exploration of transfer learning using the VGG16 pre-trained model for computer vision tasks.

5. **Experimentation and Evaluation**: Detailed trials with different models, monitoring performance on training, validation, and test sets, and making observations about underfitting and overfitting.

6. **Suggestions and Future Work**: Recommendations for further improvements, including hyperparameter tuning, ensemble methods, and additional model exploration.

## Model Tuning and Documentation:
### Trial 0:

**Thoughts:**
- Start with a baseline model using default parameters.
- Identify key features and preprocess the data.
- Use a simple architecture to understand the initial performance.

**Observations:**
- Baseline accuracy achieved.
- Identified potential areas for improvement in feature selection.

### Trial 1:

**Thoughts:**
- Introduce text inputs using GRU/LSTM layer for sequential data.
- Adjust hyperparameters for the text model.
- Evaluate the impact on accuracy.

**Observations:**
- Improved accuracy with the inclusion of text features.
- GRU/LSTM layer helps capture sequential patterns.

### Trial 2:

**Thoughts:**
- Enhance text modeling with a BiDirectional layer for better context understanding.
- Experiment with different dropout rates to prevent overfitting.

**Observations:**
- BiDirectional layer improves the model's ability to capture bidirectional dependencies in text.
- Dropout helps mitigate overfitting.

### Trial 3:

**Thoughts:**
- Introduce image inputs using Conv2D layer.
- Adjust hyperparameters for the image model.
- Evaluate the combined impact of text and image features.

**Observations:**
- Improved accuracy with the inclusion of image features.
- Conv2D layer aids in extracting hierarchical features from images.

### Trial 4:

**Thoughts:**
- Add a Dropout layer to the image model to prevent overfitting.
- Fine-tune hyperparameters for both text and image models.

**Observations:**
- Dropout in the image model helps prevent overfitting.
- Fine-tuning enhances overall model performance.

### Trial 5:

**Thoughts:**
- Implement a multi-modality learning approach by combining text and image features.
- Use a fusion layer to merge representations.
- Fine-tune the architecture for optimal performance.

**Observations:**
- Multi-modality learning further improves accuracy.
- Fusion layer successfully combines text and image information.

### Trial 6:

**Thoughts:**
- Explore multi-objective learning by predicting both price and type.
- Design a model with multiple output layers.
- Adjust hyperparameters to balance both tasks.

**Observations:**
- Successfully implemented multi-objective learning.
- Balanced model that predicts both price and type accurately.

### Final Thoughts:

- Iteratively improving the model through various trials enhances its performance.
- Documentation of each trial's rationale and observations is crucial for understanding the model's evolution.
- Achieved a satisfactory level of accuracy based on the defined evaluation criteria.
