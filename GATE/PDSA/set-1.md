# PDSA Set 1

## Question 1
**Tags:** GATE-2019(modified), Python Programming, Control Flow

Consider the following Python program:

```python=
sum_value = 0.0
j = 1.0
i = 2.0

while i / j > 0.0625:
    j = j + j
    sum_value = sum_value + i / j
    print(sum_value)

```

The number of times the variable `sum_value` will be printed when the above program is executed is ________

### Answer
5

### Feedback
The variable `sum_value` will be printed 5 times when the program is executed. This is because the program uses a while loop, and the condition `i / j > 0.0625` is checked in each iteration. The loop continues until this condition becomes false. Analyzing the values of `i` and `j` in each iteration, we can see that it is printed in the first 5 iterations:

1. `j = 1.0`, `i/j = 2.0/1.0 > 0.0625` (True, Printed)
2. `j = 2.0`, `i/j = 2.0/2.0 > 0.0625` (True, Printed)
3. `j = 4.0`, `i/j = 2.0/4.0 > 0.0625` (True, Printed)
4. `j = 8.0`, `i/j = 2.0/8.0 > 0.0625` (True, Printed)
5. `j = 16.0`, `i/j = 2.0/16.0 > 0.0625` (True, Printed)

After the 5th iteration, the condition becomes false, and the loop exits. Hence, `sum_value` is printed 5 times.


## Question 2

**Tags:** GATE-2017(modified), Python Programming, Control Flow

Consider the Python program fragment below, which is meant to divide `x` by `y` using repeated subtractions. The variables `x`, `y`, `q`, and `r` are all unsigned int.
```python
while r >= y:
    r = r - y
    q = q + 1
```
Which of the following conditions on the variables `x`, `y`, `q`, and `r` before the execution of the fragment will ensure that the loop terminates in a state satisfying the condition `x == (y * q + r)`?

### Choices
- [ ] q == r and r == 0
- [x] x > 0 and r == x and y > 0
- [ ] q == 0 and r == x and y > 0
- [ ] q == 0 and y > 0

### Feedback

To ensure that the loop terminates with the condition `x == (y * q + r)`, the following conditions must hold:

- `x` must be greater than 0.
- `r` must be equal to `x`.
- `y` must be greater than 0.

These conditions are met in `x > 0 and r == x and y > 0`


## Question 3

**Tags:** GATE-2021, Data Structures, Graphs

In an undirected connected planar graph G, there are eight vertices and five faces. The number of edges in G is __________.

### Answer
11

### Feedback
In a connected planar graph, the relationship between the number of vertices ($n$), edges ($e$), and faces ($r$) is given by Euler's formula:

$r = e - n + 2$

Given that $n = 8$ and $r = 5$:

$5 = e - 8 + 2$

Solving for $e$:

$e = 11$

Therefore, the number of edges in graph G is indeed 11, satisfying Euler's formula for a connected planar graph.


## Question 4

**Tags:** GATE 2021, Algorithms, Sorting

What is the least number of comparisons required among the array elements to sort the given array in ascending order using the following sorting algorithms?

| 23 | 32 | 45 | 69 | 72 | 73 | 89 | 97 |
|-|-|-|-|-|-|-|-|


### Choices
- [ ] Quicksort using the last element as a pivot
- [ ] Selection sort
- [ ] Mergesort
- [x] Insertion sort

### Feedback
The given array is already sorted. Insertion sort takes the least number of comparisons $O(n)$ in this case because, for a number to be inserted into an already sorted array, only one comparison is required. Hence, Insertion sort uses the least number of comparisons in this scenario.


## Question 5

**Tags:** GATE-2021(modified), Python Programming, Control flow

Consider the following Python function:

```python
def simple_function(Y, n, x):
    total = Y[0]
    for loop_index in range(1, n):
        total = x * total + Y[loop_index]
    return total
```

Let `Z` be an array of 10 elements with `Z[i] = 1`, for all `i` such that $0 \leq i \leq 9$. The value returned by `simple_function(Z, 10, 2)` is __________.

### Answer
1023

### Feedback


Given that all values in the array `Z` are 1 and `x = 2`, the function simplifies to `total = 2 * total + 1`, resulting in successive left shifting of the total by one bit and adding 1 each time. This process leads to a final value of 1023.
| Total in bits | Total Value |
|------------|-------------|
| 1          | 1           |
| 10 + 1 = 11| 3           |
| 110 + 1 = 111| 7         |
| 1110 + 1 = 1111| 15      |
| 11110 + 1 = 11111| 31   |
| 111110 + 1 = 111111| 63|
| 1111110 + 1 = 1111111| 127|
| 11111110 + 1 = 11111111| 255|
| 111111110 + 1 = 111111111| 511|
| 1111111110 + 1 = 1111111111| 1023|


