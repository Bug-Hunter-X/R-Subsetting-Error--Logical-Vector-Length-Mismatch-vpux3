# R Subsetting Bug: Logical Vector Length Mismatch

This repository demonstrates a common, yet subtle, error in R when subsetting data frames using logical vectors.  The issue arises when the length of the logical vector used for subsetting is longer than the number of rows in the data frame.  This often leads to silent failures or unexpected behavior, making it difficult to debug.

## The Bug

The `bug.R` file contains code that attempts to subset a data frame using a logical vector that exceeds the number of rows.  R does not throw an error, it silently truncates the logical vector to match the data frame's length. This is sometimes hard to detect, resulting in incorrect results.

## The Solution

The `bugSolution.R` file provides a corrected version of the code. It explicitly checks the length of the logical vector against the number of rows in the data frame and throws an error if there's a mismatch. This prevents unexpected behavior and makes debugging easier. 

## How to Reproduce

1. Clone this repository.
2. Open `bug.R` and run the code. Note that no error is thrown, but the result is unexpected.
3. Open `bugSolution.R` and run the code. The solution throws an error if the length of logical vector does not match the number of rows in the data frame.
