>In an algorithm we look for (mostly) correctness and performance
# The  Random-Access Machine (RAM)

>Algorithms can be measured in a machine-independent way using the Random Access Machine (RAM) model. This model assumes a single processor. In the RAM model, instructions are executed one after the other, with no concurrent operations. This model of computation is an abstraction that allows us to compare algorithms on the basis of performance. The assumptions made in the RAM model to accomplish this are

1. Each simple operation takes 1 time step.
2. Loops and subroutines are not simple operations.
3. Each memory access takes one time step, and there is no shortage of memory.

# Complexity
The complexity of algorithms define their runtime performance: T(n)
**T(n)** is the number of basic execution steps to process input **n**
## Input size
We measure the complexity of an algorithm as a function of the size of the input .

## Worst-Case Complexity
>In general we measure the complexity of an algorithm in the worst case and without making assumptions on the content of the input (e.g., is the input list sorted?)
Other types of analysis:
	• Best case Complexity
	• Average case Complexity

## Asymptotic Notations
>Asymptotic notations are the mathematical notations used to describe the running time of an algorithm when the input tends towards a particular value or a limiting value.

*For example: In bubble sort, when the input array is already sorted, the time taken by the algorithm is linear i.e. the best case.*
## Order of Growth
Rate of growth of T(n)
- We ignore lower-order terms in the formula
- Formulas dominated by higher-order terms grow at faster pace while increasing the value n

They (lower order) become more **insignificant** for large values of n.

For instance, if given
![[Dominant Factor.png]]
We only consider the dominant factor which is **n<sup>2</sup>**
and we conclude that T(n) is a quadratic function in n

```python
def my_function(data):
    first_element = data[0]
    
    for value in data:
        print(value)
    
    for x in data:
        for y in data:
            print(x, y)
```

>Even that the operations in ‘my_function’ don’t make sense we can see that it has multiple time complexities: **O(1) + O(n) + O(n²)**. So, when increasing the size of the input data, the **bottleneck** of this algorithm will be the operation that takes **O(n²)**. Based on this, we can describe the time complexity of this algorithm as **O(n²)**.

## "Better" Algorithms
>An algorithm A1 is considered to be asymptotically more efficient than A2 if A1's ***worst-case*** running time has a lower order of growth than A2's.

Still, A1 might not always be more efficient than A2.

However, for large enough inputs, A1 will run more quickly in the worst case than A2

We study the asymptotic efficiency of algorithms and consider the size of the input in the limit
![[Fibonacci Algos.png]]
#  Notation
>We use notations to describe the running times of algorithms 
## Big-O Notation (O-notation)
"How code slows as data grows"

>Big-O notation represents the upper bound of the running time of an algorithm. Thus, it gives the ***worst-case*** complexity of an algorithm.

> Ignore smaller operations see (Order of Growth)
## Theta Notation (Θ-Notation):
>Theta notation encloses the function from above and below. Since it represents the upper and the lower bound of the running time of an algorithm, it is used for analyzing the ***average-case*** complexity of an algorithm.

## Omega Notation (Ω-Notation):

> Omega notation represents the lower bound of the running time of an algorithm. Thus, it provides the ***best case*** complexity of an algorithm.

# Time Complexity Examples

## Constant Time — O(1)

>An algorithm is said to have a constant time when it is not dependent on the input data (n).

```python
data = [1, 2, 9, 8, 3, 4, 7, 6, 5]

def get_first(data):  
return data[0]

print(get_first(data))
```


## Logarithmic Time — O(log n)

>An algorithm is said to have a logarithmic time complexity when it reduces the size of the input data in each step (it don’t need to look at all values of the input data).

> Good example is binary search:

```python Binary Search
def binary_search(data, value):  
	n = len(data)  
	left = 0  # we start from index 0 (left)  
	right = n - 1  # end is on the final index
	while left <= right:#Repeat the steps above until the value is found or the left bounder is equal or higher the right bounder.
		middle = (left + right) // 2  # find middle index
		if value < data[middle]:  # if it is less than middle value
			right = middle - 1  # end is now index left of middle
		elif value > data[middle]:  # if value higher than middle
			left = middle + 1  #start is right of middle index
		else:  
			return middle  # middle is the value we looked for
	raise ValueError('Value is not in the list')

if __name__ == '__main__':  
data = [1, 2, 3, 4, 5, 6, 7, 8, 9]  
print(binary_search(data, 8))


left = 0
right = 8
middle = 4
```

## Linear Time — O(n)

>An algorithm is said to have a linear time complexity when the running time increases at most linearly with the size of the input data. This is the best possible time complexity when the algorithm must examine all values in the input data.

Let’s take a look at the example of a linear search, where we need to find the position of an element in an unsorted list:

```python
def linear_search(data, value):  
	for index in range(len(data)):  # for each index
		if value == data[index]:  # check if value is the one
			return index  #if it is, return the value
	raise ValueError('Value not found in the list')  
  
if __name__ == '__main__':  
	data = [1, 2, 9, 8, 3, 4, 7, 6, 5]  
	print(linear_search(data, 7))
```

> Basically,  it runs through each value to see if it is the one we look for

