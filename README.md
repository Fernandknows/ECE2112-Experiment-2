# EXP2 - Numerical Python <br/> *Christian Justin M. Fernando | 2ECE-B | ECE2112*
Hello! This repository contains Python codes I made for my ECE2112 course, particularly for Experiment #2. <br/><br/> For experiment #2 the problems and instructions are:



**1. Normalization Problem:** Normalization is one of the most basic preprocessing techniques in
data analytics. This involves centering and scaling process. Centering means subtracting the data from the
mean and scaling means dividing with its standard deviation. Mathematically, normalization can be expressed as: 𝑍 =(𝑋 − 𝑥̅) / 𝜎
In Python, element-wise mean and element-wise standard deviation can be obtained by using .mean() and.std() calls. In this problem, create a random 5 x 5 ndarray and store it to variable X. Normalize X. Save your normalized ndarray as X_normalized.npy <br/>

<p><strong><em>Here are the steps to follow for setting up and processing the matrix:</em></strong></p>

<h5><em>Import and Setup</em></h5>
<p>The code starts by importing the NumPy library and giving it the alias <code>np</code>, simplifying subsequent code.</p>

<h5><em>Matrix Generation</em></h5>
<p>A 5x5 matrix filled with random values between 0 and 1 is created using <code>np.random.random()</code>.</p>

<h5><em>Compute Statistics</em></h5>
<p>The mean and standard deviation of the generated matrix are calculated with <code>X.mean()</code> and <code>X.std()</code>.</p>

<h5><em>Normalize Matrix</em></h5>
<p>The matrix is normalized by subtracting the mean and dividing by the standard deviation, with the result stored in the variable <code>formula</code>.</p>

<h5><em>Output and Save</em></h5>
<p>The normalized matrix is printed to the console, then saved to a file named <code>'X_normalized.npy'</code> using <code>np.save()</code>. A success message is displayed to confirm the file has been saved.</p>

**Function:**

  ```
  #Assign numpy to be np.
  import numpy as np

  #Create a random 5x5 array.
  X = np.random.random((5, 5))

  #Assigning variable to the mean and standard deviation of the variable 'X' using .mean() and .std() calls.
  mean = X.mean()
  std = X.std()

  #Assign the normalization formula to variable 'formula'.
  formula = (X - mean) / std

  #Print the normalization formula.
  print(formula)

  #Saving the normalized array to a designated file.
  np.save('X_normalized.npy', formula)

  #Output to indicate that the array has been saved successfully.
  print("\nYour file has been saved as 'X_normalized.npy' successfully!")
```
**Output example:**
```
[[ 0.43494415 -0.91163436  1.23861816 -0.129228    1.09122219]
 [-0.79737562 -1.10107894 -0.68677011 -1.35623225  0.86536128]
 [-1.32304271  1.01569933  1.07487144  0.00285109  1.06525071]
 [ 1.14963972  0.04739948  0.78603041 -1.89616875  0.35921189]
 [-0.89107567  1.12934374 -1.7746977  -0.00355081  0.61041133]]

Your file has been saved as 'X_normalized.npy' successfully! 
```

<h5><em>Conclusion</em></h5>
<p>This process efficiently demonstrates generating, analyzing, and normalizing a matrix with NumPy. By creating a random matrix, calculating its statistics, and normalizing the data, we prepare it for further use. Saving the results ensures that the normalized matrix is available for future applications, with a success message confirming the task's completion.</p>

**2. Divisible by 3 Problem:** Create the following 10 x 10 ndarray, Which are the squares of the first 100 positive integers.
From this ndarray, determine all the elements that are divisible by 3. Save the result as div_by_3.npy <br/>

<p><strong><em>Here are the steps to follow for processing the array and saving the results:</em></strong></p>

<h5><em>Assign numpy to be np</em></h5>
<p>Import the NumPy library and assign it the alias <code>np</code>, which simplifies the code that follows.</p>

<h5><em>First 100 positive integers array</em></h5>
<p>Create an array <code>A</code> containing the first 100 positive integers using <code>np.arange(1, 101)</code>.</p>

<h5><em>Squaring each integer inside the array created</em></h5>
<p>Square each element of the array <code>A</code> to produce a new array <code>sqrdnum</code> with <code>A ** 2</code>.</p>

<h5><em>Reshaping into 10x10 array</em></h5>
<p>Reshape the squared numbers array <code>sqrdnum</code> into a 10x10 matrix named <code>reshapedA</code> using <code>sqrdnum.reshape(10, 10)</code>.</p>

<h5><em>Determining values that are divisible by 3</em></h5>
<p>Extract values from the matrix <code>reshapedA</code> that are divisible by 3, storing them in <code>divisible_by_3</code> with <code>reshapedA[reshapedA % 3 == 0]</code>.</p>

<h5><em>Print the results</em></h5>
<p>Print the 10x10 matrix of squared numbers and the values divisible by 3 to the console. Save the filtered values to a file named <code>'div_by_3.npy'</code> using <code>np.save()</code>. A success message is printed to confirm the file has been saved.</p>


**Function:**

```
#Assign numpy to be np.
import numpy as np

#First 100 positive integers array.
A = np.arange(1, 101)

#Squaring each integer inside the array created.
sqrdnum = A ** 2

#Reshaping into 10x10 array.
reshapedA = sqrdnum.reshape(10, 10)

#Determining values that are divisible by 3.
divisible_by_3 = reshapedA[reshapedA % 3 == 0]

#Print the results.
print("A 10x10 Array of Squared Numbers:")
print(reshapedA)

print("\nThese are the values that are divisible by 3:")
print(divisible_by_3)

np.save('div_by_3.npy', div_by_3)

#Output to prompt the user that the file has been saved as 'div_by_3.npy' successfully.
print("\nYour file has been saved as 'div_by_3.npy' successfully!")
```
**Output Example:**
```
A 10x10 Array of Squared Numbers:
[[    1     4     9    16    25    36    49    64    81   100]
 [  121   144   169   196   225   256   289   324   361   400]
 [  441   484   529   576   625   676   729   784   841   900]
 [  961  1024  1089  1156  1225  1296  1369  1444  1521  1600]
 [ 1681  1764  1849  1936  2025  2116  2209  2304  2401  2500]
 [ 2601  2704  2809  2916  3025  3136  3249  3364  3481  3600]
 [ 3721  3844  3969  4096  4225  4356  4489  4624  4761  4900]
 [ 5041  5184  5329  5476  5625  5776  5929  6084  6241  6400]
 [ 6561  6724  6889  7056  7225  7396  7569  7744  7921  8100]
 [ 8281  8464  8649  8836  9025  9216  9409  9604  9801 10000]]

These are the values that are divisible by 3:
[   9   36   81  144  225  324  441  576  729  900 1089 1296 1521 1764
 2025 2304 2601 2916 3249 3600 3969 4356 4761 5184 5625 6084 6561 7056
 7569 8100 8649 9216 9801]

Your file has been saved as 'div_by_3.npy' successfully!
```

<h5><em>Conclusion</em></h5>
<p>This script illustrates basic NumPy operations: creating and manipulating arrays. It generates the first 100 positive integers, squares them, reshapes the result into a 10x10 matrix, and identifies values divisible by 3. The filtered values are then saved to a file, with a confirmation message indicating the successful save.</p>


### The problems above focus on Numerical Python, including arrays and numerical analysis. Feel free to let me know if there is anything I can do to improve my code! Thank you!





