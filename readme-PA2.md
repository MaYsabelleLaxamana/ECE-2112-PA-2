\# ECE-2112-Programming Assignment 2



\*\*Made by:\*\* Ma. Ysabelle T. Laxamana

\*\*|\*\* 2ECE-C



This repository contains the Programming Assignment 2: NUMERICAL PYTHON (NUMPY) for the course ECE 2112: Advanced Computer Programming for the school year 2026-2027. This project covers three Python problems pertaining to Module 2: NumPy.



\## Objective

The objective of this laboratory activity is to demonstrate proficiency in utilizing the NumPy library to create and reshape arrays, perform vectorized numerical operations, compute array statistics, and apply Boolean conditions to select specific elements without the use of traditional Python loops or list comprehensions.



\## Programming Problems



\### A. REPRODUCIBLE NORMALIZATION PROBLEM

Create a reproducible random 5x5 integer array and normalize its values using the standard z-score formula. The resulting array is then saved as a `.npy` file.



\*\*The following NumPy functions and methods were used in this problem:\*\*



\* \*\*`np.random.seed()`\*\* - used to initialize the random number generator to a specific state, ensuring the randomly generated array is exactly the same every time the code is executed.

\* \*\*`np.random.randint()`\*\* - used to generate the 5x5 array (ndarray) populated with random integers between 10 and 100.

\* \*\*`np.mean()` \& `np.std()`\*\* - used to calculate the mean and population standard deviation of the entire array.

\* \*\*`np.save()`\*\* - used to export the final normalized array to the local directory.





```python

import numpy as np

np.random.seed(2112) 

X = np.random.randint(10, 101, size=(5, 5))



X\_mean = np.mean (X)

X\_std = np.std (X)



X\_normalized = (X - X\_mean)/X\_std 



print("X:\\n", X)

print("Normalized X:\\n", X\_normalized)

print("Mean =", np.mean(X\_normalized))

print("Standard Deviation =", np.std(X\_normalized))



np.save("X\_normalized.npy", X\_normalized)

```



\### **B. CUBES DIVISIBLE BY 4 PROBLEM**

Create a 10x10 array containing the cubes of the first 100 positive integers (from $1^3$ to $100^3$), and then extract only the values that are perfectly divisible by 4.



\*\*The following NumPy functions and methods were used in this problem:\*\*



\* \*\*`np.arange()`\*\* - used to generate an initial 1D array containing the sequential integers from 1 to 100.

\* \*\*`Vectorized Arithmetic (\*\* 3)`\*\* - used to cube every element within the array simultaneously.

\* \*\*`.reshape()`\*\* - used to restructure the 1D array into the required 10x10 matrix format.

\* \*\*`Boolean Indexing / Masking`\*\* - used to filter the array with the modulo operator (% 4 == 0), isolating and extracting only the elements divisible by 4.

\* \*\*`np.save()`\*\* - used to export the final normalized array to the local directory.



```python

C = np.arange(1, 101)\*\*3

C = C.reshape(10, 10)



div\_by\_4 = C\[C%4 == 0] 



print("Shape of C:", C.shape)

print("Array div\_by\_4:\\n", div\_by\_4)

print("Number of Selected Elements =", div\_by\_4.size)



np.save("div\_by\_4.npy", div\_by\_4)

```

\### **ABOVE-MEAN SQUARES PROBLEM**

Create a 6x6 array containing the squares of the first 36 positive integers, calculate the mean of the entire array, and extract all elements that are strictly greater than that mean.



\*\*The following NumPy functions and methods were used in this problem:\*\*



\* \*\*`np.arange()`\*\* - used to generate an initial 1D array containing the first 36 positive integers.

\* \*\*`Vectorized Arithmetic (\*\*2)`\*\* - used to square every element within the array simultaneously.

\* \*\*`.reshape()`\*\* - used to format the sequence of squares into a 6x6 multidimensional array.

\* \*\*`Boolean Indexing / Masking`\*\* - used to apply a strict inequality condition (>) to the array, filtering out any values that fall below or exactly on the calculated mean.

\* \*\*`np.save()`\*\* - used to export the final normalized array to the local directory.



```python

S = np.arange(1, 37)\*\*2

S = S.reshape(6, 6)



S\_mean = np.mean(S) 



above\_mean = S\[S > S\_mean] 



print("S:\\n", S)

print("Mean of S:", S\_mean)

print("Array above\_mean:", above\_mean)

print("Number of Selected Elements =", above\_mean.size)



np.save("above\_mean.npy", above\_mean)

```



\*\*Thank you for reading!\*\*



To access the full Python code for Programming Assignment 1, download the file from this link: \[link] To execute the code, open the file in Jupyter Notebook and run all the cells.





\*\*README file Version History:\*\*



\* \*\*August 28, 2026\*\* - Initial README output uploaded.

