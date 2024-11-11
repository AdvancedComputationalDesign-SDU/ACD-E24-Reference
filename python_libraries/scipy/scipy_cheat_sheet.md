# SciPy Cheat sheet for Scientific Computing

This cheat sheet covers essential SciPy functions for performing mathematical, scientific, and engineering computations in data science and machine learning applications.

---

## Table of Contents

- [Importing SciPy Modules](#importing-scipy-modules)
- [Optimization](#optimization)
- [Integration](#integration)
- [Interpolation](#interpolation)
- [Linear Algebra](#linear-algebra)
- [Statistics](#statistics)
- [Signal Processing](#signal-processing)
- [Sparse Matrices](#sparse-matrices)
- [Additional Resources](#additional-resources)

---

## Importing SciPy Modules

SciPy is organized into subpackages covering different scientific computing domains.

```python
from scipy import optimize       # Optimization
from scipy import integrate      # Integration
from scipy import interpolate    # Interpolation
from scipy import linalg         # Linear Algebra
from scipy import stats          # Statistics
from scipy import signal         # Signal Processing
from scipy import sparse         # Sparse Matrices
```

---

## Optimization

### Finding Minimum of Functions

- **Scalar Function Minimization**

  ```python
  result = optimize.minimize_scalar(function)
  ```

- **Multivariate Function Minimization**

  ```python
  result = optimize.minimize(function, initial_guess, method='BFGS')
  ```

### Root Finding

- **Scalar Root Finding**

  ```python
  root = optimize.root_scalar(function, bracket=[a, b], method='brentq')
  ```

- **Multivariate Root Finding**

  ```python
  root = optimize.root(function, initial_guess, method='hybr')
  ```

---

## Integration

### Numerical Integration

- **Definite Integrals**

  ```python
  result, error = integrate.quad(function, a, b)
  ```

- **Multiple Integrals**

  ```python
  result, error = integrate.dblquad(func, a, b, gfun, hfun)
  ```

### Solving Differential Equations

- **Ordinary Differential Equations (ODEs)**

  ```python
  from scipy.integrate import solve_ivp

  def model(t, y):
      return -2 * y + t

  solution = solve_ivp(model, [t0, tf], y0)
  ```

---

## Interpolation

### 1D Interpolation

- **Linear Interpolation**

  ```python
  from scipy.interpolate import interp1d

  f = interp1d(x_points, y_points, kind='linear')
  y_new = f(x_new)
  ```

### Spline Interpolation

- **Univariate Spline**

  ```python
  from scipy.interpolate import UnivariateSpline

  spline = UnivariateSpline(x_points, y_points)
  y_new = spline(x_new)
  ```

---

## Linear Algebra

### Solving Linear Systems

- **Solve Ax = b**

  ```python
  x = linalg.solve(A, b)
  ```

### Matrix Decompositions

- **Eigenvalues and Eigenvectors**

  ```python
  eigenvalues, eigenvectors = linalg.eig(A)
  ```

- **Singular Value Decomposition (SVD)**

  ```python
  U, s, Vh = linalg.svd(A)
  ```

- **Cholesky Decomposition**

  ```python
  L = linalg.cholesky(A)
  ```

---

## Statistics

### Descriptive Statistics

- **Summary Statistics**

  ```python
  mean = np.mean(data)
  median = np.median(data)
  variance = np.var(data)
  ```

### Probability Distributions

- **Normal Distribution**

  ```python
  from scipy.stats import norm

  # PDF
  pdf = norm.pdf(x, loc=mean, scale=std_dev)

  # CDF
  cdf = norm.cdf(x, loc=mean, scale=std_dev)
  ```

- **Sampling from Distributions**

  ```python
  samples = norm.rvs(loc=mean, scale=std_dev, size=1000)
  ```

### Hypothesis Testing

- **T-Test**

  ```python
  from scipy.stats import ttest_ind

  stat, p_value = ttest_ind(sample1, sample2)
  ```

- **Chi-Squared Test**

  ```python
  from scipy.stats import chi2_contingency

  stat, p_value, dof, expected = chi2_contingency(table)
  ```

---

## Signal Processing

### Filtering

- **Design a Butterworth Filter**

  ```python
  b, a = signal.butter(N=4, Wn=0.25)
  filtered_signal = signal.filtfilt(b, a, data)
  ```

### Spectral Analysis

- **Compute FFT**

  ```python
  from scipy.fft import fft

  fft_values = fft(data)
  ```

### Convolution and Correlation

- **Convolution**

  ```python
  convolved = signal.convolve(data1, data2)
  ```

- **Correlation**

  ```python
  correlated = signal.correlate(data1, data2)
  ```

---

## Sparse Matrices

### Creating Sparse Matrices

- **CSR Matrix**

  ```python
  from scipy.sparse import csr_matrix

  sparse_matrix = csr_matrix((data, (row_indices, col_indices)), shape=(m, n))
  ```

### Sparse Matrix Operations

- **Matrix Multiplication**

  ```python
  result = sparse_matrix.dot(other_matrix)
  ```

- **Converting to Dense**

  ```python
  dense_matrix = sparse_matrix.toarray()
  ```

---

## Additional Resources

- [SciPy Tutorial](https://docs.scipy.org/doc/scipy/reference/tutorial/)
- [SciPy Lecture Notes](https://scipy-lectures.org/)
- [Scientific Python Cheat sheet](https://scipy-lectures.org/intro/summary.html)
- [SciPy Recipes](https://scipy-cookbook.readthedocs.io/)

---

*By mastering these SciPy functions, you'll enhance your ability to perform advanced scientific computations necessary for complex data analysis and machine learning tasks.*

---