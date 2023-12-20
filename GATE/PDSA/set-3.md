# GATE PDSA Set 3

## Question 1

Consider a sequence \(a\) of elements \(a_0 = 1\), \(a_1 = 5\), \(a_2 = 7\), \(a_3 = 8\), \(a_4 = 9\), and \(a_5 = 2\). The following operations are performed on a stack \(S\) and a queue \(Q\), both of which are initially empty.
1. Push the elements of \(a\) from \(a_0\) to \(a_5\) in that order into \(S\).
2. Enqueue the elements of \(a\) from \(a_0\) to \(a_5\) in that order into \(Q\).
3. Pop an element from \(S\).
4. Dequeue an element from \(Q\).
5. Pop an element from \(S\).
6. Dequeue an element from \(Q\).
7. Dequeue an element from \(Q\) and push the same element into \(S\).
8. Repeat operation 7 three times.
9. Pop an element from \(S\).
10. Pop an element from \(S\).

The top element of \(S\) after executing the above operations is _______.

### Answer
8

### Feedback
This sequence of operations manipulates the stack and queue in a specific order. By following the given steps, the top element of the stack \(S\) after executing all the operations is \(8\).

| Step | Operation                              | Stack \(S\)                | Queue \(Q\)          |
| ---- | -------------------------------------- | -------------------------- | -------------------- |
| 1    | Push elements of \(a\) to \(S\)        | \(1, 5, 7, 8, 9, 2\)       | Empty                |
| 2    | Enqueue elements of \(a\) to \(Q\)     | \(1, 5, 7, 8, 9, 2\)       | \(1, 5, 7, 8, 9, 2\) |
| 3    | Pop from \(S\)                         | \(1, 5, 7, 8, 9\)          | \(1, 5, 7, 8, 9, 2\) |
| 4    | Dequeue from \(Q\)                     | \(1, 5, 7, 8, 9\)          | \(5, 7, 8, 9, 2\)    |
| 5    | Pop from \(S\)                         | \(1, 5, 7, 8\)             | \(5, 7, 8, 9, 2\)    |
| 6    | Dequeue from \(Q\)                     | \(1, 5, 7, 8\)             | \(7, 8, 9, 2\)       |
| 7    | Dequeue from \(Q\) and push into \(S\) | \(1, 5, 7, 8, 7\)          | \(8, 9, 2\)          |
| 8    | Repeat operation VII three times       | \(1, 5, 7, 8, 7, 8, 9, 2\) | Empty                |
| 9    | Pop from \(S\)                         | \(1, 5, 7, 8, 7, 8, 9\)    | Empty                |
| 10   | Pop from \(S\)                         | \(1, 5, 7, 8, 7, 8\)       | Empty                |

Therefore, after executing these operations, the top element of stack \(S\) is \(8\).

## Question 2
Suppose a stack implementation supports an instruction REVERSE, which reverses the order of elements on the stack, in addition to the PUSH and POP instructions. Which one of the following statements is TRUE (with respect to this modified stack)?

### Choices 
- [ ] A queue cannot be implemented using this stack.
- [ ] A queue can be implemented where ENQUEUE takes a single instruction and DEQUEUE takes a sequence of two instructions.
- [x] A queue can be implemented where ENQUEUE takes a sequence of three instructions and DEQUEUE takes a single instruction.
- [ ] A queue can be implemented where both ENQUEUE and DEQUEUE take a single instruction each.

#### Feedback
With the REVERSE instruction, a queue can be implemented using this modified stack where ENQUEUE would require a sequence of three instructions (PUSH, REVERSE, PUSH), and DEQUEUE would require a single instruction (POP).

## Question 3
Consider the queues Q1 containing four elements and Q2 containing none (shown as the Initial State in the figure). The only operations allowed on these two queues are Enqueue(Q, element) and Dequeue(Q). The minimum number of Enqueue operations on Q1 required to place the elements of Q1 in Q2 in reverse order (shown as the Final State in the figure) without using any additional storage is___________.
```
Initial State:  
Q1: |1|2|3|4|  
Q2: | | | | |  

Final State:  
Q1: | | | | |  
Q2: |4|3|2|1|  
```

### Answer
0

### Feedback
The operations performed demonstrate the reversal of elements between Q1 and Q2 without using additional storage, achieving the Final State with the elements reversed in Q2 from the Initial State of Q1. 

