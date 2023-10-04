# Stack
> Its a LIFO data structure

> LIFO -> Last In First Out

![[Stack.png]]


- `empty()` – Returns whether the stack is empty – Time Complexity: O(1)
- `size()` – Returns the size of the stack – Time Complexity: O(1)
- `top() / peek()` – Returns a reference to the topmost element of the stack – Time Complexity: O(1)
- `push(a)` – Inserts the element ‘a’ at the top of the stack – Time Complexity: O(1)
- `pop()` – Deletes the topmost element of the stack – Time Complexity: O(1)
``` python
# Python program to
# demonstrate stack implementation
# using list

stack = []

# append() function to push
# element in the stack
stack.append('a')
stack.append('b')
stack.append('c')

print('Initial stack')
print(stack)

# pop() function to pop
# element from stack in
# LIFO order
print('\nElements popped from stack:')
print(stack.pop())
print(stack.pop())
print(stack.pop())

print('\nStack after elements are popped:')
print(stack)

# uncommenting print(stack.pop())
# will cause an IndexError
# as the stack is now empty
```

| Advantages (+) | Disadvantages (-)                                                                       |
| ---------- | ------------------------------------------------------------------------------------ |
|Simple, well-defined set of operations, easy to understand and use| Restrictions in size, can not add more elements if full                              |
|Efficient, adding and removing elements have time complexity O(1)| No fast access to elements other than the top element                                |
|Used to reverse order of elements (LIFO)| Searching not efficient, you have to pop elements one by one to find desired element |
|Can be used to implement undo/redo functions|                                                                                      |


# Queue

> Its a FIFO data structure -> First In First Out
> ex. A line of people

> Linear data structure

![[Queue.png]]

![[Queue 2.png]]
- **Enqueue:** Adds an item to the queue. If the queue is full, then it is said to be an Overflow condition – Time Complexity : O(1)
- **Dequeue:** Removes an item from the queue. The items are popped in the same order in which they are pushed. If the queue is empty, then it is said to be an Underflow condition – Time Complexity : O(1)
- **Front:** Get the front item from queue – Time Complexity : O(1)
- **Rear:** Get the last item from queue – Time Complexity : O(1)


``` python
# Python program to
# demonstrate queue implementation
# using list

# Initializing a queue
queue = []

# Adding elements to the queue
queue.append('a')
queue.append('b')
queue.append('c')

print("Initial queue")
print(queue)

# Removing elements from the queue
print("\nElements dequeued from queue")
print(queue.pop(0))
print(queue.pop(0))
print(queue.pop(0))

print("\nQueue after removing elements")
print(queue)

# Uncommenting print(queue.pop(0))
# will raise and IndexError
# as the queue is now empty
```

## Priority Queue
> FIFO data structure that serves elements with highest priorities first before elements with lower priority

> In a priority queue, each element has a priority value associated with it. When you add an element to the queue, it is inserted in a position based on its priority value.


**A Priority Queue is an extension of the queue with the following properties:

- Every item has a priority associated with it.
- An element with high priority is dequeued before an element with low priority.
- If two elements have the same priority, they are served according to their order in the queue.

- **enqueue():** This function is used to insert new data into the queue.
- **dequeue():** This function removes the element with the highest priority from the queue.
- **peek()/top():** This function is used to get the highest priority element in the queue without removing it from the queue.

|Arrays|enqueue()|dequeue()|peek()|
|---|---|---|---|
|Time Complexity|O(1)|O(n)|O(n)|

# Linked List
In an array, if an element at index 3 is deleted, then all the elements at indexes >3 must be moved one index down (in memory location they have to be next to each other)

![[Linked List.png]]

![[Linked List 2.png]]

##  t-Sets
also called union-finds or merge-finds

>Disjoint Sets -> Sets that have no elements in common
>also called mutually exclusive or independent

## Doubly Linked Lists
Traversal of items can be done in both forward and backward directions as every node contains an additional **prev** pointer that points to the previous node.
![[Doubly Linked List 2.png]]
![[Doubly Linked List.png]]


```python
class Node:
	def __init__(self,data):
		self.data = data
		self.next = None
		self.prev = None

class LinkedList:
	def __init__(self):
		self.head = None
	def search(self,target):
		current = self.head
		while current:
			if current.data == target:
				return current
			current = current.next
		return None
	def insert(self,node):
		node.next = self.head
		if self.head:
			self.head.prev = node
		self.head = node
		node.prev = None


```

> Disadvantage:
> Linked Lists take up a lot of memory

**Linked List vs. Array in Time Complexity**

