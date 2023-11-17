# Reddit Fake Post Detection

This project aims to detect fake posts on Reddit using natural language processing (NLP) and machine learning (ML) techniques. Two different implementations have been explored to achieve this goal, each with its unique preprocessing and modeling approaches.

## Implementation 1

### Text Cleaning

- Remove special characters
- Remove user handles/mentions
- Remove hashtags
- Remove stopwords/punctuation
- Convert to lowercase
- Remove multiple spaces
- Remove numbers
- Remove emojis
- Remove non-ASCII characters
- Remove currency symbols
- Remove emails/dates
- Remove HTML tags/URLs

### Noise Scan
Utilized the `TextFrame` class from the `nt` library to perform a noise scan on the training data.

### Train Preprocessing
Applied a series of text cleaning steps using the [nfx library](https://pypi.org/project/nfx/), including removing user handles, hashtags, URLs, HTML tags, dates, emails, non-ASCII characters, stopwords, punctuation, special characters, emojis, and numbers. Additionally, the text was converted to lowercase and lemmatized.

### Test Preprocessing
Performed similar preprocessing steps on the testing data.

### Train-Validation Split
Split the cleaned training data into training and validation sets for model evaluation.

### Models

#### Trial 1: XGBoost
- Hyperparameter tuning: Bayesian Search with Validation set
- Analyzer: Word
- Results: The score obtained from this method was not satisfactory.

#### Trial 1.2: XGBoost
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Character
- Results: The score further decreased.

#### Trial 2: Logistic Regression
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Word
- Results: The score improved compared to the first trial.

#### Trial 2.2: Logistic Regression
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Character
- Results: The score significantly decreased, suggesting character-level analysis may not be suitable for NLP text.

#### Trial 3: Decision Tree
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Word
- Results: The score did not show improvement.

#### Trial 3.2: Decision Tree
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Character
- Results: Similar to Trial 2.2, the score worsened.

#### Trial 4: SVM
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Word
- Results: The SVM model took a long time and crashed, preventing a conclusive result.
## Implementation 2

### Text Cleaning
Implemented an alternative preprocessing method using the `SnowballStemmer` and removing German stopwords.

### Train Preprocessing
Applied the new preprocessing technique to the training data.

### Test Preprocessing
Applied the same preprocessing to the testing data.

### Models

#### Trial 4: XGBoost
- Hyperparameter tuning: Bayesian Search with Validation set
- Analyzer: Word
- Results: The new preprocessing method decreased the score compared to the first preprocessing technique.

#### Trial 5: Logistic Regression
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Word
- Results: The score improved compared to logistic regression with the first preprocessing technique.

#### Trial 6: Decision Tree
- Hyperparameter tuning: Random Search with Validation set
- Analyzer: Word
- Results: The score remained similar to previous trials.
