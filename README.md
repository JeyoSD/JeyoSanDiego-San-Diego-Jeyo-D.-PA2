# Experiment 2: Numerical Python v.1.1

This repository contains Jupyter Notebook code written in the Python programming language. It is a set of two exercises that utilize Numerical Python concepts.

## 1. Normalization Problem
The first part of the code imports the NumPy Library using `import numpy as np` for use in the code and defines the main function. The first three lines of code generate and output a 5x5 array with randomized values using `np.random.random((5,5))` and store the randomized array in `X`.
```
import numpy as np #Imports the NumPy Library
def main():
    X = np.random.random((5,5)) #Generates a 5x5 array with randomized values
    print("Your randomized array is as follows: ", X) #Outputs the generated randomized array
```
The main body of the code finds the mean value of the array by finding the quotient of the sum of all elements and the total number of elements in the array using `.mean()` and finds the standard deviation using `.std()`. It stores the results in `mean` and `std`, which are then used in the normalization formula of ((x-mean)/standard deviation) and saved under `X_normalized` and output for viewing.
```
    mean = X.mean() #Finds the mean value of array X
    std = X.std() #Finds the standard deviation of array X
    print("\nYour mean is: " + str(mean) + ", while your standard deviation is: " + str(std) + "." + "\n") #Outputs the mean and standard deviation

    X_normalized = ((X-mean)/std) #Solves for the normalized values of the array
    print("The normalized array is as follows: ", X_normalized) #Prints another notification for the 
```
The last segment of the code uses `np.save()` to save `X_normalized` as a .npy file in the user's local directory, displaying an output message and then calling the main function to execute the code. 
```
    np.save('X_normalized.npy', X_normalized) #Saves the normalized values as X_normalized.npy

    print("\nYour normalized array has been saved as 'X_normalized.npy', you may find it in your local disk.") #Outputs a message to notify the user of the process

main()
```

### Normalization Code:
```
import numpy as np #Imports the NumPy Library
def main():
    X = np.random.random((5,5)) #Generates a 5x5 array with randomized values
    print("Your randomized array is as follows:\n", X) #Outputs the generated randomized array
    mean = X.mean() #Finds the mean value of array X
    std = X.std() #Finds the standard deviation of array X
    print("\nYour mean is: " + str(mean) + ", while your standard deviation is: " + str(std) + "." + "\n") #Outputs the mean and standard deviation

    X_normalized = ((X-mean)/std) #Solves for the normalized values of the array
    print("The normalized array is as follows:\n", X_normalized) #Outputs the normalized values for the array

    np.save('X_normalized.npy', X_normalized) #Saves the normalized values as X_normalized.npy

    print("\nYour normalized array has been saved as 'X_normalized.npy', you may find it in your local disk.") #Outputs a message notifying the user of the saved file

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
The first part of the code imports the NumPy Library and generates an array with values ranging from 1 to 100 using `np.arange(1, 100)`, storing the array in `Y`. The next code raises all elements of the array by 2, squaring all values. Since the array is initially shapeless, the code uses ```.reshape(10,10)``` to transform the unshaped array into a 10x10 shape, storing the array in `Y_squared.`
```
import numpy as np #Imports the NumPy Library
def main():
    Y = np.arange(1, 101) #Generates an array with the values of 1 to 100
    Y_squared = (Y**2).reshape(10, 10) #Squares all the values in the array and reshapes the array to a 10x10 shape
```
The next part of the code stores a Boolean expression to find all values that are divisible by three and have no remainder, specifically searching for those that are perfectly divisible by 3 and storing the condition in `is_divisible_by_3`. It is comprised primarily of two parts: `Y_squared % 3` divides the values by 3 and returns the remainder of the quotient, while `== 0` imposes the condition that the remainder of the quotient of each value must equal 0, turning the expression into the necessary condition. The next code indexes all values that return true from `is_divisible_by_3` in the array `Y_squared`, generating an unshaped array with all values divisible by 3. It then transforms this array into a 3x11 array using `.reshape(3,11)` and stores the array in `div_by_3`.
```
    is_divisible_by_3 = Y_squared % 3 == 0 #Stores a condition for values that are divisible by 3 
    div_by_3 = (Y_squared[is_divisible_by_3]).reshape(3,11) #Finds all values according to the condition and reshapes the array to 3x11
```
The last parts of the code send an output message and display the `Y_squared` array and the `div_by_3` array. It then saves the `div_by_3` array in the user's local files using `np.save()` and notifies the user of the process with the following message before calling the main function to execute the code.
```
    print("Your initial 10x10 array of the squares of the first 100 integers is as follows:\n", Y_squared) #Outputs the squared values of the initial array
    print("\nThe integers divisible by 3 in the 10x10 array is as follows:\n", div_by_3) #Outputs the array with values divisible by 3

    np.save('div_by_3.npy', div_by_3) #Saves the div_by_3 array as 'div_by_3.npy' in the user's local directory

    print("\nThe array of numbers divisible by three has been saved as 'div_by_3.npy', you may find it in your local disk.") #Outputs a message notifying the user of the saved file
    
main()
```

### Divisible by 3 Code:
```
import numpy as np #Imports the NumPy Library
def main():
    Y = np.arange(1, 101) #Generates an array with the values of 1 to 100
    Y_squared = (Y**2).reshape(10, 10) #Squares all the values in the array and reshapes the array to a 10x10 shape

    is_divisible_by_3 = Y_squared % 3 == 0 #Stores a condition for values that are divisible by 3 
    div_by_3 = (Y_squared[is_divisible_by_3]).reshape(3,11) #Finds all values according to the condition and reshapes the array to 3x11

    print("Your initial 10x10 array of the squares of the first 100 integers is as follows:\n", Y_squared) #Outputs the squared values of the initial array
    print("\nThe integers divisible by 3 in the 10x10 array is as follows:\n", div_by_3) #Outputs the array with values divisible by 3

    np.save('div_by_3.npy', div_by_3) #Saves the div_by_3 array as 'div_by_3.npy' in the user's local directory

    print("\nThe array of numbers divisible by three has been saved as 'div_by_3.npy', you may find it in your local disk.") #Outputs a message notifying the user of the saved file
    
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
