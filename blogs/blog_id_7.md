# Understanding Binary Search in Python

## Introduction
Binary Search is an efficient algorithm for finding an element in a sorted list. The binary search algorithm works by repeatedly dividing the search interval in half, which makes it faster than linear search, especially for large datasets.

## How Binary Search Works
In binary search, there are two main components:
- **Search Interval**: The range within which the search is conducted. Initially, the interval covers the entire array.
- **Middle Element Comparison**: The middle element of the interval is compared with the target value. If they match, the search is successful. If the target value is smaller, the search continues in the left half; if it's larger, the search continues in the right half.

### Key Points
- Binary search works only on sorted arrays.
- It has a time complexity of **O(log n)**, making it highly efficient.

## Example
Here’s a simple example of a binary search function that returns the index of a target value if it exists in a sorted array, or -1 if it doesn’t:

```python
def binary_search(arr, target):
    left, right = 0, len(arr) - 1  # Set initial search bounds

    while left <= right:
        mid = (left + right) // 2  # Find the middle index

        if arr[mid] == target:  # Target found
            return mid
        elif arr[mid] < target:  # Move to the right half
            left = mid + 1
        else:  # Move to the left half
            right = mid - 1

    return -1  # Target not found

# Example usage
array = [1, 3, 5, 7, 9, 11]
target = 7
result = binary_search(array, target)
print("Target found at index:", result)  # Output: Target found at index: 3