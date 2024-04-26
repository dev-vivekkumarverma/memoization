---

# Memoization in Python: Optimizing Fibonacci Calculation

## Introduction
This repository demonstrates the use of memoization, a powerful technique to optimize recursive functions, using the example of calculating Fibonacci numbers in Python. 

## Overview
The provided Jupyter Notebook (`recursion.ipynb`) contains two implementations of the Fibonacci sequence calculation: 
1. A naive recursive approach.
2. An optimized approach using memoization.

## File Contents
- **`recursion.ipynb`**: Contains the Python code for both the naive and memoized implementations of the Fibonacci sequence calculation.

## Installation
1. Clone the repository to your local machine.
2. Ensure you have Jupyter Notebook installed.
3. Open `recursion.ipynb` using Jupyter Notebook.

## Usage
### Naive Recursive Approach
```python
import time

@timeProfiler
def find_feb(n):
    def feb(n):
        if n == 1:
            return 0
        elif n == 2:
            return 1
        else:
            return feb(n - 1) + feb(n - 2)
        
    return feb(n)

result, execution_time = find_feb(19)
print(f"Result: {result}, Execution Time: {execution_time} seconds")
```

### Memoized Approach
```python
import time

@timeProfiler
def find_feb_with_memo(n):
    memo = {}
    
    def feb_memoised(n):
        if n in memo:
            return memo[n]
        if n == 1:
            return 0
        elif n == 2:
            return 1
        else:
            res = feb_memoised(n - 1) + feb_memoised(n - 2)
            memo[n] = res
            return res
    
    return feb_memoised(n)

result, execution_time = find_feb_with_memo(19)
print(f"Result: {result}, Execution Time: {execution_time} seconds")
```

## Conclusion
Memoization significantly reduces computation time by storing previously computed results. This is evident from the comparison of execution times between the naive and memoized approaches.

---
