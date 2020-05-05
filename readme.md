# Project Goal

Input: a text file of the integer matrix as in the above example, and a value k given by a user using the keyboard.

Output: the size of the maximum submatrix and the coordinates of the bottom right corner(s). In the above example for k=20, the output would be

## Installation

JupyterLab can be installed using conda or pip

```bash
conda install -c conda-forge jupyterlab
pip install jupyterlab
```

## Imports

```python
import numpy as np
```

## Approach to the problem
* Importing the data from file: Used numpy.loadtext('filepath', dtype="integer(*by default: float*), delimiter(" "))
  
* Input statement to ask user for k-value

* Create a function *printMaxSqaureSubMatrix(arr, kval)* that takes the array and kval as a parameter.

   * Check if the row and column are empty and return if so.

   * Create a bit_array and sizes array which is of same size as the 
     original array.

   * bit_array and sizes is an array initialized with 0.

   * Use a for loop to see if the element in (ij)th position of original 
     array is greater than or less than k-value.

   * If the element is greater than k-value, set the (ij)th 
     element in bit_array to 1 and if less, set it to 0. 

   * Set a maximum(integer) and coordinates(tuple) as variable
   * **Important:**  Use sizes array to keep track of maximum submatrix 
     size.
      1. For the 1st row and 1st column (if we consider every element to 
         be bottom right hand corner of the sub matrix), there is no way 
         there could be any possible cells to the left or above them. 
         So, the value for sizes array when either i or j is set to the 
         same element as of bit_array 
      2. Coming to the other row and column then the first one, if a 1 
         is seen in the bit_array, which means the element is greater 
         than k-value, the minimum of elements in their top, left and 
         top-left is taken and 1 is added to it. In this way, sizes 
         array is set up.
   * Keep track of maximum. If the sizes_array (ijth) element is greater 
     than or equal to maximum. 
      1. If it's **equal** to the maximum, that means a new largest 
         possible another bottom right corner is found. Store the i, jth 
         position in 'coordinates' tuple. 
      2. If it's greater, a new maximum is found. Update the maximum and  
         clear all coordinates previously recorded and add the new i jth 
         position to the tuple.
  * Return the maximum and print the tuple. 
     
   

 
## Thank you!
