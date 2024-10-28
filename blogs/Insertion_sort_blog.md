# Insertion Sort Algorithm

__Insertion sort__ is a sorting algorithm that places an unsorted element at its suitable place in each iteration.

Insertion sort works similarly as we sort cards in our hand in a card game.

We assume that the first card is already sorted then, we select an unsorted card. If the unsorted card is greater than the card in hand, it is placed on the right otherwise, to the left. In the same way, other unsorted cards are taken and put in their right place.

A similar approach is used by insertion sort.

###

# Working of Insertion Sort

Suppose we need to sort the following array.

![App Screenshot](https://github.com/user-attachments/assets/1593dee0-19c8-4c37-a303-4d377a34efe9)

1. The first element in the array is assumed to be sorted. Take the second element and store it separately in key.

Compare key with the first element. If the first element is greater than key, then key is placed in front of the first element.

![App Screenshot](https://github.com/user-attachments/assets/02717596-e533-4ca3-be51-67bae38ada58)

2. Now, the first two elements are sorted.  

Take the third element and compare it with the elements on the left of it. Placed it just behind the element smaller than it. If there is no element smaller than it, then place it at the beginning of the array.

![App Screenshot](https://github.com/user-attachments/assets/eb0f87c0-1400-4d18-8b03-d2038722ca44)

3. Similarly, place every unsorted element at its correct position.

![App Screenshot](https://github.com/user-attachments/assets/175f1181-c244-473b-afbd-1357098db3de)

![App Screenshot](https://github.com/user-attachments/assets/efad4578-daf1-480a-a6b9-f2a03c1d681b)

###

# Insertion Sort Algorithm

~~~
insertionSort(array)
  mark first element as sorted
  for each unsorted element X
    'extract' the element X
    for j <- lastSortedIndex down to 0
      if current element j > X
        move sorted element to the right by 1
    break loop and insert X here
end insertionSort
~~~

###

# Insertion Sort in Python

~~~python
# Insertion sort in Python


def insertionSort(array):

    for step in range(1, len(array)):
        key = array[step]
        j = step - 1
        
        # Compare key with each element on the left of it until an element smaller than it is found
        # For descending order, change key<array[j] to key>array[j].        
        while j >= 0 and key < array[j]:
            array[j + 1] = array[j]
            j = j - 1
        
        # Place key at after the element just smaller than it.
        array[j + 1] = key


data = [9, 5, 1, 4, 3]
insertionSort(data)
print('Sorted Array in Ascending Order:')
print(data)
~~~

# Insertion Sort Complexity

* Space Complexity:	O(1)
* Stability:	Yes

# Insertion Sort Applications

The insertion sort is used when:

* the array is has a small number of elements
* there are only a few elements left to be sorted






