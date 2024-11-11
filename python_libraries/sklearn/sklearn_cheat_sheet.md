# Scikit-Learn Cheat sheet for Machine Learning

This cheat sheet covers essential scikit-learn operations for building and evaluating machine learning models.

---

## Table of Contents

- [Introduction](#introduction)
- [General Workflow](#general-workflow)
- [Data Preprocessing](#data-preprocessing)
- [Supervised Learning](#supervised-learning)
- [Unsupervised Learning](#unsupervised-learning)
- [Model Evaluation and Selection](#model-evaluation-and-selection)
- [Hyperparameter Tuning](#hyperparameter-tuning)
- [Pipelines](#pipelines)
- [Feature Engineering](#feature-engineering)
- [Saving and Loading Models](#saving-and-loading-models)
- [Additional Resources](#additional-resources)

---

## Introduction

Scikit-Learn provides tools for every stage of the machine learning process. This cheat sheet will guide you through the essential steps and functions.

---

## General Workflow

1. **Import Libraries**

   ```python
   import numpy as np
   import pandas as pd
   from sklearn import datasets
   from sklearn.model_selection import train_test_split
   from sklearn.preprocessing import StandardScaler
   from sklearn.linear_model import LogisticRegression
   from sklearn.metrics import accuracy_score
   ```

2. **Load and Explore Data**

   ```python
   data = datasets.load_breast_cancer()
   X = data.data
   y = data.target
   ```

3. **Split Data**

   ```python
   X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, random_state=42)
   ```

4. **Preprocess Data**

   ```python
   scaler = StandardScaler()
   X_train_scaled = scaler.fit_transform(X_train)
   X_test_scaled = scaler.transform(X_test)
   ```

5. **Train Model**

   ```python
   model = LogisticRegression()
   model.fit(X_train_scaled, y_train)
   ```

6. **Make Predictions**

   ```python
   y_pred = model.predict(X_test_scaled)
   ```

7. **Evaluate Model**

   ```python
   accuracy = accuracy_score(y_test, y_pred)
   print(f'Accuracy: {accuracy:.2f}')
   ```

---

## Data Preprocessing

### Handling Missing Values

- **Imputation**

  ```python
  from sklearn.impute import SimpleImputer

  imputer = SimpleImputer(strategy='mean')
  X_imputed = imputer.fit_transform(X)
  ```

### Encoding Categorical Variables

- **Label Encoding**

  ```python
  from sklearn.preprocessing import LabelEncoder

  le = LabelEncoder()
  y_encoded = le.fit_transform(y)
  ```

- **One-Hot Encoding**

  ```python
  from sklearn.preprocessing import OneHotEncoder

  ohe = OneHotEncoder(sparse=False)
  X_encoded = ohe.fit_transform(X_categorical)
  ```

### Feature Scaling

- **Standardization**

  ```python
  from sklearn.preprocessing import StandardScaler

  scaler = StandardScaler()
  X_scaled = scaler.fit_transform(X)
  ```

- **Normalization**

  ```python
  from sklearn.preprocessing import MinMaxScaler

  scaler = MinMaxScaler()
  X_normalized = scaler.fit_transform(X)
  ```

---

## Supervised Learning

### Classification Algorithms

- **Logistic Regression**

  ```python
  from sklearn.linear_model import LogisticRegression

  model = LogisticRegression()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

- **Support Vector Machine**

  ```python
  from sklearn.svm import SVC

  model = SVC()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

- **Decision Tree**

  ```python
  from sklearn.tree import DecisionTreeClassifier

  model = DecisionTreeClassifier()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

- **Random Forest**

  ```python
  from sklearn.ensemble import RandomForestClassifier

  model = RandomForestClassifier()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

### Regression Algorithms

- **Linear Regression**

  ```python
  from sklearn.linear_model import LinearRegression

  model = LinearRegression()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

- **Decision Tree Regressor**

  ```python
  from sklearn.tree import DecisionTreeRegressor

  model = DecisionTreeRegressor()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

- **Random Forest Regressor**

  ```python
  from sklearn.ensemble import RandomForestRegressor

  model = RandomForestRegressor()
  model.fit(X_train, y_train)
  y_pred = model.predict(X_test)
  ```

---

## Unsupervised Learning

### Clustering Algorithms

- **K-Means Clustering**

  ```python
  from sklearn.cluster import KMeans

  kmeans = KMeans(n_clusters=3)
  kmeans.fit(X)
  labels = kmeans.labels_
  ```

- **Hierarchical Clustering**

  ```python
  from sklearn.cluster import AgglomerativeClustering

  clustering = AgglomerativeClustering(n_clusters=3)
  labels = clustering.fit_predict(X)
  ```

### Dimensionality Reduction

- **Principal Component Analysis (PCA)**

  ```python
  from sklearn.decomposition import PCA

  pca = PCA(n_components=2)
  X_pca = pca.fit_transform(X)
  ```

- **t-SNE**

  ```python
  from sklearn.manifold import TSNE

  tsne = TSNE(n_components=2)
  X_tsne = tsne.fit_transform(X)
  ```

---

## Model Evaluation and Selection

### Classification Metrics

- **Accuracy Score**

  ```python
  from sklearn.metrics import accuracy_score

  accuracy = accuracy_score(y_test, y_pred)
  ```

- **Confusion Matrix**

  ```python
  from sklearn.metrics import confusion_matrix

  cm = confusion_matrix(y_test, y_pred)
  ```

- **Classification Report**

  ```python
  from sklearn.metrics import classification_report

  report = classification_report(y_test, y_pred)
  print(report)
  ```

- **ROC Curve and AUC**

  ```python
  from sklearn.metrics import roc_curve, auc

  fpr, tpr, thresholds = roc_curve(y_test, y_scores)
  roc_auc = auc(fpr, tpr)
  ```

### Regression Metrics

- **Mean Squared Error (MSE)**

  ```python
  from sklearn.metrics import mean_squared_error

  mse = mean_squared_error(y_test, y_pred)
  ```

- **Mean Absolute Error (MAE)**

  ```python
  from sklearn.metrics import mean_absolute_error

  mae = mean_absolute_error(y_test, y_pred)
  ```

- **R² Score**

  ```python
  from sklearn.metrics import r2_score

  r2 = r2_score(y_test, y_pred)
  ```

---

## Hyperparameter Tuning

### Grid Search

- **GridSearchCV**

  ```python
  from sklearn.model_selection import GridSearchCV

  param_grid = {'n_neighbors': [3, 5, 7]}
  grid_search = GridSearchCV(estimator=KNeighborsClassifier(), param_grid=param_grid, cv=5)
  grid_search.fit(X_train, y_train)
  best_model = grid_search.best_estimator_
  ```

### Randomized Search

- **RandomizedSearchCV**

  ```python
  from sklearn.model_selection import RandomizedSearchCV

  param_distributions = {'n_estimators': [50, 100, 200], 'max_depth': [None, 10, 20]}
  random_search = RandomizedSearchCV(estimator=RandomForestClassifier(), param_distributions=param_distributions, n_iter=10, cv=5)
  random_search.fit(X_train, y_train)
  best_model = random_search.best_estimator_
  ```

---

## Pipelines

### Creating a Pipeline

- **Pipeline Example**

  ```python
  from sklearn.pipeline import Pipeline
  from sklearn.preprocessing import StandardScaler
  from sklearn.svm import SVC

  pipeline = Pipeline([
      ('scaler', StandardScaler()),
      ('svc', SVC())
  ])

  pipeline.fit(X_train, y_train)
  y_pred = pipeline.predict(X_test)
  ```

### Column Transformer

- **Handling Different Data Types**

  ```python
  from sklearn.compose import ColumnTransformer
  from sklearn.preprocessing import OneHotEncoder

  numeric_features = ['age', 'income']
  numeric_transformer = StandardScaler()

  categorical_features = ['gender', 'city']
  categorical_transformer = OneHotEncoder(handle_unknown='ignore')

  preprocessor = ColumnTransformer(
      transformers=[
          ('num', numeric_transformer, numeric_features),
          ('cat', categorical_transformer, categorical_features)
      ])

  from sklearn.pipeline import Pipeline
  pipeline = Pipeline([
      ('preprocessor', preprocessor),
      ('classifier', LogisticRegression())
  ])

  pipeline.fit(X_train, y_train)
  y_pred = pipeline.predict(X_test)
  ```

---

## Feature Engineering

### Feature Selection

- **Univariate Feature Selection**

  ```python
  from sklearn.feature_selection import SelectKBest, chi2

  selector = SelectKBest(chi2, k=10)
  X_new = selector.fit_transform(X, y)
  ```

- **Recursive Feature Elimination**

  ```python
  from sklearn.feature_selection import RFE
  from sklearn.linear_model import LogisticRegression

  model = LogisticRegression()
  rfe = RFE(model, n_features_to_select=10)
  X_rfe = rfe.fit_transform(X, y)
  ```

### Generating Polynomial Features

- **Polynomial Features**

  ```python
  from sklearn.preprocessing import PolynomialFeatures

  poly = PolynomialFeatures(degree=2)
  X_poly = poly.fit_transform(X)
  ```

---

## Saving and Loading Models

### Using Joblib

- **Save Model**

  ```python
  import joblib

  joblib.dump(model, 'model.joblib')
  ```

- **Load Model**

  ```python
  model = joblib.load('model.joblib')
  ```

### Using Pickle

- **Save Model**

  ```python
  import pickle

  with open('model.pkl', 'wb') as file:
      pickle.dump(model, file)
  ```

- **Load Model**

  ```python
  with open('model.pkl', 'rb') as file:
      model = pickle.load(file)
  ```

---

## Additional Resources

- [Scikit-Learn Official Documentation](https://scikit-learn.org/stable/)
- [Scikit-Learn Tutorials](https://scikit-learn.org/stable/tutorial/index.html)
- [Machine Learning with Scikit-Learn](https://www.datacamp.com/community/tutorials/machine-learning-python)
- [Scikit-Learn API Reference](https://scikit-learn.org/stable/modules/classes.html)
- [Scikit-Learn Cheat Sheet by DataCamp](https://www.datacamp.com/cheat-sheet/scikit-learn-cheat-sheet-classification-and-regression-in-python)

---