| Step | Q1      | Q2      | Operation                |
| ---- | ------- | ------- | ------------------------ |
| 1    | 1,2,3,4 |         |                          |
| 2    | 2,3,4   | 1       | Enqueue(Dequeue(Q1), Q2) |
| 3    | 3,4     | 1,2     | Enqueue(Dequeue(Q1), Q2) |
| 4    | 3,4     | 2,1     | Enqueue(Dequeue(Q2), Q2) |
| 5    | 4       | 2,1,3   | Enqueue(Dequeue(Q1), Q2) |
| 6    | 4       | 1,3,2   | Enqueue(Dequeue(Q2), Q2) |
| 7    | 4       | 3,2,1   | Enqueue(Dequeue(Q2), Q2) |
| 9    |         | 3,2,1,4 | Enqueue(Dequeue(Q1), Q2) |
| 9    |         | 2,1,4,3 | Enqueue(Dequeue(Q2), Q2) |
| 10   |         | 1,4,3,2 | Enqueue(Dequeue(Q2), Q2) |
| 11   |         | 4,3,2,1 | Enqueue(Dequeue(Q2), Q2) |

From the above table it is clear that no Enqueue operation is performed on Q1. THus The minimum number of Enqueue operations on Q1 required is 0.

## Question 4

Consider the following sequence of operations on an empty stack:  
1. push(54)
2. push(52)
3. pop()
4. push(55)
5. push(62)
6. s = pop()

Consider the following sequence of operations on an empty queue:
1. enqueue(21)
2. enqueue(24)
3. dequeue()
4. enqueue(28)
5. enqueue(32)
6. q = dequeue()

The value of \(s + q\) is _______

### Answer
86

### Feedback

**Stack Operations**

| Operation   | Stack   |
|-------------|---------|
| push(54)    | [54]    |
| push(52)    | [54, 52]|
| pop()       | [54]    |
| push(55)    | [54, 55]|
| push(62)    | [54, 55, 62] |
| s = pop()   | \(s = 62\), Stack: [54, 55] |

**Queue Operations**

| Operation       | Queue   |
|-----------------|---------|
| enqueue(21)     | [21]    |
| enqueue(24)     | [21, 24]|
| dequeue()       | [24]    |
| enqueue(28)     | [24, 28]|
| enqueue(32)     | [24, 28, 32]|
| q = dequeue()   | \(q = 24\), Queue: [28, 32] |

Therefore, \(s = 62\) and \(q = 24\). The value of \(s + q\) is \(62 + 24 = 86\).

## Question 5

Let A be a priority queue for maintaining a set of elements. Suppose A is implemented using a max-heap data structure. The operation EXTRACT-MAX(A) extracts and deletes the maximum element from A. The operation INSERT(A, key) inserts a new element key in A. The properties of a max-heap are preserved at the end of each of these operations. When A contains n elements, which one of the following statements about the worst-case running time of these two operations is TRUE?

### Choices 
- [ ] Both EXTRACT-MAX(A) and INSERT(A, key) run in \(O(1)\).
- [x] Both EXTRACT-MAX(A) and INSERT(A, key) run in \(O(\log n)\).
- [ ] EXTRACT-MAX(A) runs in \(O(1)\) whereas INSERT(A, key) runs in \(O(n)\).
- [ ] EXTRACT-MAX(A) runs in \(O(1)\) whereas INSERT(A, key) runs in \(O(\log n)\).

### Feedback
In a max-heap:
- EXTRACT-MAX operation requires \(O(\log n)\) time as it involves reorganizing the heap to maintain its properties after removing the maximum element.
- INSERT operation also requires \(O(\log n)\) time to maintain the max-heap property by correctly placing the newly inserted element in the heap, considering it might need to traverse the height of the heap, which is \(O(\log n)\).

Therefore, both EXTRACT-MAX and INSERT operations run in \(O(\log n)\) time in the worst case scenario for a max-heap implementation.

## Question 6

Which one of the following sequences when stored in an array at locations \(A[1], \ldots, A[10]\) forms a max-heap?

### Choices 
- [ ] 23, 17, 10, 6, 13, 14, 1, 5, 7, 12
- [x] 23, 17, 14, 7, 13, 10, 1, 5, 6, 12
- [ ] 23, 17, 14, 6, 13, 10, 1, 5, 7, 15
- [ ] 23, 14, 17, 1, 10, 13, 16, 12, 7, 5

### Feedback
To form a max-heap, the elements must satisfy the heap property: every node should be greater than or equal to its children.

In the sequence B: 23, 17, 14, 7, 13, 10, 1, 5, 6, 12
When arranged in an array:
```
      23
     /   \
   17     14
  / \    /  \
 7  13  10   1
/ \  /
5 6 12
```
The sequence, when represented as a binary tree, follows the max-heap property. Therefore, sequence B forms a max-heap when stored in an array at locations \(A[1], \ldots, A[10]\).

