# Pandas Cheat sheet for Data Science and Machine Learning

This cheat sheet covers essential pandas operations for data manipulation, analysis, and preparation in data science and machine learning applications.

---

## Table of Contents

- [Introduction](#introduction)
- [Data Structures](#data-structures)
- [Data Ingestion](#data-ingestion)
- [Exploring DataFrames](#exploring-dataframes)
- [Data Selection and Indexing](#data-selection-and-indexing)
- [Handling Missing Data](#handling-missing-data)
- [Data Cleaning and Transformation](#data-cleaning-and-transformation)
- [Merging, Joining, and Concatenation](#merging-joining-and-concatenation)
- [Grouping and Aggregation](#grouping-and-aggregation)
- [Pivot Tables and Reshaping](#pivot-tables-and-reshaping)
- [Working with Dates and Times](#working-with-dates-and-times)
- [Categorical Data](#categorical-data)
- [Data Visualization with Pandas](#data-visualization-with-pandas)
- [Exporting Data](#exporting-data)
- [Performance Tips](#performance-tips)
- [Additional Resources](#additional-resources)

---

## Introduction

Pandas is a powerful Python library for data manipulation and analysis, built on top of NumPy. It provides data structures like `DataFrame` and `Series` for working with structured data, essential for data science and machine learning tasks.

---

## Data Structures

### Series

A one-dimensional labeled array capable of holding any data type.

```python
import pandas as pd

# Create a Series
s = pd.Series([1, 3, 5, 7, 9], index=['a', 'b', 'c', 'd', 'e'])
```

### DataFrame

A two-dimensional labeled data structure with columns of potentially different types.

```python
# Create a DataFrame from a dictionary
data = {'Name': ['Alice', 'Bob', 'Charlie', 'David'],
        'Age': [25, 30, 35, 40],
        'Salary': [50000, 60000, 70000, 80000]}
df = pd.DataFrame(data)
```

---

## Data Ingestion

### Reading Data from Various Sources

- **CSV File**

  ```python
  df = pd.read_csv('data/file_name.csv')
  ```

- **Excel File**

  ```python
  df = pd.read_excel('data/file_name.xlsx', sheet_name='Sheet1')
  ```

- **JSON File**

  ```python
  df = pd.read_json('data/file_name.json')
  ```

- **SQL Database**

  ```python
  import sqlite3

  conn = sqlite3.connect('data/database.db')
  df = pd.read_sql_query('SELECT * FROM table_name', conn)
  ```

- **HTML Tables**

  ```python
  tables = pd.read_html('https://www.example.com')
  df = tables[0]  # First table on the page
  ```

---

## Exploring DataFrames

### Basic Information

- **View DataFrame Shape**

  ```python
  df.shape  # (rows, columns)
  ```

- **Display First Few Rows**

  ```python
  df.head(5)
  ```

- **Display Last Few Rows**

  ```python
  df.tail(5)
  ```

- **Data Types of Columns**

  ```python
  df.dtypes
  ```

- **Summary of the DataFrame**

  ```python
  df.info()
  ```

- **Statistical Summary**

  ```python
  df.describe(include='all')
  ```

---

## Data Selection and Indexing

### Selecting Data

- **Select Column**

  ```python
  df['column_name']
  ```

- **Select Multiple Columns**

  ```python
  df[['column1', 'column2']]
  ```

- **Select Rows by Label (`loc`)**

  ```python
  df.loc[row_label]
  df.loc[row_label, 'column_name']
  ```

- **Select Rows by Position (`iloc`)**

  ```python
  df.iloc[row_index]
  df.iloc[row_index, column_index]
  ```

### Conditional Selection

- **Filter Rows Based on Condition**

  ```python
  df_filtered = df[df['Age'] > 30]
  ```

- **Multiple Conditions**

  ```python
  df_filtered = df[(df['Age'] > 30) & (df['Salary'] >= 70000)]
  ```

- **isin for Multiple Values**

  ```python
  df_filtered = df[df['Name'].isin(['Alice', 'Bob'])]
  ```

---

## Handling Missing Data

### Detecting Missing Data

- **Check for Missing Values**

  ```python
  df.isnull().sum()
  ```

- **Check for Any Missing Values**

  ```python
  df.isnull().any()
  ```

### Handling Missing Data

- **Drop Rows with Missing Values**

  ```python
  df_clean = df.dropna()
  ```

- **Drop Columns with Missing Values**

  ```python
  df_clean = df.dropna(axis=1)
  ```

- **Fill Missing Values**

  ```python
  df_filled = df.fillna(value)
  df['column_name'].fillna(df['column_name'].mean(), inplace=True)
  ```

- **Forward and Backward Fill**

  ```python
  df.fillna(method='ffill', inplace=True)  # Forward Fill
  df.fillna(method='bfill', inplace=True)  # Backward Fill
  ```

---

## Data Cleaning and Transformation

### Renaming Columns

- **Rename Columns**

  ```python
  df.rename(columns={'old_name': 'new_name'}, inplace=True)
  ```

### Changing Data Types

- **Convert Data Types**

  ```python
  df['column_name'] = df['column_name'].astype('int')
  ```

- **Datetime Conversion**

  ```python
  df['date_column'] = pd.to_datetime(df['date_column'])
  ```

### Handling Duplicates

- **Find Duplicate Rows**

  ```python
  duplicates = df.duplicated()
  ```

- **Drop Duplicate Rows**

  ```python
  df.drop_duplicates(inplace=True)
  ```

### String Operations

- **String Methods**

  ```python
  df['Name'] = df['Name'].str.upper()
  df['Email'] = df['Email'].str.strip()
  ```

### Applying Functions

- **Apply Function to Column**

  ```python
  df['Salary_in_K'] = df['Salary'].apply(lambda x: x / 1000)
  ```

- **Apply Function to Rows**

  ```python
  def calculate_bonus(row):
      return row['Salary'] * 0.1 if row['Age'] > 30 else 0

  df['Bonus'] = df.apply(calculate_bonus, axis=1)
  ```

---

## Merging, Joining, and Concatenation

### Merging DataFrames

- **Merge on a Key Column**

  ```python
  merged_df = pd.merge(df_left, df_right, on='key_column', how='inner')
  ```

- **Merge on Multiple Columns**

  ```python
  merged_df = pd.merge(df1, df2, on=['key1', 'key2'], how='outer')
  ```

### Joining DataFrames

- **Join Using Index**

  ```python
  joined_df = df_left.join(df_right, how='left')
  ```

### Concatenating DataFrames

- **Concatenate Along Rows**

  ```python
  combined_df = pd.concat([df1, df2], axis=0)
  ```

- **Concatenate Along Columns**

  ```python
  combined_df = pd.concat([df1, df2], axis=1)
  ```

---

## Grouping and Aggregation

### GroupBy Operations

- **Group By Column and Aggregate**

  ```python
  df_grouped = df.groupby('Department')['Salary'].mean()
  ```

- **Group By Multiple Columns**

  ```python
  df_grouped = df.groupby(['Department', 'Gender']).agg({'Salary': ['mean', 'sum']})
  ```

### Aggregate Functions

- **Common Aggregate Functions**

  - `mean()`
  - `sum()`
  - `count()`
  - `min()`
  - `max()`
  - `median()`

- **Apply Custom Aggregate Function**

  ```python
  df_grouped = df.groupby('Department').agg({'Salary': lambda x: x.max() - x.min()})
  ```

---

## Pivot Tables and Reshaping

### Pivot Tables

- **Create a Pivot Table**

  ```python
  pivot_table = df.pivot_table(values='Salary', index='Department', columns='Gender', aggfunc='mean')
  ```

### Reshaping Data

- **Melt (Unpivot) Data**

  ```python
  melted_df = pd.melt(df, id_vars=['Department'], value_vars=['Salary', 'Bonus'], var_name='Metric', value_name='Amount')
  ```

- **Stack and Unstack**

  ```python
  stacked = df.stack()
  unstacked = df.unstack()
  ```

---

## Working with Dates and Times

### DateTime Operations

- **Convert to DateTime**

  ```python
  df['date_column'] = pd.to_datetime(df['date_column'])
  ```

- **Extract Date Components**

  ```python
  df['Year'] = df['date_column'].dt.year
  df['Month'] = df['date_column'].dt.month
  df['Day'] = df['date_column'].dt.day
  ```

- **Date Arithmetic**

  ```python
  df['Next_Month'] = df['date_column'] + pd.DateOffset(months=1)
  df['Days_Since'] = (pd.Timestamp('today') - df['date_column']).dt.days
  ```

---

## Categorical Data

### Handling Categorical Variables

- **Convert to Category Data Type**

  ```python
  df['Category'] = df['Category'].astype('category')
  ```

- **Set Category Order**

  ```python
  df['Category'] = df['Category'].cat.set_categories(['Low', 'Medium', 'High'], ordered=True)
  ```

- **One-Hot Encoding**

  ```python
  df_encoded = pd.get_dummies(df, columns=['Category'])
  ```

---

## Data Visualization with Pandas

### Basic Plotting

- **Line Plot**

  ```python
  df.plot(x='Date', y='Value')
  ```

- **Bar Plot**

  ```python
  df.groupby('Category')['Amount'].sum().plot(kind='bar')
  ```

- **Histogram**

  ```python
  df['Age'].plot(kind='hist', bins=10)
  ```

- **Box Plot**

  ```python
  df.boxplot(column='Salary', by='Department')
  ```

### Advanced Visualization

- **Scatter Matrix**

  ```python
  pd.plotting.scatter_matrix(df, figsize=(10, 10))
  ```

- **Correlation Heatmap**

  ```python
  import seaborn as sns
  import matplotlib.pyplot as plt

  corr = df.corr()
  sns.heatmap(corr, annot=True)
  plt.show()
  ```

---

## Exporting Data

- **Save DataFrame to CSV**

  ```python
  df.to_csv('data/output_file.csv', index=False)
  ```

- **Save DataFrame to Excel**

  ```python
  df.to_excel('data/output_file.xlsx', index=False)
  ```

- **Save DataFrame to JSON**

  ```python
  df.to_json('data/output_file.json', orient='records', lines=True)
  ```

---

## Performance Tips

- **Use Vectorized Operations**

  Avoid loops by using pandas built-in functions that operate on entire columns.

- **Optimize Data Types**

  Downcast numeric types to save memory.

  ```python
  df['int_column'] = pd.to_numeric(df['int_column'], downcast='integer')
  ```

- **Chunking Large Datasets**

  Read and process data in chunks.

  ```python
  chunks = pd.read_csv('large_file.csv', chunksize=10000)
  for chunk in chunks:
      process(chunk)
  ```

- **Set Index**

  Set a column as the index for faster lookups.

  ```python
  df.set_index('key_column', inplace=True)
  ```

---

## Additional Resources

- [Pandas Official Documentation](https://pandas.pydata.org/docs/)
- [10 Minutes to Pandas](https://pandas.pydata.org/docs/user_guide/10min.html)
- [Pandas Tutorial on DataCamp](https://www.datacamp.com/community/tutorials/pandas-tutorial-dataframe-python)
- [Pandas Cheat Sheet by DataCamp](https://www.datacamp.com/cheat-sheet/pandas-cheat-sheet-for-data-science-in-python)
