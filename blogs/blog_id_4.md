# Understanding Recursion in Python

## Introduction
Recursion is a powerful tool in programming that allows a function to call itself. This method is used to solve problems that can be broken down into smaller, simpler subproblems.

## How Recursion Works
In a recursive function, there are typically two main components:
- **Base Case**: The condition under which the recursion stops.
- **Recursive Case**: The part of the function where the function calls itself with a smaller or simpler input.

## Example
Here’s a simple example of a recursive function that calculates the factorial of a number:

```python
def factorial(n):
    if n == 0:
        return 1 
    else:
        return n * factorial(n - 1)  
