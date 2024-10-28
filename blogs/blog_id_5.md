# Understanding List Comprehensions in Python

## Introduction
List comprehensions are a concise way to create lists in Python. They provide a shorter syntax for generating a new list by applying an expression to each item in an iterable, often with an optional filtering condition.

## How List Comprehensions Work
List comprehensions consist of:
- **Expression**: The operation to apply to each element.
- **Iterable**: The data source (e.g., list, range).
- **Condition (optional)**: A filter that determines whether to include the element in the new list.

## Example
Here's a simple example that generates a list of squares for the numbers from 0 to 9:

```python
squares = [x**2 for x in range(10)]
print(squares)  
