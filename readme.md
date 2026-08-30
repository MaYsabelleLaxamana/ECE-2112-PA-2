# ECE-2112-Programming Assignment 2

**Made by:** Ma. Ysabelle T. Laxamana **|** 2ECE-C

This repository contains the Programming Assignment 2: NUMERICAL PYTHON (NUMPY) for the course ECE2112: Advanced Computer Programming and Algorithms for the school year 2026-2027. This project covers three Python problems pertaining to Module 2: NumPy.

## Objective
The objective of this laboratory activity is to demonstrate proficiency in utilizing the NumPy library to create and reshape arrays, perform vectorized numerical operations, compute array statistics, and apply Boolean conditions to select specific elements without the use of traditional Python loops.

## Programming Problems

### A. REPRODUCIBLE NORMALIZATION PROBLEM
Create a reproducible random 5x5 integer array and normalize its values using the standard z-score formula. The resulting array is then saved as a `.npy` file.

**The following NumPy functions and methods were used in this problem:**

* **`np.random.seed()`** - used to initialize the random number generator to a specific state, ensuring the randomly generated array is exactly the same every time the code is executed.
* **`np.random.randint()`** - used to generate the 5x5 array (ndarray) with random integers between 10 and 100.
* **`np.mean()` & `np.std()`** - used to calculate the mean and standard deviation of the entire array.
* **`np.save()`** - used to export the final normalized array to the local directory.

```python
import numpy as np
np.random.seed(2112) 
X = np.random.randint(10, 101, size=(5, 5))

X_mean = np.mean (X)
X_std = np.std (X)

X_normalized = (X - X_mean)/X_std 

print("X:\n", X)
print("Normalized X:\n", X_normalized)
print("Mean =", np.mean(X_normalized))
print("Standard Deviation =", np.std(X_normalized))

np.save("X_normalized.npy", X_normalized)
```

### B. CUBES DIVISIBLE BY 4 PROBLEM
Create a 10x10 array containing the cubes of the first 100 positive integers (from 1³ to 100³), and then extract only the values that are perfectly divisible by 4.

**The following NumPy functions and methods were used in this problem:**

* **`np.arange()`** - used to generate an initial 1D array containing the sequential integers from 1 to 100.
* **`Vectorized Arithmetic (**3)`** - used to cube every element within the array simultaneously.
* **`.reshape()`** - used to restructure the 1D array into the required 10x10 matrix format. 
* **`Boolean Indexing/Masking`** - used to filter the array with the modulo operator (%4 == 0), isolating and extracting only the elements divisible by 4.
* **`np.save()`** - used to export the final normalized array to the local directory.

```python
C = np.arange(1, 101)**3
C = C.reshape(10, 10)

div_by_4 = C[C%4 == 0] 

print("Shape of C:", C.shape)
print("Array div_by_4:\n", div_by_4)
print("Number of Selected Elements =", div_by_4.size)

np.save("div_by_4.npy", div_by_4)
```

### C. ABOVE-MEAN SQUARES PROBLEM
Create a 6x6 array containing the squares of the first 36 positive integers, calculate the mean of the entire array, and extract all elements that are strictly greater than that mean.

**The following NumPy functions and methods were used in this problem:**

* **`np.arange()`** - used to generate an initial 1D array containing the first 36 positive integers.
* **`Vectorized Arithmetic (**2)`** - used to square every element within the array simultaneously.
* **`.reshape()`** - used to format the sequence of squares into a 6x6 multidimensional array.
* **`Boolean Indexing/Masking`** - used to apply a strict inequality condition (>) to the array, filtering out any values that fall below or exactly on the calculated mean.
* **`np.save()`** - used to export the final normalized array to the local directory.

```python
S = np.arange(1, 37)**2
S = S.reshape(6, 6)

S_mean = np.mean(S) 
above_mean = S[S > S_mean]

print("S:\n", S)
print("Mean of S:", S_mean)
print("Array above_mean:", above_mean)
print("Number of Selected Elements =", above_mean.size)

np.save("above_mean.npy", above_mean)
```

**Thank you for reading!**

 To access the full Python code for Programming Assignment 2, download the file from this link: https://github.com/MaYsabelleLaxamana/ECE-2112-PA-2/blob/main/LAXAMANA_PA2.ipynb. To execute the code, open the file in Jupyter Notebook and run all the cells.

**README file Version History:**

* **August 28, 2026** - Initial README output uploaded.
* **August 30, 2026** - Made minor changes in the README output.