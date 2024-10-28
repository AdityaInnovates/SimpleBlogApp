
# Bubble Sort

__Bubble sort__ is a sorting algorithm that compares two adjacent elements and swaps them until they are in the intended order.

Just like the movement of air bubbles in the water that rise up to the surface, each element of the array move to the end in each iteration. Therefore, it is called a bubble sort. 

# Working of Bubble Sort

Suppose we are trying to sort the elements in __ascending order__.

__1. First Iteration (Compare and Swap)__

* Starting from the first index, compare the first and the second elements.

* If the first element is greater than the second element, they are swapped.

* Now, compare the second and the third elements. Swap them if they are not in order.

* The above process goes on until the last element.


![Bubble-sort-0](https://github.com/user-attachments/assets/a06eeaa0-602d-46d7-9b26-6cf5b7fb6575)


__2. Remaining Iteration__

The same process goes on for the remaining iterations.

After each iteration, the largest element among the unsorted elements is placed at the end.

![Bubble-sort-1](https://github.com/user-attachments/assets/5a7d450e-a255-4a7e-bb1a-73a5eeb49125)

In each iteration, the comparison takes place up to the last unsorted element.

![Bubble-sort-2](https://github.com/user-attachments/assets/3615b536-70fb-482c-8a2d-e350cb251311)

The array is sorted when all the unsorted elements are placed at their correct positions.

![Bubble-sort-3](https://github.com/user-attachments/assets/08747a85-caa0-46d3-b5f7-f1718383243b)

# Bubble Sort Algorithm

~~~
bubbleSort(array)
  for i <- 1 to sizeOfArray - 1
    for j <- 1 to sizeOfArray - 1 - i
      if leftElement > rightElement
        swap leftElement and rightElement
end bubbleSort
~~~

# Bubble Sort Code in Python

~~~python
# Bubble sort in Python

def bubbleSort(array):
    
  # loop to access each array element
  for i in range(len(array)):

    # loop to compare array elements
    for j in range(0, len(array) - i - 1):

      # compare two adjacent elements
      # change > to < to sort in descending order
      if array[j] > array[j + 1]:

        # swapping elements if elements
        # are not in the intended order
        temp = array[j]
        array[j] = array[j+1]
        array[j+1] = temp


data = [-2, 45, 0, 11, -9]

bubbleSort(data)

print('Sorted Array in Ascending Order:')
print(data)
~~~

###

# Optimized Bubble Sort Algorithm

In the above algorithm, all the comparisons are made even if the array is already sorted.

This increases the execution time.

To solve this, we can introduce an extra variable swapped. The value of swapped is set true if there occurs swapping of elements. Otherwise, it is set __false__.

After an iteration, if there is no swapping, the value of swapped will be __false__. This means elements are already sorted and there is no need to perform further iterations.

This will reduce the execution time and helps to optimize the bubble sort.

# Algorithm for optimized bubble sort is

~~~
bubbleSort(array)
  for i <- 1 to sizeOfArray - 1
    swapped <- false
    for j <- 1 to sizeOfArray - 1 - i
      if leftElement > rightElement
        swap leftElement and rightElement
        swapped <- true
    if swapped == false
      break
end bubbleSort
~~~

###

# Optimized Bubble Sort in Python

~~~python
# Optimized Bubble sort in Python

def bubbleSort(array):
    
  # loop through each element of array
  for i in range(len(array)):
        
    # keep track of swapping
    swapped = False
    
    # loop to compare array elements
    for j in range(0, len(array) - i - 1):

      # compare two adjacent elements
      # change > to < to sort in descending order
      if array[j] > array[j + 1]:

        # swapping occurs if elements
        # are not in the intended order
        temp = array[j]
        array[j] = array[j+1]
        array[j+1] = temp

        swapped = True
          
    # no swapping means the array is already sorted
    # so no need for further comparison
    if not swapped:
      break

data = [-2, 45, 0, 11, -9]

bubbleSort(data)

print('Sorted Array in Ascending Order:')
print(data)
~~~

###

# Bubble Sort Complexity

* Space Complexity:	O(1)
* Stability:	Yes

###

# Bubble Sort Applications

Bubble sort is used if

* complexity does not matter
* short and simple code is preferred
