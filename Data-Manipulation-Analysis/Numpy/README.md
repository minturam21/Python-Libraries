
# 📘 NumPy Notes for Data Science, Interviews & Real Projects

> A complete self-study guide to master NumPy efficiently — focused on what’s truly needed for real-world data science and interview success.

---

## 🧩 1. Basics & Setup

### What is NumPy?
NumPy (Numerical Python) is a **library for fast numerical computations**.  
It provides a multidimensional array object called **ndarray**, which is much faster and more memory-efficient than Python lists.

### Why NumPy?
- Faster than native Python lists (written in C)
- Supports vectorized operations
- Foundation for Pandas, SciPy, scikit-learn, etc.

### Basic Setup
```python
import numpy as np
print(np.__version__)
````

---

## 🔢 2. Creating Arrays

### Common Ways to Create Arrays

```python
np.array([1, 2, 3])          # From list
np.arange(0, 10, 2)          # Range of numbers
np.linspace(0, 1, 5)         # 5 evenly spaced numbers
np.zeros((2, 3))             # 2x3 matrix of zeros
np.ones((3, 2))              # 3x2 matrix of ones
np.full((2, 2), 7)           # 2x2 filled with 7
np.eye(3)                    # Identity matrix
```

### Random Arrays

```python
np.random.rand(2, 3)         # Uniform random numbers
np.random.randn(2, 3)        # Normal distribution
np.random.randint(0, 10, (2, 3))  # Random integers
np.random.choice([1, 2, 3, 4])
```

---

## 🧮 3. Array Attributes

### Important Properties

```python
arr = np.array([[1, 2, 3], [4, 5, 6]])
arr.shape      # (2, 3)
arr.dtype      # int64
arr.ndim       # 2
arr.size       # 6
arr.itemsize   # bytes per element
```

### Reshaping & Flattening

```python
arr.reshape(3, 2)
arr.ravel()          # Flatten (returns view)
arr.flatten()        # Flatten (returns copy)
```

### Data Type Conversion

```python
arr.astype(float)
```

---

## 🧭 4. Indexing & Slicing

### 1D Example

```python
arr = np.array([10, 20, 30, 40, 50])
arr[1:4]        # [20, 30, 40]
```

### 2D Example

```python
arr = np.array([[1,2,3], [4,5,6], [7,8,9]])
arr[1, 2]       # 6
arr[:, 1]       # All rows, 2nd column
arr[0:2, 0:2]   # Sub-matrix
```

### Boolean & Conditional Indexing

```python
arr[arr > 4]
np.where(arr % 2 == 0)
```

---

## ⚙️ 5. Array Operations

### Element-wise Arithmetic

```python
a = np.array([1, 2, 3])
b = np.array([10, 20, 30])
a + b
a * 2
b / a
```

### Broadcasting

Allows operations between different-shaped arrays automatically.

```python
a = np.array([[1], [2], [3]])
b = np.array([10, 20, 30])
a + b
```

### Aggregate Functions

```python
arr.sum()
arr.mean()
arr.std()
arr.var()
arr.min()
arr.max()
arr.sum(axis=0)
arr.mean(axis=1)
```

### Logical Operations

```python
np.logical_and(arr > 3, arr < 8)
np.logical_or(arr < 2, arr > 8)
```

---

## 📊 6. Statistical & Mathematical Functions

```python
np.mean(arr)
np.median(arr)
np.std(arr)
np.var(arr)
np.percentile(arr, 75)
np.corrcoef(x, y)
np.exp(arr)
np.log(arr)
np.sqrt(arr)
np.cumsum(arr)
np.cumprod(arr)
```

🧠 *Useful in feature scaling, EDA, and statistical analysis.*

---

## 🧱 7. Matrix Operations (Linear Algebra)

```python
A = np.array([[1, 2], [3, 4]])
B = np.array([[5, 6], [7, 8]])

np.dot(A, B)          # Matrix multiplication
A @ B                 # Same as np.dot
A.T                   # Transpose
np.linalg.inv(A)      # Inverse
np.linalg.det(A)      # Determinant
np.linalg.solve(A, [1, 0])  # Solve Ax = b
np.linalg.eig(A)      # Eigenvalues & eigenvectors
```

🧠 *Essential for ML algorithms like PCA, regression, etc.*

---

## 🔄 8. Joining, Splitting, Copying

### Combine Arrays

```python
np.hstack((a, b))
np.vstack((a, b))
np.concatenate([a, b], axis=0)
```

### Split Arrays

```python
np.split(arr, 3)
np.hsplit(arr, 2)
np.vsplit(arr, 2)
```

### Copy vs Reference

```python
b = a               # Reference (linked)
c = a.copy()        # Copy (independent)
```

---

## 🧰 9. Handling Missing or Invalid Data

```python
arr = np.array([1, 2, np.nan, 4, np.inf])

np.isnan(arr)
np.isinf(arr)
np.nan_to_num(arr)
np.nanmean(arr)
```

🧠 *Used for cleaning datasets before feeding ML models.*

---

## 🧠 10. Useful Utilities

```python
np.sort(arr)
np.argsort(arr)
np.unique(arr)
arr.nbytes
np.vectorize(func)(arr)
```

### Timing Code

```python
%timeit np.sum(arr)
```

---

## 🎯 Bonus (Optional but Useful)

* **Structured Arrays:** `np.recarray`
* **Masked Arrays:** `np.ma`
* **File Saving:**

  ```python
  np.save('data.npy', arr)
  np.load('data.npy')
  np.savez('data.npz', x=a, y=b)
  ```

---

## 🧩 Practice Ideas

1. Compute mean, std, min, max per column of a dataset using NumPy.
2. Implement Linear Regression manually using NumPy (no sklearn).
3. Load a CSV using `np.genfromtxt()` and clean NaN values.
4. Create and visualize random distributions.
5. Try vectorizing Python loops using NumPy for performance gain.

---

## ✅ Summary

| Concept             | Why It Matters               |
| ------------------- | ---------------------------- |
| Array Creation      | Data input and preprocessing |
| Indexing & Slicing  | Data filtering               |
| Broadcasting        | Fast computation             |
| Aggregation & Stats | EDA, ML preprocessing        |
| Linear Algebra      | Model training               |
| Missing Data        | Data cleaning                |
| Joining & Splitting | Dataset management           |

---

