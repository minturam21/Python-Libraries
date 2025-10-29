
# 🐍 Seaborn Complete Notes for Data Science

---

## 📘 1. Introduction to Seaborn

### What is Seaborn?
Seaborn is a Python **data visualization library** based on **Matplotlib**. It provides a **high-level interface** for creating **attractive and informative statistical graphics**. It is especially useful for **exploratory data analysis (EDA)** in data science.

### Why Seaborn?
- Simpler syntax than Matplotlib
- Built-in dataset support
- Integrated with pandas DataFrames
- Attractive default color themes

### Installation
```bash
pip install seaborn
```

### Importing Seaborn
```python
import seaborn as sns
import matplotlib.pyplot as plt
```

### Loading Built-in Datasets
```python
df = sns.load_dataset("tips")
print(df.head())
```

---

## 🎨 2. Understanding Seaborn Themes & Styles

### Setting Style
```python
sns.set_style("darkgrid")
sns.set_style("whitegrid")
sns.set_style("ticks")
sns.set_style("dark")
```

### Color Palettes
```python
sns.color_palette("husl")
sns.color_palette("coolwarm")
sns.color_palette("rocket")
```

### Context
Adjust the size and scaling of elements.
```python
sns.set_context("notebook")
sns.set_context("talk")
sns.set_context("paper")
sns.set_context("poster")
```

### Adjusting Figure Size
```python
plt.figure(figsize=(10, 6))
```

---

## 📊 3. Basic Plot Types

### Univariate Plots
- `sns.histplot(data, x='column')`
- `sns.kdeplot(data, x='column')`
- `sns.boxplot(data=df, x='column')`
- `sns.violinplot(data=df, x='column')`
- `sns.stripplot(data=df, x='category', y='value')`

### Bivariate Plots
- `sns.scatterplot(x, y, data=df)`
- `sns.lineplot(x, y, data=df)`
- `sns.regplot(x, y, data=df)`
- `sns.lmplot(x, y, data=df)`

---

## 📈 4. Multivariate Data Visualization

- `sns.pairplot(df)` – pairwise relationships
- `sns.jointplot(x, y, data=df)` – combination of scatter & histograms
- `sns.heatmap(df.corr(), annot=True, cmap='coolwarm')`
- `sns.catplot(x, y, hue, data=df, kind='box')`

---

## 📚 5. Working with Categorical Data

- `sns.countplot(x='column', data=df)` – counts of each category
- `sns.barplot(x='category', y='value', data=df)` – mean + confidence interval
- `sns.pointplot(x='category', y='value', data=df)` – line between category averages

### Ordering Categories
```python
sns.barplot(x='category', y='value', data=df, order=['A','B','C'])
```

---

## ⚙️ 6. Advanced Customization

- Changing colors: `palette='rocket'`
- Add title: `plt.title('My Plot')`
- Add labels: `plt.xlabel('X-axis'); plt.ylabel('Y-axis')`
- Control transparency: `alpha=0.7`
- Use markers in lineplots: `markers=True`

---

## 📉 7. Statistical Relationships

- `sns.lmplot(x, y, data=df)` – linear regression
- `sns.lmplot(x, y, hue='category', data=df)` – multiple regressions
- `sns.jointplot(x, y, kind='hex', data=df)` – density visualization

---

## 🔥 8. Heatmaps and Correlations

### Correlation Matrix
```python
corr = df.corr()
sns.heatmap(corr, annot=True, cmap='coolwarm', linewidths=0.5)
plt.title("Correlation Heatmap")
```

### Diverging Color Palettes
```python
sns.heatmap(corr, cmap='RdBu_r', center=0)
```

---

## 🧩 9. Grid and Multi-Plot Functions

- `sns.FacetGrid(df, col='gender')`
- `sns.PairGrid(df).map_diag(sns.histplot).map_offdiag(sns.scatterplot)`
- `sns.JointGrid(x='x', y='y', data=df)`

---

## 📙 10. Seaborn with Pandas and NumPy

- Works directly with pandas DataFrames
- Handles NaN values automatically (but can drop missing data manually)
- Combine with `groupby` for summarized visuals

Example:
```python
sns.barplot(x='day', y='total_bill', hue='sex', data=df, estimator=sum)
```

---

## 🔍 11. Seaborn for EDA (Exploratory Data Analysis)

EDA aims to understand data before applying machine learning.

- Distribution plots to see spread
- Boxplots to detect outliers
- Heatmaps to identify correlations
- Pairplots for relationship overview

Example:
```python
sns.pairplot(df, hue='species')
```

---

## 🎯 12. Seaborn Integration with Matplotlib

```python
sns.boxplot(x='day', y='total_bill', data=df)
plt.title('Total Bill by Day')
plt.xlabel('Day of Week')
plt.ylabel('Total Bill ($)')
plt.savefig("plot.png")
plt.show()
```

---

## 💼 13. Project Practice

### Titanic Dataset
Visualize survival rate by gender and class.

### Tips Dataset
Explore how total bill varies by day, gender, and time.

### Iris Dataset
Compare sepal/petal dimensions across species.

### Custom Dataset
Perform full EDA and create a visualization report.

---

## 🧠 14. Advanced Topics

- Customizing dark/light themes
- `sns.clustermap()` – hierarchical heatmaps
- Visualizing feature importance in ML models
- Combining Seaborn with Plotly for interactive dashboards

---

## 🧩 15. Mini Projects

1. Titanic Survival Analysis  
2. Restaurant Tips Exploration  
3. Iris Dataset Visualization  
4. Kaggle Dataset EDA Report  

---

## 🏁 Summary

Seaborn is a powerful tool for data visualization that simplifies the process of understanding complex datasets. By mastering Seaborn, data scientists can create visuals that communicate patterns, correlations, and insights clearly and efficiently.
