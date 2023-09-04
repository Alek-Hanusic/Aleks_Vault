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
![[Stack.png]]
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

>Big-O notation represents the upper bound of the running time of an algorithm. Thus, it gives the ***worst-case*** complexity of an algorithm.

## Theta Notation (Θ-Notation):
>Theta notation encloses the function from above and below. Since it represents the upper and the lower bound of the running time of an algorithm, it is used for analyzing the ***average-case*** complexity of an algorithm.

## Omega Notation (Ω-Notation):

> Omega notation represents the lower bound of the running time of an algorithm. Thus, it provides the ***best case*** complexity of an algorithm.