## Question 7

Consider the array representation of a binary min-heap containing 1023 elements. The minimum number of comparisons required to find the maximum in the heap is_____.

### Answer
511

### Feedback
In a binary min-heap with 1023 (2^10-1) elements, the maximum elements will be at the leaves.
- Number of leaf nodes in a complete binary tree with 1023 elements is \(2^9 = 512\).
- To find the maximum element of 2 elements we need 1 comparison, for 3 elements - 2 comparisons, etc.
- To find the maximum element of 512 elements, the minimum number of comparison required is 511.

## Question 8

Consider the following statements:
I. The smallest element in a max-heap is always at a leaf node.
II. The second largest element in a max-heap is always a child of a root node.
III. A max-heap can be constructed from a binary search tree in \(\Theta(n)\) time.
IV. A binary search tree can be constructed from a max-heap in \(\Theta(n)\) time.
Which of the above statements are TRUE?

### Choices 
- [x] I, II and III
- [ ] I, II and IV
- [ ] I, III and IV
- [ ] II, III and IV

### Feedback
Let's evaluate each statement:

I. The smallest element in a max-heap is always at a leaf node.  
   - True. In a max-heap, the smallest element will be at a leaf node as all parent nodes have larger values than their children.

II. The second largest element in a max-heap is always a child of a root node.  
   - True. In a max-heap, the second largest element will be a child of the root node as it's among the children of the largest element (root).

III. A max-heap can be constructed from a binary search tree in \(\Theta(n)\) time.  
   - True. A max-heap can be constructed from a binary search tree in linear time complexity by performing heapify which takes \(\Theta(n)\) time.

IV. A binary search tree can be constructed from a max-heap in \(\Theta(n)\) time.  
   - False. It takes \(\Theta(n\log n)\) time

Therefore, the statements I, II, and III are TRUE.


## Question 9

Let H be a binary min-heap consisting of \(n\) elements implemented as an array. What is the worst-case time complexity of an optimal algorithm to find the maximum element in H?

### Choices 
- [ ] \(\Theta(1)\)
- [ ] \(\Theta(\log  n)\)
- [x] \(\Theta(n)\)
- [ ] \(\Theta(n \text{ log } n)\)

### Explanation
In a binary min-heap:
- The maximum element is always a leaf node in the heap, and to find the maximum element, we need to traverse all leaf nodes to identify the maximum among them.
- In the worst case, the number of leaf nodes in a binary heap is \(\lceil \frac{n}{2} \rceil\) (approximately half of the total nodes).
- Therefore, to find the maximum element in a binary min-heap, we need to perform a linear search among the leaf nodes, resulting in a time complexity of \(\Theta(n)\) in the worst case.
  

## Question 10

Consider the following array of elements 〈89, 19, 50, 17, 12, 15, 2, 5, 7, 11, 6, 9, 100〉. The minimum number of interchanges needed to convert it into a max-heap is

### Choices 
- [ ] 4
- [ ] 5
- [ ] 2
- [x] 3

### Explanation
The process of converting an array into a max-heap involves the process of heapification, which ensures that the max-heap property is satisfied.
For the given array:
```
Initially: [89, 19, 50, 17, 12, 15, 2, 5, 7, 11, 6, 9, 100]

89
├── 19
│   ├── 17
│   │   ├── 5
│   │   └── 7
│   └── 12
│       ├── 11
│       └── 6
└── 50
    ├── 15
    │   ├── 9
    │   └── 100
    └── 2
```
Only wrong entry is 100.

To make it a Max-heap:
```
1. Swap(100,15)
89
├── 19
│   ├── 17
│   │   ├── 5
│   │   └── 7
│   └── 12
│       ├── 11
│       └── 6
└── 50
    ├── 100
    │   ├── 9
    │   └── 15
    └── 2

2. Swap(100,50)
89
├── 19
│   ├── 17
│   │   ├── 5
│   │   └── 7
│   └── 12
│       ├── 11
│       └── 6
└── 100
    ├── 50
    │   ├── 9
    │   └── 15
    └── 2

3. Swap(100,89)
100
├── 19
│   ├── 17
│   │   ├── 5
│   │   └── 7
│   └── 12
│       ├── 11
│       └── 6
└── 89
    ├── 50
    │   ├── 9
    │   └── 15
    └── 2
```

Thus the number of interchanges required is 3.