## Question 6

**Tags:** GATE-2021, Data Structures, Heaps

Let H be a binary min-heap consisting of n elements implemented as an array. What is the worst case time complexity of an optimal algorithm to find the maximum element in H?

### Choices
- [ ] $\Theta(1)$
- [ ] $\Theta(\log n)$
- [x] $\Theta(n)$
- [ ] $\Theta(n \log n)$

### Feedback
The largest element in a min-heap will always be found at a leaf node since every node in a min-heap satisfies the property that its value is smaller than its children's values. The largest element can't have any children, making it reside in a leaf node. In a heap with $n$ elements, there are approximately $\frac{n}{2}$leaf nodes. To find the maximum among these leaves, it would take $\Theta(\frac{n}{2})$ operations, which simplifies to $\Theta(n)$.


## Question 7

**Tags:** GATE-2021, Data Structures, Trees

Consider a complete binary tree with 7 nodes. Let $A$ denote the set of first 3 elements obtained by performing Breadth-First Search (BFS) starting from the root. Let $B$ denote the set of first 3 elements obtained by performing Depth-First Search (DFS) starting from the root. The value of $|A - B|$ is _________.

### Answer
$1$

### Feedback

![image](https://hackmd.io/_uploads/S1Lh9BiV6.png)

Breadth-First Search = $1,2,3,4,5,6,7$  
Depth-First Search = $1,2,4,5,3,6,7$  

$A = \{1, 2, 3\}$  
$B = \{1, 2, 4\}$  

$A - B = \{3\}$  

Hence, the value of $|A - B|$ will be $1$ after performing the said operation on a complete binary tree.


## Question 8

**Tags:** GATE-2021, Algorithms, Search

What is the number of arithmetic operations required to implement binary search on a sorted array?

### Choices
- [ ] $ϴ(n)$
- [x] $ϴ(\log n)$
- [ ] $ϴ(1)$
- [ ] $ϴ(n^2)$

### Feedback
The number of arithmetic operations in binary search is related to the number of iterations in the loop. In the case of binary search, the while loop continues until the `beg` index is less than or equal to the `end` index. The arithmetic operation within the loop, `m = (l + h) / 2`, occurs with each iteration. 

```c
while (beg <= end) {
    m = (l + h) / 2;
    // ...other operations...
}
```

As the loop runs in $ϴ(\log n)$ time due to halving the search space at each step, the number of arithmetic operations is also $ϴ(\log n)$. Therefore, the correct option is $ϴ(\log n)$.




## Question 9

**Tags:** GATE-2021, Data Structures, Graph

Let $G$ be a connected undirected weighted graph. Consider the following two statements.

S1: There exists a minimum weight edge in $G$ which is present in every minimum spanning tree of $G$.

S2: If every edge in $G$ has distinct weight, then $G$ has a unique minimum spanning tree.

Which one of the following options is correct?

### Choices
- [x] $S1$ is false and $S2$ is true
- [ ] Both $S1$ and $S2$ are false
- [ ] $S1$ is true and $S2$ is false
- [ ] Both $S1$ and $S2$ are true

### Feedback

The Kruskal's algorithm can be used to discover the Minimum Spanning Tree on a graph $G$. When implementing Kruskal's algorithm, edges are sorted by weight, and the smallest edge is chosen first. However, $S1$ is false because the Kruskal's method may not always choose a particular weighted edge if there are multiple copies of it. It does not guarantee the selection of a specific minimum weight edge present in every minimum spanning tree.

$S2$ is True. Kruskal's algorithm will always choose a distinct set of edges, resulting in a distinct minimal spanning tree if the sorted order of the edges contains only distinct values due to its reliance on sorting and selecting edges with distinct weights.

## Question 10

**Tags:** GATE-2014, Data Structures, Linked List  

What is the worst-case time complexity of inserting $n$ elements into an empty linked list, maintaining sorted order?

### Choices
- [ ] $\Theta(n)$
- [ ] $\Theta(n \log n)$
- [x] $\Theta(n^2)$
- [ ] $\Theta(1)$

### Feedback

Consider a sorted list where inserting an element requires traversing till the end, necessitating comparisons equal to the number of elements in the worst case.

For the 1st element, no comparison is needed.
For the 2nd element, 1 comparison is needed.
And so on, until the $n$th element requiring $(n - 1)$ comparisons.

The total comparisons needed to insert $n$ elements is the sum of the first $n - 1$ natural numbers, given by:
$$ 1 + 2 + \ldots + (n - 1) = \frac{n(n - 1)}{2} = O(n^2) $$

Therefore, in the worst case, the time complexity of inserting $n$ elements into a sorted linked list is $\Theta(n^2)$.