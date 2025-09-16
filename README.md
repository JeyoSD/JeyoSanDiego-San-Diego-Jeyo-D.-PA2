# Experiment 2: Numerical Python

This is a repository that contains Jupyter Notebook code using the Python programming language. It is a set of two exercises that make use of Numerical Python concepts.

## 1. Normalization Problem
This code creates a randomized 5x5 array using ```np.random.random((5,5))``` and finds the mean and standard deviation by using ```.mean()``` and ```.std()```. It displays the array generated and normalizes it using the formula: ```Z = (X - mean)/std```. It displays the normalized version of the array and saves it in the user's disk under the file name of `X_normalized.npy`.

### Normalization Code:
```
#Create a random 5 x 5 ndarray and store it in variable X. Normalize X. Save your normalized ndarray as X_normalized.npy

import numpy as np
def main():
    X = np.random.random((5,5))
    mean = X.mean()
    std = X.std()

    print("Your randomized array is as follows: ")
    print(X)

    print("\nYour mean is: " + str(mean) + ", while your standard deviation is: " + str(std) + "." + "\n")
    print("The normalized array is as follows: ")

    X_normalized = ((X-mean)/std)

    print(X_normalized)

    np.save('X_normalized.npy', X_normalized)

    print("\nYour normalized array has been saved as 'X_normalized.npy', you may find it in your local disk.")

main()
```

**Example Loaded Output:**
```
array([[ 0.94716928, -0.25180561, -0.35069721,  1.47234633,  1.2590635 ],
       [-2.07379894, -0.22683178, -0.16289402, -0.1612131 , -1.40514277],
       [-1.32131392,  1.18814389,  1.39934099, -0.65533627, -0.14768257],
       [-0.13094868,  0.15219797,  1.2645757 ,  0.2199112 ,  0.42804477],
       [-1.67302108, -1.17207574, -0.37918033,  1.3615139 ,  0.41963449]])
```

## 2. Divisible by 3 Problem:
This code generates an array containing the squares of the first 100 integers in a 10x10 array. It accomplishes this by creating an array ranging from 1-100 using ```np.arange(1,101)``` and squaring every element in the array. It then finds all the numbers in the array divisible by 3 using ```is_divisible_by_3 = Y_squared % 3 == 0``` and indexing the results from the initial array before displaying the results and saving it in the user's disk under the name `div_by_3.npy`.

### Divisible by 3 Code:
```
#Create a 10x10 ndarray from the squares of the first 100 integers. 
#From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy

import numpy as np
def main():
    Y = np.arange(1, 101)
    Y_squared = (Y**2).reshape(10, 10)

    is_divisible_by_3 = Y_squared % 3 == 0

    div_by_3 = (Y_squared[is_divisible_by_3]).reshape(3,11)

    print("Your initial 10x10 array of the squares of the first 100 integers is as follows: ")
    print(Y_squared)

    print("\nThe integers divisible by 3 in the 10x10 array is as follows: ")
    print(div_by_3)

    np.save('div_by_3.npy', div_by_3)

    print("\nThe array of numbers divisible by three has been saved as 'div_by_3.npy', you may find it in your local disk.")
    
main()
```

**Loaded Output:**
```
array([[   9,   36,   81,  144,  225,  324,  441,  576,  729,  900, 1089],
       [1296, 1521, 1764, 2025, 2304, 2601, 2916, 3249, 3600, 3969, 4356],
       [4761, 5184, 5625, 6084, 6561, 7056, 7569, 8100, 8649, 9216, 9801]])
```

### Requirements:

• Python v.3.8 or later versions

• Jupyter Notebook

### How to Run:

**1.** Download the repository or make a fork through GitHub.

**2.** Open Jupyter Notebook and upload the file (.ipynb) using the notebook.

**3.** Run the cells.
