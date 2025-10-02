# NumPy Practice Notebook

This notebook serves as a practical introduction and cheatsheet for fundamental operations and functions in the **NumPy** library, which is essential for numerical computing in Python.

## Table of Contents

1.  [Array Creation and Attributes](#array-creation-and-attributes)
2.  [Intrinsic Array Creation Methods](#intrinsic-array-creation-methods)
3.  [Array Manipulation](#array-manipulation)
4.  [Array Properties and Aggregation](#array-properties-and-aggregation)
5.  [Basic Array Arithmetic and Boolean Indexing](#basic-array-arithmetic-and-boolean-indexing)
6.  [Practical Examples (Use Cases)](#practical-examples-use-cases)

---

## 1. Array Creation and Attributes

Demonstrates the basic creation of NumPy arrays and inspection of their core properties.

| Operation | Code Example | Description |
| :--- | :--- | :--- |
| **Basic Creation** | `arr = np.array([[...]], np.int64)` | Creates a NumPy array, explicitly setting the data type. |
| **Shape** | `arr.shape` | Returns a tuple indicating the size of each dimension (e.g., `(1, 20)` for 1 row, 20 columns). |
| **Data Type** | `arr.dtype` | Returns the data type of the elements (e.g., `dtype('int64')`). |
| **Indexing/Assignment** | `arr[0, 3] = 69` | Accesses or modifies an element at a specific index. |
| **From List** | `listarr = np.array([[...]])` | Creates a multi-dimensional array from a Python list of lists. |
| **Size** | `listarr.size` | Returns the total number of elements in the array. |
| **From Set** | `np.array({654, ...})` | **Note:** Creating an array directly from a set results in an `object` dtype array, which is generally inefficient for numerical work. |

---

## 2. Intrinsic Array Creation Methods

Methods provided by NumPy for quickly generating arrays with predefined values or sequences.

| Function | Code Example | Description |
| :--- | :--- | :--- |
| **`np.zeros`** | `z = np.zeros((6, 9))` | Creates an array of the specified shape, filled with zeros (default dtype is `float`). |
| **`np.arange`** | `rng = np.arange(15)` | Creates an array with evenly spaced values within a given interval. |
| **`np.linspace`** | `lspace = np.linspace(1, 15, 10)` | Returns a specified number of evenly spaced samples (10 samples) over a closed interval (`[1, 15]`). |
| **`np.empty`** | `emp = np.empty((2, 3))` | Creates an array without initializing its entries. Values are whatever is currently in memory. |
| **`np.identity`**| `idt = np.identity(3)` | Creates a square identity matrix (a 2D array with 1s on the main diagonal and 0s elsewhere). |

---

## 3. Array Manipulation

Functions for changing the dimensions or orientation of an array.

| Function | Code Example | Description |
| :--- | :--- | :--- |
| **`reshape`** | `a.reshape(3, 33)` | Gives a new shape to an array without changing its data (must be a valid distribution, e.g., $3 \times 33 = 99$ elements). |
| **`ravel`** | `a.ravel()` | Returns a flattened one-dimensional array. |
| **`np.vstack`** | `np.vstack([a, b])` | Stacks arrays vertically (row-wise). |
| **`np.hstack`** | `np.hstack([a, b])` | Stacks arrays horizontally (column-wise). |

---

## 4. Array Properties and Aggregation

Functions for performing calculations and retrieving structural information.

| Property/Method | Code Example | Description |
| :--- | :--- | :--- |
| **Sum (Axis 0)** | `a2.sum(axis=0)` | Sums elements along the specified axis (columns). |
| **Sum (Axis 1)** | `a2.sum(axis=1)` | Sums elements across the specified axis (rows). |
| **Transpose** | `a2.T` | Returns the transpose of the array (swaps rows and columns). |
| **Flat Iterator** | `for _ in a2.flat:` | Provides an efficient iterator over all elements of the array. |
| **Dimensions** | `a2.ndim` | Returns the number of array dimensions. |
| **Bytes Consumed** | `a2.nbytes` | Returns the total number of bytes consumed by the array data. |
| **Max Index** | `oo.argmax()` | Returns the index of the maximum value. |
| **Min Index** | `oo.argmin()` | Returns the index of the minimum value. |
| **Sorted Indices** | `oo.argsort()` | Returns the indices that would sort the array. |
| **Argmax (Axis)** | `a2.argmax(axis=0)` | Returns the indices of the maximum values along an axis. |
| **To List** | `a2.tolist()` | Converts the NumPy array back into a nested Python list. |

---

## 5. Basic Array Arithmetic and Boolean Indexing

NumPy makes element-wise operations and conditional selections straightforward.

| Operation | Code Example | Description |
| :--- | :--- | :--- |
| **Element-wise Addition** | `a2 + ar2` | Performs standard matrix addition. |
| **Conditional Indexing** | `np.where(a2 > 2)` | Returns the indices where a condition is true. |
| **Count Non-Zero** | `np.count_nonzero(a2)` | Counts the number of non-zero elements in the array. |
| **Boolean Filtering** | `arr[arr % 2 == 1]` | Extracts elements that satisfy a condition (e.g., odd numbers). |
| **Conditional Assignment**| `arr[arr % 2 == 1] = -1` | Assigns a new value to all elements that satisfy a condition. |

---

## 6. Practical Examples (Use Cases)

A collection of common NumPy operations demonstrated with practical scenarios:

* **Extracting odd numbers:** Using boolean indexing to filter a 1D array.
* **Replacing values conditionally:** Modifying an array in place based on a condition.
* **Safe conditional replacement:** Using `.copy()` to modify a filtered array without changing the original.
* **Vertical Stacking:** Using `np.vstack()` to combine two arrays row-wise.
* **Horizontal Stacking:** Using `np.hstack()` to combine two arrays column-wise.
* **Finding matching positions:** Using `np.where(a == b)` to get indices where two arrays have equal elements.
* **Filtering by range:** Using multiple conditions with the bitwise AND operator (`&`) for range filtering (e.g., `(a >= 5) & (a <= 10)`).
* **Reversing a 2D array's rows:** Using slicing `arr[::-1, :]` to quickly reverse the order of rows.
