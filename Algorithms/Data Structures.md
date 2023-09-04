# Stack
> Its a LIFO data structure

> LIFO -> Last In First Out

![[Pasted image 20230904233736.png]]


> `empty()` – Returns whether the stack is empty – Time Complexity: O(1)
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

| Advantages | Disadvantages                                                                        |
| ---------- | ------------------------------------------------------------------------------------ |
|Simple, well-defined set of operations, easy to understand and use| Restrictions in size, can not add more elements if full                              |
|Efficient| No fast access to elements other than the top element                                |
|            | Searching not efficient, you have to pop elements one by one to find desired element |
|            |                                                                                      |

