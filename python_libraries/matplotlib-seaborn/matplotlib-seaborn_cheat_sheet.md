# Matplotlib and Seaborn Cheat sheet for Data Visualization

This cheat sheet covers essential Matplotlib and Seaborn functions for creating a wide variety of plots and customizing them for data analysis and machine learning applications.

---

## Table of Contents

- [Matplotlib Basics](#matplotlib-basics)
- [Plot Types in Matplotlib](#plot-types-in-matplotlib)
- [Customization in Matplotlib](#customization-in-matplotlib)
- [Subplots and Figures](#subplots-and-figures)
- [Seaborn Basics](#seaborn-basics)
- [Plot Types in Seaborn](#plot-types-in-seaborn)
- [Customization in Seaborn](#customization-in-seaborn)
- [Advanced Visualization Techniques](#advanced-visualization-techniques)
- [Additional Resources](#additional-resources)

---

## Matplotlib Basics

### Importing Matplotlib

```python
import matplotlib.pyplot as plt
```

### Basic Plotting

- **Line Plot**

  ```python
  plt.plot(x, y)
  plt.show()
  ```

- **Scatter Plot**

  ```python
  plt.scatter(x, y)
  plt.show()
  ```

### Labels and Titles

```python
plt.xlabel('X-axis Label')
plt.ylabel('Y-axis Label')
plt.title('Plot Title')
```

### Saving Figures

```python
plt.savefig('figure.png', dpi=300)
```

---

## Plot Types in Matplotlib

### Bar Chart

```python
plt.bar(categories, values)
```

### Histogram

```python
plt.hist(data, bins=20)
```

### Pie Chart

```python
plt.pie(sizes, labels=labels, autopct='%1.1f%%')
```

### Box Plot

```python
plt.boxplot(data)
```

---

## Customization in Matplotlib

### Colors and Styles

- **Set Color**

  ```python
  plt.plot(x, y, color='red')
  ```

- **Line Style**

  ```python
  plt.plot(x, y, linestyle='--')
  ```

- **Markers**

  ```python
  plt.plot(x, y, marker='o')
  ```

### Legends

```python
plt.legend(['Series 1', 'Series 2'])
```

### Axes Limits

```python
plt.xlim(min_value, max_value)
plt.ylim(min_value, max_value)
```

### Grid

```python
plt.grid(True)
```

---

## Subplots and Figures

### Creating Subplots

```python
fig, ax = plt.subplots(nrows=2, ncols=2)
ax[0, 0].plot(x, y)
ax[0, 1].bar(categories, values)
ax[1, 0].hist(data)
ax[1, 1].scatter(x, y)
plt.tight_layout()
```

### Figure Size

```python
plt.figure(figsize=(10, 6))
```

---

## Seaborn Basics

### Importing Seaborn

```python
import seaborn as sns
```

### Setting Style

```python
sns.set(style='whitegrid')
```

### Loading Example Datasets

```python
tips = sns.load_dataset('tips')
```

---

## Plot Types in Seaborn

### Scatter Plot with Regression Line

```python
sns.regplot(x='total_bill', y='tip', data=tips)
```

### Categorical Plots

- **Box Plot**

  ```python
  sns.boxplot(x='day', y='total_bill', data=tips)
  ```

- **Violin Plot**

  ```python
  sns.violinplot(x='day', y='total_bill', data=tips)
  ```

- **Bar Plot**

  ```python
  sns.barplot(x='day', y='total_bill', data=tips)
  ```

### Distribution Plots

- **Histogram and KDE**

  ```python
  sns.histplot(data['column'], kde=True)
  ```

- **Joint Distribution**

  ```python
  sns.jointplot(x='total_bill', y='tip', data=tips, kind='scatter')
  ```

### Heatmaps

```python
corr = data.corr()
sns.heatmap(corr, annot=True, cmap='coolwarm')
```

---

## Customization in Seaborn

### Color Palettes

```python
sns.set_palette('pastel')
```

### Context Settings

```python
sns.set_context('talk')
```

### Facet Grids

```python
g = sns.FacetGrid(tips, col='time', row='smoker')
g.map(sns.scatterplot, 'total_bill', 'tip')
```

---

## Advanced Visualization Techniques

### Pair Plot

```python
sns.pairplot(data)
```

### Swarm Plot

```python
sns.swarmplot(x='day', y='total_bill', data=tips)
```

### Count Plot

```python
sns.countplot(x='day', data=tips)
```

---

## Additional Resources

- [Matplotlib Gallery](https://matplotlib.org/stable/gallery/index.html)
- [Seaborn Gallery](https://seaborn.pydata.org/examples/index.html)
- [Python Graph Gallery](https://www.python-graph-gallery.com/)

---