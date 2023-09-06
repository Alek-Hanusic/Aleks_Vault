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

>An algorithm is said to have a logarithmic time complexity when it reduces the size of the input data in each step (it don’t need to look at all values of the input data), for example:

> Good example is binary search

```python Code Block
def binary_search(data, value):  
	n = len(data)  
	left = 0  # we start from index 0 (left)  
	right = n - 1  # end is on the final index
	while left <= right:  
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