|Operation|Linked list|Array|
|---|---|---|
|Random Access|O(N)|O(1)|
|Insertion and deletion at beginning|O(1)|(N)|
|Insertion and deletion at end|O(N)|O(1)|
|Insertion and deletion at a random position|O(N)|O(N)|
### **_Advantages of Linked Lists:_**

- **Dynamic nature:** Linked lists are used for dynamic memory allocation.
- **Memory efficient:** Memory consumption of a linked list is efficient as its size can grow or shrink dynamically according to our requirements, which means effective memory utilization hence, no memory wastage.
- **Ease of Insertion and Deletion:** Insertion and deletion of nodes are easily implemented in a linked list at any position.
- **Implementation:** For the implementation of stacks and queues and for the representation of trees and graphs.
- The linked list can be expanded in constant time.

### ***Disadvantages of Linked Lists:***

- **Memory usage:** The use of pointers is more in linked lists hence, complex and requires more memory.
- **Accessing a node:** Random access is not possible due to dynamic memory allocation.
- **Search operation costly:** Searching for an element is costly and requires O(n) time complexity.
- **Traversing in reverse order:** Traversing is more time-consuming and reverse traversing is not possible in singly linked lists. 

### ***Applications of Linked List:***

Here are some of the applications of a linked list:

- Linear data structures such as stack, queue, and non-linear data structures such as hash maps, and graphs can be implemented using linked lists.
- **Dynamic memory allocation:** We use a linked list of free blocks.
- **Implementation of graphs:** Adjacency list representation of graphs is the most popular in that it uses linked lists to store adjacent vertices.
- In web browsers and editors, doubly linked lists can be used to build a forwards and backward navigation button.
- A circular doubly linked list can also be used for implementing data structures like Fibonacci heaps.

### **_Applications of Linked Lists in real world:_**

- The list of songs in the music player is linked to the previous and next songs. 
- In a web browser, previous and next web page URLs are linked through the previous and next buttons.
- In the image viewer, the previous and next images are linked with the help of the previous and next buttons.
- Switching between two applications is carried out by using **“alt+tab**” in windows and “**cmd+tab**” in mac book. It requires the functionality of a circular linked list.
- In mobile phones, we save the contacts of people. The newly entered contact details will be placed at the correct alphabetical order.
- This can be achieved by a linked list to set contact at the correct alphabetical position.
- The modifications that we made in the documents are actually created as nodes in doubly linked list. We can simply use the undo option by pressing **Ctrl+Z** to modify the contents. It is done by the functionality of a linked list.


# Dynamic Array



>A Dynamic Array automatically grows when we try to make an insertion and there is no more space left for the new item. Usually the area doubles in size.

**Approach:** When we enter an element in array but array is full then you create a function, this function creates a new array double size or as you wish and copy all element from the previous array to a new array and return this new array.

| Advantages | Disadvantages      |
| ---------- | ------------------ |
| Random access of elements **O(1)** by index number | Wastes more memory |
| Good locality of reference and data cache utilization |  Shifting elements is time consuming O(n) |
| Easy to insert/delete at the end |  Expanding/Shrinking the array is time consuming **O(n)** (all elements have to be copied over to new array) |


# Hash Tables

>A Hash table is defined as a data structure used to insert, look up, and remove key-value pairs quickly. It operates on the hashing concept, where each key is translated by a hash function into a distinct index in an array. The index functions as a storage location for the matching value. **In simple words, it maps the keys with the value.**


![[Hash table.png]]

![[Hash Table 2.png]]


Hashing is a technique or process of mapping keys, and values into the hash table by using a hash function. It is done for faster access to elements. The efficiency of mapping depends on the efficiency of the hash function used.

Let a hash function H(x) maps the value **x** at the index **x%10** in an Array. For example if the list of values is [11,12,13,14,15] it will be stored at positions {1,2,3,4,5} in the array or Hash table respectively.

![[Hash Table 3.png]]

Some hash functions use modulo to determine index
## Complexity Analysis of a Hash Table:

For lookup, insertion, and deletion operations, hash tables have an average-case time complexity of O(1). Yet, these operations may, in the worst case, require O(n) time, where n is the number of elements in the table.

## Applications of Hash Table:

- Hash tables are frequently used for indexing and searching massive volumes of data. A search engine might use a hash table to store the web pages that it has indexed.
- Data is usually cached in memory via hash tables, enabling rapid access to frequently used information. 
- Hash functions are frequently used in cryptography to create digital signatures, validate data, and guarantee data integrity.
- Hash tables can be used for implementing database indexes, enabling fast access to data based on key values.