## Quasilinear Time — O(n log n)
>An algorithm is said to have a quasilinear time complexity when each operation in the input data have a logarithm time complexity. It is commonly seen in sorting algorithms (e.g. mergesort, timsort, heapsort).

>A complex example, can be found in the Mergesort algorithm. Mergesort is an efficient, general-purpose, comparison-based sorting algorithm which has quasilinear time complexity, let’s see an example:

```python
def merge_sort(data):  
	if len(data) <= 1:  
		return  
  
	mid = len(data) // 2  
	left_data = data[:mid]  
	right_data = data[mid:]  
  
	merge_sort(left_data)  
	merge_sort(right_data)  
  
	left_index = 0  
	right_index = 0  
	data_index = 0  
  
	while left_index < len(left_data) and right_index < len(right_data):  
	if left_data[left_index] < right_data[right_index]:  
		data[data_index] = left_data[left_index]  
		left_index += 1  
	else:  
		data[data_index] = right_data[right_index]  
		right_index += 1  
	data_index += 1  
  
	if left_index < len(left_data):  
		del data[data_index:]  
		data += left_data[left_index:]  
	elif right_index < len(right_data):  
		del data[data_index:]  
		data += right_data[right_index:]  
  
if __name__ == '__main__':  
	data = [9, 1, 7, 6, 2, 8, 5, 3, 4, 0]  
	merge_sort(data)  
	print(data)
```

![[Mergesort.png]]

## Quadratic Time — O(n²)

>An algorithm is said to have a quadratic time complexity when it needs to perform a linear time operation for each value in the input data, for example:

```python
for x in data:  
	for y in data:  
		print(x, y)
```

>Bubble sort is a great example of quadratic time complexity since for each value it needs to compare to all other values in the list, let’s see an example:

```python
def bubble_sort(data):  
	swapped = True  
	while swapped:  
		swapped = False  
		for i in range(len(data)-1):  
			if data[i] > data[i+1]:  
				data[i], data[i+1] = data[i+1], data[i]  
				swapped = True  
  
if __name__ == '__main__':  
	data = [9, 1, 7, 6, 2, 8, 5, 3, 4, 0]  
	bubble_sort(data)  
	print(data)
```

## Exponential Time — O(2^n)

>An algorithm is said to have an exponential time complexity when the growth doubles with each addition to the input data set. This kind of time complexity is usually seen in brute-force algorithms.

As exemplified by Vicky Lai:

_In cryptography, a brute-force attack may systematically check all possible elements of a password by iterating through subsets. Using an exponential algorithm to do this, it becomes incredibly resource-expensive to brute-force crack a long password versus a shorter one. This is one reason that a long password is considered more secure than a shorter one._

