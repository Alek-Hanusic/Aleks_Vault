# The  Random-Access Machine (RAM)

Algorithms can be measured in a machine-independent way using the Random Access Machine (RAM) model. This model assumes a single processor. In the RAM model, instructions are executed one after the other, with no concurrent operations. This model of computation is an abstraction that allows us to compare algorithms on the basis of performance. The assumptions made in the RAM model to accomplish this are

1. Each simple operation takes 1 time step.
2. Loops and subroutines are not simple operations.
3. Each memory access takes one time step, and there is no shortage of memory.

# Complexity
## Input size
We measure the complexity of an algorithm as a function of the size of the input .

## Worst-Case Complexity
In general we measure the complexity of an algorithm in the worst case and without making assumptions on the content of the input (e.g., is the input list sorted?)
Other types of analysis:
	• Best case Complexity
	• Average case Complexity

## Order of Growth
Rate of growth of T(n)
- We ignore lower-order terms in the formula
- Formulas dominated by higher-order terms grow at faster pace while increasing the value n

They (lower order) become more **insignificant** for large values of n.
