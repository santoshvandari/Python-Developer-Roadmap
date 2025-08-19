# Popular Libraries

Python's strength lies in its extensive ecosystem of libraries. Here are the most important libraries that every Python developer should know.

## NumPy for Numerical Computing

NumPy is the foundation of scientific computing in Python, providing powerful array operations and mathematical functions.

### Array Creation and Basic Operations

```python
import numpy as np

# Creating arrays
arr1d = np.array([1, 2, 3, 4, 5])
arr2d = np.array([[1, 2, 3], [4, 5, 6]])
zeros = np.zeros((3, 4))
ones = np.ones((2, 3))
range_arr = np.arange(0, 10, 2)  # [0, 2, 4, 6, 8]
linspace = np.linspace(0, 1, 5)  # [0, 0.25, 0.5, 0.75, 1]

print(f"1D array: {arr1d}")
print(f"2D array:\n{arr2d}")
print(f"Array shape: {arr2d.shape}")
print(f"Array dtype: {arr1d.dtype}")

# Array operations
print(f"Sum: {np.sum(arr1d)}")
print(f"Mean: {np.mean(arr1d)}")
print(f"Standard deviation: {np.std(arr1d)}")
print(f"Max: {np.max(arr1d)}")
print(f"Min: {np.min(arr1d)}")
```

### Array Manipulation and Mathematical Operations

```python
# Mathematical operations
a = np.array([1, 2, 3, 4])
b = np.array([5, 6, 7, 8])

print(f"Addition: {a + b}")
print(f"Multiplication: {a * b}")
print(f"Power: {a ** 2}")
print(f"Square root: {np.sqrt(a)}")

# Matrix operations
matrix_a = np.array([[1, 2], [3, 4]])
matrix_b = np.array([[5, 6], [7, 8]])

print(f"Matrix multiplication:\n{np.dot(matrix_a, matrix_b)}")
print(f"Element-wise multiplication:\n{matrix_a * matrix_b}")

# Array indexing and slicing
data = np.array([[1, 2, 3, 4], [5, 6, 7, 8], [9, 10, 11, 12]])
print(f"Element at [1,2]: {data[1, 2]}")
print(f"First row: {data[0, :]}")
print(f"Last column: {data[:, -1]}")
print(f"Subarray:\n{data[1:, 1:3]}")

# Boolean indexing
numbers = np.array([1, 5, 3, 8, 2, 9, 4])
mask = numbers > 4
print(f"Numbers > 4: {numbers[mask]}")
```

## Pandas for Data Manipulation

Pandas provides powerful data structures and analysis tools for working with structured data.

### DataFrames and Series

```python
import pandas as pd
import numpy as np

# Creating DataFrames
data = {
    "Name": ["Alice", "Bob", "Charlie", "Diana", "Eve"],
    "Age": [25, 30, 35, 28, 32],
    "City": ["New York", "London", "Tokyo", "Paris", "Sydney"],
    "Salary": [70000, 80000, 90000, 75000, 85000]
}

df = pd.DataFrame(data)
print("DataFrame:")
print(df)
print(f"\nDataFrame info:")
print(df.info())

# Basic operations
print(f"\nFirst 3 rows:")
print(df.head(3))
print(f"\nDescriptive statistics:")
print(df.describe())

# Selecting data
print(f"\nNames column:")
print(df["Name"])
print(f"\nMultiple columns:")
print(df[["Name", "Salary"]])
print(f"\nRows where Age > 30:")
print(df[df["Age"] > 30])
```