Another example of an exponential time algorithm is the recursive calculation of [Fibonacci](https://en.wikipedia.org/wiki/Fibonacci_number) numbers:

```python
def fibonacci(n):  
    if n <= 1:  
        return n  
    return fibonacci(n-1) + fibonacci(n-2)
```

>A recursive function may be described as a function that calls itself in specific conditions. As you may have noticed, the time complexity of recursive functions is a little harder to define since it depends on how many times the function is called and the time complexity of a single function call.

>Using n= 4

![[Fibonacci.png]]


## Factorial — O(n!)

An algorithm is said to have a factorial time complexity when it grows in a factorial way based on the size of the input data, for example:

``` 
2! = 2 x 1 = 2  
3! = 3 x 2 x 1 = 6  
4! = 4 x 3 x 2 x 1 = 24  
5! = 5 x 4 x 3 x 2 x 1 = 120  
6! = 6 x 5 x 4 x 3 x 2 x 1 = 720  
7! = 7 x 6 x 5 x 4 x 3 x 2 x 1 = 5.040  
8! = 8 x 7 x 6 x 5 x 4 x 3 x 2 x 1 = 40.320
```

>A great example of an algorithm which has a factorial time complexity is the Heap’s algorithm, which is used for generating all possible permutations of _n_ objects.

```python
def heap_permutation(data, n):
    if n == 1:
        print(data)
        return
    
    for i in range(n):
        heap_permutation(data, n - 1)
        if n % 2 == 0:
            data[i], data[n-1] = data[n-1], data[i]
        else:
            data[0], data[n-1] = data[n-1], data[0]
    
if __name__ == '__main__':
    data = [1, 2, 3]
    heap_permutation(data, len(data))
```

Output:
```python
[1, 2, 3]  
[2, 1, 3]  
[3, 1, 2]  
[1, 3, 2]  
[2, 3, 1]  
[3, 2, 1]
```

# Search Algorithms
## Linear Search
> Time complexity O(n), it depends on the input size (list size) because it has to check each individual value

```python
def search(list,n):
	index = 0
	while index < len(list):
		if list[index] == n
			return True
		index = index + 1
	return False
```

```python
def linear_search(list, target):
	i = 0
	for i in range(0, len(list)):
		if list[i] == target:
			return i
	return False
```

```python
list = [1,2,3,4,5,6,7,8]
def binary_search(list,target):
	start = 0
	end = len(list) - 1
	while start <= last:
		midpoint = (start+end)//2
		if list[midpoint] == target:
			return midpoint
		if list[midpoint] < target:
			end = midpoint -1
		if list[midpoint] > target:
			start = midpoint +1
```

# Sorting Algorithms

## Selection Sort

>Selection sort is a simple sorting algorithm that works by repeatedly selecting the minimum element from the unsorted portion of the array and swapping it with the first element of the unsorted portion.

>The time complexity of selection sort is O(n^2), where n is the number of elements in the array.

It involves two nested loops. The outer loop runs n times (for n elements), and the inner loop runs n - 1 times on average (for the remaining unsorted elements).

## Double Selection Sort

>Bidirectional selection sort is a variation of selection sort that works by selecting both the minimum and maximum elements from the unsorted portion of the array in each pass and swapping them with the first and last elements of the unsorted portion, respectively.

>The time complexity of bidirectional selection sort is also O(n^2), where n is the number of elements in the array.

 Like regular selection sort, bidirectional selection sort also involves two nested loops. The outer loop runs n/2 times (approximately), and the inner loop runs n - 1 times on average for each half of the unsorted portion.

***Both selection sort and bidirectional selection sort have quadratic time complexities, making them inefficient for large datasets. They are primarily used for educational purposes or in situations where simplicity is more important than efficiency. For larger datasets, more efficient sorting algorithms like merge sort, quicksort, or heap sort are typically preferred.***

## Insertion Sort

```pseudocode
for i: 1 to length(A)-1
	j = i
	while j>0 and A[j-1]>A[j]
		swap A[j] and A[j-1]
	j = j-1
```


>Insertion sort is a simple sorting algorithm that builds the final sorted array one item at a time.

>The time complexity of insertion sort is also **O(n^2)**, where n is the number of elements in the array.

>It involves two nested loops. The outer loop runs n times (for n elements), and the inner loop runs on average n/2 times for each element in the worst case scenario.

Insertion sort is similar in time complexity to selection sort and is considered inefficient for large datasets. However, it has some advantages over selection sort, such as being adaptive (meaning it performs well on partially sorted data) and stable (it maintains the relative order of equal elements).


## Bubble Sort
>Algorithmic Steps:

1. Start at the beginning of the list.
2. Compare the first two elements. If they are out of order, swap them.
3. Move to the next pair of elements and repeat the comparison and swap process until you reach the end of the list.
4. After one pass through the list, the largest element will "bubble" to the end of the list.
5. Repeat the above steps for the remaining unsorted portion of the list, excluding the elements already sorted in previous passes.
6. Continue these passes until no swaps are needed, indicating that the list is fully sorted.
![[Bubble_sort.gif]]
> Worst case time complexity of **O(n^2)**


## Merge sort
>Uses **divide and conquer strategy**


>**Algorithmic Steps:**

- **Divide:** The unsorted list is divided into two (or more) sublists of roughly equal size.
- **Conquer:** Each sublist is recursively sorted using the merge sort algorithm.
- **Merge:** The sorted sublists are then merged back together to produce a single sorted list. This merging step is where the algorithm gets its name.

**Space Complexity:** Merge sort is not an in-place sorting algorithm, meaning it requires additional memory to store the sublists during the sorting process. The space complexity is O(n), as it needs temporary storage for the sublists being merged.

>**Time Complexity:** Merge sort guarantees a time complexity of O(n log n), where n is the number of elements in the list.

```python
# Define a function for merge sort that takes an input list of integers.
def merge_sort(lst):
    # Get the length of the input list.
    list_length = len(lst)
    
    # Base case: If the list has only one element or is empty, it is already sorted.
    if list_length == 1:
        return lst
    
    # Calculate the midpoint of the list.
    mid_point = list_length // 2
    
    # Recursively apply merge_sort to the left and right halves of the list.
    left_half = merge_sort(lst[:mid_point])
    right_half = merge_sort(lst[mid_point:])
    
    # Merge the sorted left and right halves and return the result.
    return merge(left_half, right_half)

# Define a function to merge two sorted lists.
def merge(left, right):
    # Initialize an empty list to store the merged result.
    output = []
    
    # Initialize two pointers (i and j) for the left and right lists.
    i = j = 0
    
    # Compare elements from both lists and merge them in sorted order.
    while (i < len(left) and j < len(right)):
        if left[i] < right[j]:
            output.append(left[i])
            i += 1
        else:
            output.append(right[j])
            j += 1
    
    # Append any remaining elements from both lists (if any).
    output.extend(left[i:])
    output.extend(right[j:])
    
    # Return the merged and sorted list.
    return output

# Create an unsorted list of integers.
unsorted_list = [2, 4, 1, 5, 7, 2, 6, 1, 1, 6, 4, 10, 33, 5, 7, 23]

# Apply merge_sort to the unsorted list to obtain a sorted list.
sorted_list = merge_sort(unsorted_list)

# Print the original unsorted list and the sorted list.
print("Original Unsorted List:", unsorted_list)
print("Sorted List:", sorted_list)
```



# Cheat Sheets

![[Data Structure Operations.png]]

![[Sorting Algorithms.png]]1