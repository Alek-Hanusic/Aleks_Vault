# Stack
> Its a LIFO data structure

> LIFO -> Last In First Out

![[Stack.png]]


- `empty()` – Returns whether the stack is empty – Time Complexity: O(1)
- `size()` – Returns the size of the stack – Time Complexity: O(1)
- `top() / peek()` – Returns a reference to the topmost element of the stack – Time Complexity: O(1)
- `push(a)` – Inserts the element ‘a’ at the top of the stack – Time Complexity: O(1)
- `pop()` – Deletes the topmost element of the stack – Time Complexity: O(1)
```
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

- **Enqueue:** Adds an item to the queue. If the queue is full, then it is said to be an Overflow condition – Time Complexity : O(1)
- **Dequeue:** Removes an item from the queue. The items are popped in the same order in which they are pushed. If the queue is empty, then it is said to be an Underflow condition – Time Complexity : O(1)
- **Front:** Get the front item from queue – Time Complexity : O(1)
- **Rear:** Get the last item from queue – Time Complexity : O(1)


```
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

