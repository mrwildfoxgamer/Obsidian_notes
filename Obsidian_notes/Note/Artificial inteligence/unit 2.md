### What is Machine Learning?

ML is a subset of AI that allows machines to learn from examples and experience without being explicitly programmed. It uses statistical techniques and algorithms to recognize patterns in data, make predictions, classify information, and automate decision-making.

**Tom Mitchell's Definition (1997):** _"A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves with experience."_

- **Task (T):** The problem being solved (e.g., spam classification, price prediction)
- **Experience (E):** Historical data used for learning
- **Performance (P):** A measurable metric (e.g., accuracy, error rate)

### Data in Machine Learning

Data = facts, observations, or measurements used to train, test, and evaluate ML models.

**Types of Data:**

_By Structure:_

- **Structured** – organized in tables/schemas (e.g., SQL databases, spreadsheets) → used in fraud detection, business intelligence
- **Unstructured** – no fixed format (e.g., images, videos, emails) → used in sentiment analysis, speech recognition
- **Semi-structured** – partial organization with tags/metadata (e.g., JSON, XML) → used in document classification, web scraping

_By Representation:_

- **Numerical (Quantitative):**
    - Discrete – countable (e.g., number of clicks)
    - Continuous – measurable with infinite range (e.g., temperature)
- **Categorical (Qualitative):**
    - Nominal – no order (e.g., gender, car brand)
    - Ordinal – ranked order (e.g., satisfaction levels)

_By Labelling:_

- **Labeled** – inputs paired with outputs → used in classification, regression, NLP
- **Unlabeled** – no predefined outputs → used in clustering, anomaly detection

**Data-Information-Knowledge Pyramid:** Data (raw facts) → Information (contextualized/organized data) → Knowledge (insight, experience, understanding).

### Types of Learning

**1. Supervised Learning**

- Uses labeled datasets to train models to find patterns/relationships
- Learns the mapping between features and target output
- **Types:** Classification and Regression
- Uses an error signal (difference between desired output D and actual output Y) to adjust the neural network

**2. Unsupervised Learning**

- Works with unlabeled data; no feedback on correctness
- The network itself discovers patterns and relationships
- **Approaches:** Clustering, Association, Dimensionality Reduction

### Learning Systems

A structured framework enabling machines to learn from data with minimal human guidance.

**Components:**

1. **Data Input** – quality/volume of data affects performance
2. **Learning Algorithm** – e.g., Linear Regression, Neural Networks, Decision Trees
3. **Model Output** – predictions/classifications, improved over training cycles
4. **Feedback Mechanism** – compares predictions to actual results to reduce error

### Steps in Developing an ML System

1. **Defining Problems & Objectives** – identify task type (classification, regression, clustering) and metrics (accuracy, precision, recall, F1)
2. **Data Collection & Preparation** – gathering from databases/sensors/web/surveys; preprocessing (cleaning, handling missing values, normalization/encoding)
3. **Choosing Training Experience** – supervised (labeled data), unsupervised (pattern discovery), or reinforcement learning (trial and error)
4. **Selecting Target Function** – defines input-output relationship (e.g., loan approval → accept/reject)
5. **Choosing Representation for Target Function** – Decision Trees (hierarchical tasks), Neural Networks (non-linear/complex data), Linear Models (interpretable problems)
6. **Selecting Function Approximation Algorithm** – e.g., Gradient Descent, Backpropagation, Least Squares — searches hypothesis space and minimizes error
7. **Training the Model** – iteratively adjusting parameters; watching for overfitting
8. **Evaluating Model Performance** – hold-out validation, k-fold cross-validation; metrics like accuracy, precision, recall, F1, MSE
9. **Iterative Refinement** – repeated trial-and-improvement cycle to boost accuracy/robustness

### ML Tasks Overview

- **Supervised Learning** → Regression (predicts continuous values, e.g., house prices) & Classification (predicts discrete categories, e.g., spam detection, disease diagnosis)
- **Unsupervised Learning** → Clustering (groups similar data, e.g., customer segmentation, anomaly detection)

### Regression

Models the relationship between a dependent variable and one or more independent variables for prediction.

**Types:**

- **Simple/Univariate Linear Regression** – one independent variable
- **Multiple/Multivariate Linear Regression** – more than one independent variable
- **Non-linear Regression** – for non-linear relationships

**Linear Regression Formula:** Y = mX + b

- Y = dependent variable, X = independent variable, m = slope, b = intercept

**Evaluation Metrics for Regression:**

- **MAE (Mean Absolute Error)** – average of absolute differences between predicted and true values
- **MSE (Mean Squared Error)** – average of squared differences between actual and predicted values
- **RMSE (Root Mean Squared Error)** – square root of MSE
- **R² (Coefficient of Determination)** – best possible score is 1.0; can be negative; measures how well predictions approximate actual values

### Classification

A supervised learning technique used to identify the category of new observations based on training data. Classes are called targets/labels/categories.

**Types of Classifiers:**

- **Binary Classifier** – two outcomes (e.g., spam/not spam, male/female)
- **Multi-class Classifier** – more than two outcomes (e.g., crop types, music genres)

**Confusion Matrix Concepts:**

- **True Positive (TP):** correctly predicted positive
- **True Negative (TN):** correctly predicted negative
- **False Positive (FP):** incorrectly predicted positive (Type I error)
- **False Negative (FN):** incorrectly predicted negative (Type II error)

**Evaluation Measures:**

- **Accuracy** = (TP+TN) / (TP+TN+FP+FN)
- **Recall (TPR)** = TP / (TP+FN)
- **Precision** = TP / (TP+FP)
- **F1 Score** = 2×(Recall×Precision) / (Recall+Precision)
- **Confusion Matrix** – an N×N table summarizing classification accuracy, where N = number of classes

### Clustering

The process of grouping objects so that items within a cluster are more similar to each other than to items in other clusters. It's an iterative discovery process requiring domain expertise.

**Evaluation Factors:**

1. **Clustering Tendency**
2. **Number of Clusters (k)** – critical parameter (e.g., in K-means); too high → over-segmentation; too low → poor grouping. Optimal k found via the **Elbow Method**
3. **Clustering Quality** – measured via **Silhouette Score**
    - Combines **Cohesion** (intra-cluster distance, mean = a) and **Separation** (inter-cluster distance, mean = b)
    - Formula: **(b−a) / max(b,a)**
    - Range: [-1, 1]. Closer to +1 = well-separated clusters; 0 = on cluster boundary; negative = likely misassigned sample