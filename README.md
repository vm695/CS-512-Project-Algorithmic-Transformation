# CS-512-Project-Algorithmic-Transformation
## Introduction

The objective of this project is to perform an algorithmic transformation from ZOE to Subset Sum Problem. 
This project presents an algorithmic transformation for converting Zero-One Equation (ZOE) problems into Subset Sum problems. Utilizing efficient encoding techniques, ZOE instances in CSV format are transformed into integer representations suitable for Subset Sum analysis. The transformation involves encoding each column into integers, forming a Subset Sum problem. This program, optimized for scalability, handles matrices up to 20x20 dimensions. This transformation enables leveraging Subset Sum-solving methodologies to efficiently tackle ZOE challenges.

## Step 1: Place the input file

A Comma Separated Values (CSV) file `input.csv` with m x n matrix containing only 0 and 1's.
The file should have in total m rows, and each row up to n values and is placed in the same path as the script file. The values can be only 0 or 1.

## Step 2: Run the Script file

Run the `Alg_Transformation_script.py` file. this will read the input file `input.csv` and validates it. It then performs the algorithmic transformation from the input ZOE instance to a Subset Sum Problem. If the transformed subset sum problem has a solution, it is then converted into a ZOE solution.

## Step 3 : Output
The Output is printed on the terminal and also the output ZOE vector is stored in a `output.csv` file, present in the same folder as the script and input file.

## Transformation Process
The transformation algorithm from ZOE to SUBSET SUM is done as below

### Reduction from ZOE to SUBSET SUM
Initially, the m × n input ZOE instance is analyzed column-wise. Each column represents a binary vector of length m. To facilitate the translation to the Subset Sum problem, these binary vectors are interpreted as integers. Each column is treated as a integer value, with its binary representation transformed into its decimal equivalent. The target sum is represented by an all-1’s vector of size n, reflecting the sum of all integers formed from the ZOE columns. Subsequently, all column vectors and the target all-1’s vector are encoded as integers. This encoding process ensures that the ZOE instance is translated into a form compatible with the Subset Sum problem.

### Solving the SUBSET SUM
With the ZOE instance transformed into a Subset Sum instance, the goal shifts to finding a subset of integers from the given set whose sum equals the target value determined in the previous step. We have used dynamic programming to efficiently solve the Subset Sum problem and identify the subset of integers that satisfies the target sum condition.

### Converting the solution
Upon successful resolution of the Subset Sum problem, the obtained solution is verified for its feasibility. If a valid solution exists, it indicates the presence of a subset of integers that sums up to the target value. Assuming the Subset Sum instance is solvable, the final step involves translating the obtained solution back into a solution for the original ZOE problem.This translation process entails mapping the integers comprising the Subset Sum solution to their corresponding binary decision variables in the ZOE instance. This includes assigning 1 to a variable x<sub>i</sub> if the integer obtained form the i<sup>th</sup> column is present in the solution of SUBSET SUM.

<img width="1081" alt="image" src="https://github.com/vm695/CS-512-Project-Algorithmic-Transformation/assets/167110841/578f3eee-2054-4ff1-8bff-f3f35eeb0867">
