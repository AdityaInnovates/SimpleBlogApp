---

# Heap Sort Algorithm

### Difficulty: Medium  
**Topic**: Sorting Algorithms  
**Time Complexity**: O(n log n)  
**Space Complexity**: O(1)  

---

Heap Sort is a comparison-based sorting technique that uses a binary heap data structure. It builds a max heap (or min heap) and repeatedly extracts the maximum (or minimum) element to create a sorted array. The algorithm is efficient and performs well for large datasets.

---

### Algorithm

1. **Build the Heap**: 
   - Create a max heap from the input data. This step ensures that the largest element is at the root of the heap.
2. **Extract Elements**: 
   - Swap the root of the heap (maximum element) with the last element of the heap.
   - Reduce the size of the heap by one.
   - Heapify the root of the heap to maintain the max heap property.
3. **Repeat**: 
   - Continue the process until all elements are sorted.

---

### Input and Output

- **Input**: 
  - An array of integers to be sorted.
- **Output**:
  - A sorted array in ascending order.

---

### Example

#### Input
```python
Array: [12, 11, 13, 5, 6, 7]
```
#### Output
```python
Sorted Array: [5, 6, 7, 11, 12, 13]
```
---

## Solution

Below is a Python solution for the Heap Sort algorithm.

```python
def heapify(arr, n, i):
    largest = i  # Initialize largest as root
    left = 2 * i + 1  # left = 2*i + 1
    right = 2 * i + 2  # right = 2*i + 2

    # Check if left child exists and is greater than root
    if left < n and arr[left] > arr[largest]:
        largest = left

    # Check if right child exists and is greater than largest so far
    if right < n and arr[right] > arr[largest]:
        largest = right

    # Change root if needed
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]  # Swap

        # Heapify the root
        heapify(arr, n, largest)

def heap_sort(arr):
    n = len(arr)

    # Build a max heap
    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    # One by one extract elements from heap
    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]  # Swap
        heapify(arr, i, 0)

# Example usage
arr = [12, 11, 13, 5, 6, 7]
heap_sort(arr)
print("Sorted array is", arr)
```

---

### Pros and Cons

- **Pros**:
  - Efficient for large datasets.
  - Performs well in worst-case scenarios compared to other sorting algorithms.
  
- **Cons**:
  - More complex to implement compared to simpler algorithms like bubble sort.
  - Not stable (does not preserve the relative order of equal elements).

---

### Use Cases

- Suitable for applications where performance is critical.
- Used in implementing priority queues.
- Applicable in scenarios where the data is too large to fit into memory (external sorting).

---

### Additional Challenges

1. **Implement Min Heap**: Modify the algorithm to sort in descending order by implementing a min heap.
2. **Heap Sort with Duplicates**: Extend the algorithm to handle arrays with duplicate values while maintaining stability.

---