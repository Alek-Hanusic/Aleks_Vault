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
## Doubly Linked Lists
Traversal of items can be done in both forward and backward directions as every node contains an additional **prev** pointer that points to the previous node.
![[Doubly Linked List 2.png]]
![[Doubly Linked List.png]]


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


