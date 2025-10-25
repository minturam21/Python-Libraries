

## 🧩 1. Introduction to Pandas

**Pandas** is a powerful open-source Python library used for **data analysis**, **data manipulation**, and **data cleaning**.  
It provides fast, flexible, and expressive data structures designed to work with **structured data**.

### 🔹 Why Pandas?
- Built on top of NumPy → faster and efficient
- Makes data cleaning and analysis easy
- Handles tabular data (rows & columns) like Excel or SQL

### 🔹 Importing Pandas
```python
import pandas as pd
```

### 🔹 Main Data Structures
| Object | Description | Similar To |
|--------|--------------|-------------|
| **Series** | 1D labeled array | List or column |
| **DataFrame** | 2D labeled table | Excel sheet or SQL table |

---

## 📗 2. Series and DataFrame

### 🧠 Series
A **Series** is a one-dimensional array with labels (index).

```python
import pandas as pd
s = pd.Series([10, 20, 30, 40], index=['a', 'b', 'c', 'd'])
print(s)
```

**Operations:**
- Access elements: `s['a']`
- Mathematical ops: `s * 2`, `s + 10`
- Functions: `s.mean()`, `s.sum()`, `s.describe()`

### 🧠 DataFrame
A **DataFrame** is a two-dimensional labeled data structure.

```python
data = {'Name': ['Alice', 'Bob', 'Charlie'], 'Age': [25, 30, 35]}
df = pd.DataFrame(data)
print(df)
```

**Useful Attributes:**
```python
df.shape       # (rows, columns)
df.columns     # list of column names
df.index       # row indexes
df.dtypes      # data types
df.values      # data as NumPy array
```

**Accessing Data:**
```python
df['Name']                # Single column
df[['Name', 'Age']]       # Multiple columns
df.loc[0]                 # Access by label
df.iloc[0]                # Access by position
```

---

## 📘 3. Input and Output (I/O Operations)

### Reading Data
```python
pd.read_csv('data.csv')
pd.read_excel('data.xlsx')
pd.read_json('data.json')
```

### Writing Data
```python
df.to_csv('output.csv', index=False)
df.to_excel('output.xlsx', index=False)
```

**Useful Parameters:**
- `nrows`: Read limited rows  
- `usecols`: Select specific columns  
- `na_values`: Treat certain strings as NaN  
- `skiprows`: Skip rows while reading

---

## 📙 4. Data Cleaning & Preprocessing

### 🔹 Handling Missing Data
```python
df.isnull()       # Check for missing
df.dropna()       # Remove missing rows
df.fillna(0)      # Replace NaN with 0
df.fillna(method='ffill')  # Forward fill
```

### 🔹 Handling Duplicates
```python
df.duplicated()
df.drop_duplicates(inplace=True)
```

### 🔹 Renaming Columns
```python
df.rename(columns={'OldName': 'NewName'}, inplace=True)
```

### 🔹 Changing Data Types
```python
df['Age'] = df['Age'].astype(float)
df['Date'] = pd.to_datetime(df['Date'])
```

### 🔹 String Operations
```python
df['Name'] = df['Name'].str.lower()
df['City'] = df['City'].str.replace(' ', '_')
```

### 🔹 Replacing Values
```python
df['Gender'].replace({'M': 'Male', 'F': 'Female'}, inplace=True)
```

---

## 📒 5. Indexing, Selection & Filtering

### Label-based and Position-based
```python
df.loc[0, 'Name']     # by label
df.iloc[1, 2]         # by index position
```

### Conditional Filtering
```python
df[df['Age'] > 25]
df[(df['Age'] > 25) & (df['Gender'] == 'Male')]
```

### Sorting
```python
df.sort_values(by='Age', ascending=False)
df.sort_index()
```

### Reset and Set Index
```python
df.reset_index(drop=True, inplace=True)
df.set_index('Name', inplace=True)
```

---

## 📕 6. Data Transformation & Manipulation

### Apply and Map
```python
df['New'] = df['Age'].apply(lambda x: x + 2)
df['Gender'] = df['Gender'].map({'M': 'Male', 'F': 'Female'})
```

### Merging and Joining
```python
pd.merge(df1, df2, on='ID', how='inner')
pd.concat([df1, df2], axis=0)
```

### Pivot and Melt
```python
df.pivot_table(values='Sales', index='Month', columns='Region')
pd.melt(df, id_vars=['ID'], var_name='Attribute', value_name='Value')
```

---

## 📗 7. Grouping & Aggregation

```python
df.groupby('Gender')['Age'].mean()
df.groupby(['Gender', 'City']).agg({'Salary':'mean', 'Age':'max'})
```

### Transform vs Aggregate vs Filter
- **agg:** Returns summary per group  
- **transform:** Returns same size as input  
- **filter:** Returns subset of groups

---

## 📘 8. Time Series & Date Handling

```python
df['Date'] = pd.to_datetime(df['Date'])
df['Year'] = df['Date'].dt.year
df['Month'] = df['Date'].dt.month
```

**Resampling:**
```python
df.resample('M').mean()
df['Sales'].rolling(window=3).mean()
```

---

## 📙 9. Advanced Pandas Concepts

### MultiIndex
```python
df.set_index(['City', 'Year'], inplace=True)
df.loc[('Delhi', 2024)]
```

### Categorical Data
```python
df['Gender'] = df['Gender'].astype('category')
```

### One-hot Encoding
```python
pd.get_dummies(df, columns=['Gender'])
```

### Using `.query()` and `.eval()`
```python
df.query('Age > 30 & Salary > 50000')
df.eval('Bonus = Salary * 0.10', inplace=True)
```

---

## 📒 10. Visualization

```python
df['Age'].plot(kind='hist')
df.plot(x='Age', y='Salary', kind='scatter')
```

You can combine with **Matplotlib** or **Seaborn** for advanced visualizations.

---

## 📕 11. Performance Optimization

- Prefer vectorized operations instead of loops  
- Use `.query()` and `.eval()` for faster filtering  
- Convert object columns to categorical types  
- Use chunk loading for large files

---

## 📘 12. Common Interview Questions

1. Difference between `loc` and `iloc`  
2. How to merge two DataFrames?  
3. Difference between `concat()`, `merge()`, and `join()`  
4. How to handle missing values?  
5. Explain groupby and pivot_table.  
6. What’s vectorization in Pandas?  
7. How to optimize memory usage?  

---

## 🧠 13. Projects for Practice

- **Data Cleaning Project:** Clean messy CSV (missing & duplicate data)  
- **EDA Project:** Titanic / Netflix dataset  
- **Feature Engineering:** Create new columns from raw data  
- **Time Series Analysis:** Stock price or weather dataset  

---

## ✅ 14. Summary

| Concept | Real-world Use |
|----------|----------------|
| Cleaning & preprocessing | Data preparation |
| Grouping & aggregation | Summarization |
| Merging & joining | Combining datasets |
| Pivot tables | Reshaping data |
| Visualization | Reporting and insights |

---

