# NumPy Cheat sheet for Data Science and Machine Learning

This cheat sheet covers essential NumPy operations for numerical computing, data manipulation, and preparation in data science and machine learning applications.

---

## Table of Contents

- [Introduction](#introduction)
- [Creating Arrays](#creating-arrays)
- [Inspecting Arrays](#inspecting-arrays)
- [Data Types](#data-types)
- [Array Mathematics](#array-mathematics)
- [Broadcasting](#broadcasting)
- [Indexing and Slicing](#indexing-and-slicing)
- [Shape Manipulation](#shape-manipulation)
- [Stacking and Splitting Arrays](#stacking-and-splitting-arrays)
- [Statistical Functions](#statistical-functions)
- [Linear Algebra](#linear-algebra)
- [Random Number Generation](#random-number-generation)
- [Advanced Topics](#advanced-topics)
- [Integration with Pandas](#integration-with-pandas)
- [Performance Tips](#performance-tips)
- [Additional Resources](#additional-resources)

---

## Introduction

NumPy is a fundamental library for numerical computing in Python. It provides high-performance multidimensional arrays and tools for working with these arrays.

---

## Creating Arrays

### From Lists or Tuples

```python
import numpy as np

# 1D Array
array_1d = np.array([1, 2, 3, 4, 5])

# 2D Array
array_2d = np.array([[1, 2], [3, 4], [5, 6]])
```

### Special Arrays

- **Zeros**

  ```python
  zeros_array = np.zeros((rows, columns))
  ```

- **Ones**

  ```python
  ones_array = np.ones((rows, columns))
  ```

- **Constant Value**

  ```python
  full_array = np.full((rows, columns), fill_value)
  ```

- **Identity Matrix**

  ```python
  identity_matrix = np.eye(n)
  ```

- **Arange**

  ```python
  sequence_array = np.arange(start, stop, step)
  ```

- **Linspace**

  ```python
  linear_array = np.linspace(start, stop, num_elements)
  ```

---

## Inspecting Arrays

### Attributes

- **Shape of Array**

  ```python
  array.shape
  ```

- **Number of Dimensions**

  ```python
  array.ndim
  ```

- **Total Number of Elements**

  ```python
  array.size
  ```

- **Data Type**

  ```python
  array.dtype
  ```

### Viewing Data

- **First Few Elements**

  ```python
  array[:5]
  ```

- **Last Few Elements**

  ```python
  array[-5:]
  ```

---

## Data Types

### Specifying Data Types

- **Create Array with Specific Type**

  ```python
  array = np.array([1, 2, 3], dtype='float32')
  ```

- **Change Data Type**

  ```python
  array = array.astype('int64')
  ```

---

## Array Mathematics

### Element-wise Operations

- **Addition**

  ```python
  result = array1 + array2
  ```

- **Subtraction**

  ```python
  result = array1 - array2
  ```

- **Multiplication**

  ```python
  result = array1 * array2
  ```

- **Division**

  ```python
  result = array1 / array2
  ```

### Scalar Operations

- **Multiply by Scalar**

  ```python
  result = array * scalar_value
  ```

- **Add Scalar**

  ```python
  result = array + scalar_value
  ```

### Universal Functions (ufunc)

- **Square Root**

  ```python
  np.sqrt(array)
  ```

- **Exponential**

  ```python
  np.exp(array)
  ```

- **Logarithm**

  ```python
  np.log(array)
  ```

- **Trigonometric Functions**

  ```python
  np.sin(array)
  np.cos(array)
  np.tan(array)
  ```

---

## Broadcasting

NumPy allows operations on arrays of different shapes.

- **Broadcasting Example**

  ```python
  array = np.array([1, 2, 3])
  result = array + 10  # Adds 10 to each element
  ```

---

## Indexing and Slicing

### Basic Indexing

- **Access Element**

  ```python
  element = array[row_index, column_index]
  ```

- **Modify Element**

  ```python
  array[row_index, column_index] = new_value
  ```

### Slicing

- **Slice Rows and Columns**

  ```python
  sub_array = array[start_row:end_row, start_col:end_col]
  ```

- **Reverse Array**

  ```python
  reversed_array = array[::-1]
  ```

### Boolean Indexing

- **Filter Based on Condition**

  ```python
  filtered_array = array[array > value]
  ```

---

## Shape Manipulation

### Reshape Array

- **Reshape**

  ```python
  reshaped_array = array.reshape(new_shape)
  ```

- **Flatten Array**

  ```python
  flattened_array = array.flatten()
  ```

### Transpose Array

- **Transpose**

  ```python
  transposed_array = array.T
  ```

### Expand Dimensions

- **Add Dimension**

  ```python
  expanded_array = np.expand_dims(array, axis)
  ```

---

## Stacking and Splitting Arrays

### Stacking

- **Vertical Stack**

  ```python
  vstack_array = np.vstack((array1, array2))
  ```

- **Horizontal Stack**

  ```python
  hstack_array = np.hstack((array1, array2))
  ```

### Splitting

- **Split Array**

  ```python
  split_arrays = np.split(array, indices_or_sections)
  ```

---

## Statistical Functions

### Basic Statistics

- **Minimum and Maximum**

  ```python
  min_value = np.min(array)
  max_value = np.max(array)
  ```

- **Sum**

  ```python
  total_sum = np.sum(array)
  ```

- **Mean**

  ```python
  mean_value = np.mean(array)
  ```

- **Median**

  ```python
  median_value = np.median(array)
  ```

- **Standard Deviation**

  ```python
  std_dev = np.std(array)
  ```

- **Variance**

  ```python
  variance = np.var(array)
  ```

### Axis Parameter

Compute along a specific axis.

- **Sum Along Axis**

  ```python
  sum_along_axis0 = np.sum(array, axis=0)
  sum_along_axis1 = np.sum(array, axis=1)
  ```

---

## Linear Algebra

### Dot Product

- **Dot Product of Vectors**

  ```python
  dot_product = np.dot(vector1, vector2)
  ```

### Matrix Multiplication

- **Matrix Product**

  ```python
  product = np.matmul(matrix1, matrix2)
  ```

### Determinant

- **Compute Determinant**

  ```python
  determinant = np.linalg.det(matrix)
  ```

### Inverse

- **Compute Inverse**

  ```python
  inverse_matrix = np.linalg.inv(matrix)
  ```

### Eigenvalues and Eigenvectors

- **Compute Eigenvalues and Eigenvectors**

  ```python
  eigenvalues, eigenvectors = np.linalg.eig(matrix)
  ```

---

## Random Number Generation

### Random Numbers

- **Random Floats Between 0 and 1**

  ```python
  random_array = np.random.rand(rows, columns)
  ```

- **Random Integers**

  ```python
  random_ints = np.random.randint(low, high, size)
  ```

### Random Distributions

- **Normal Distribution**

  ```python
  normal_samples = np.random.normal(loc=mean, scale=std_dev, size=shape)
  ```

- **Binomial Distribution**

  ```python
  binomial_samples = np.random.binomial(n, p, size)
  ```

### Reproducibility

- **Set Seed**

  ```python
  np.random.seed(seed_value)
  ```

---

## Advanced Topics

### Vectorization

Avoid loops by using vectorized operations.

- **Example**

  ```python
  # Instead of looping
  result = [x**2 for x in array]

  # Use NumPy vectorization
  result = array ** 2
  ```

### Broadcasting Rules

Understand how arrays with different shapes are combined.

- **Example**

  ```python
  array1.shape  # (3, 1)
  array2.shape  # (1, 4)
  result = array1 + array2  # Resulting shape (3, 4)
  ```

### Memory Layout

- **Contiguous Arrays**

  ```python
  array = np.ascontiguousarray(array)
  ```

### Advanced Indexing

- **Fancy Indexing**

  ```python
  indices = [1, 3, 5]
  selected_elements = array[indices]
  ```

---

## Integration with Pandas

### Converting Between Pandas and NumPy

- **DataFrame to NumPy Array**

  ```python
  array = df.values
  ```

- **NumPy Array to DataFrame**

  ```python
  df = pd.DataFrame(array, columns=['Col1', 'Col2'])
  ```

---

## Performance Tips

- **Use Built-in Functions**

  NumPy functions are optimized in C and are faster than pure Python loops.

- **Avoid Copying Arrays**

  Use views instead of copies when possible.

- **Use Appropriate Data Types**

  Smaller data types save memory and can improve performance.

  ```python
  array = np.array([1, 2, 3], dtype='int8')
  ```

- **Use Numexpr for Complex Expressions**

  ```python
  import numexpr as ne

  result = ne.evaluate('array1 + array2 * array3')
  ```

---

## Additional Resources

- [NumPy Official Documentation](https://numpy.org/doc/)
- [NumPy User Guide](https://numpy.org/doc/stable/user/index.html)
- [NumPy Tutorial on W3Schools](https://www.w3schools.com/python/numpy/)
- [NumPy Cheat Sheet by DataCamp](https://www.datacamp.com/cheat-sheet/numpy-cheat-sheet-data-analysis-in-python)
- [NumPy Exercises](https://www.machinelearningplus.com/python/101-numpy-exercises-python/)

---