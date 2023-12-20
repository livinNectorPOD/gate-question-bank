


# GATE PDSA  Set 2

## Question 1

**Tags**: GATE-2019 (modified), 

Consider the following python program:
```python
def jumble(x, y):
    x = 2 * x + y
    return x

x,y = 2,5
y = jumble(y, x)
x = jumble(y, x)
print(x)
```

### Answer
26

### Feedback

1. Initially, in the `main()` function, `x = 2` and `y = 5`.
2. `y` is updated to `jumble(5, 2)`, which evaluates to $2 \times 5 + 2 = 12$.
3. Subsequently, `x` is updated to `jumble(12, 2)`, which evaluates to $2 \times 12 + 2 = 26$.
4. Therefore, the final value of `x` printed by the program is $26$.

## Question 2

**Tags**: GATE-2018 (modified), Algorithms, recursion

Consider the following program written in pseudo-code. Assume that `x` and `y` are integers:
```
Count(x, y) {
    if (y != 1) {
        if (x != 1) {
            print(“*”);
            Count(x/2, y);
        } else {
            y = y – 1;
            Count(1024, y);
        }
    }
}
```

The number of times that the print statement is executed by the call Count$(1024, 1024)$ is _____.

### Answer
10230

#### Feedback
For the call `Count(1024, 1024)`, the program initiates with $(x, y) = (1024, 1024)$. 

The print statement inside the `Count` function executes when $x$ is not $1$. Starting with $x = 1024$ and continuously dividing it by $2$ until it becomes $1$.

```
x = 1024 -> 512 -> 256 -> 128 -> 64 -> 32 -> 16 -> 8 -> 4 -> 2 (10 times)  
```
The `else` part inside the `Count` function reduces $y$ by $1$ and recursively calls `Count(1024, y)`. This reduction continues until $y$ becomes $1$. 

```
y = 1024 -> ... -> 2 ( 1023 times)   
```

Hence, the total number of executions of the print statement is $1023 \times 10 = 10230$.

## Question 3

**Tags**: GATE-2023 (modified), Python programming, recursion

Consider the following program:

```python
def main():
    f1()
    f2(2)
    f3()
    return 0

def f1():
    return 1

def f2(X):
    f3()
    if X == 1:
        return f1()
    else:
        return X * f2(X - 1)

def f3():
    return 5

main()
```

Which one of the following options represents the activation tree corresponding to the main function?

### Choices 
- [x] _
    ```
    main
    ├── f1
    ├── f2
    │   ├── f3
    │   └── f2
    │       ├── f3
    │       └── f1
    └── f3
    ```
- [ ] _
    ```
    main
    ├── f1
    ├── f2
    │   ├── f3
    │   └── f1
    └── f3
    ```
- [ ] _
    ```
    main
    ├── f1
    ├── f2
    │   ├── f3
    │   └── f1
    └── 
    ```
- [ ] _
    ```
    main
    ├── f1
    ├── f2
    │   ├── f3
    │   ├── f2
    │   └── f1
    └── f3
    ```

### Feedback

- main calls `f1`, `f2` and `f3`. and `f1` and `f3` returns.
- In `f2`, `f3` is called and `f2` is called again with `X=1` as the condition goes to else part.
- In the new `f2`, `f3` is called and `f1` is called end the calls end there.

## Question 4

What is the worst-case time complexity of inserting $n$ elements into an empty linked list, if the linked list needs to be maintained in sorted order?

### Choices 
- [ ] $ \Theta(n \log n) $
- [ ] $ \Theta(n) $
- [ ] $ \Theta(1) $
- [x] $ \Theta(n^2) $

#### Feedback
The total number of comparisons needed to insert $n$ elements into a sorted linked list can be computed as the sum of the first $n - 1$ natural numbers: $1 + 2 + 3 + \dots + (n - 1) = \frac{n(n - 1)}{2}$. This is of the order $O(n^2)$, which means it is also $\Omega(n^2)$ and therefore $\Theta(n^2)$.

## Question 5

Consider the following python function:
```python 
def fun(n):
    for i in range(1, n + 1):
        j = 1
        while j < n:
            print(i, j)
            j += i

```

Time complexity of `fun` in terms of $ \Theta $ notation is

### Choices 
- [ ] $ \Theta(n^n) $
- [ ] $ \Theta(n^2) $
- [x] $ \Theta(n \log n) $
- [ ] $ \Theta(n^2 \log n) $

#### Feedback
The outer loop runs $n$ times, and the inner loop runs $\frac{n}{i}$ times for each value of $i$ from $1$ to $n$. Therefore, the total number of iterations is approximately $\sum_{i=1}^{n} \frac{n}{i}$, which is $n \log n$. Hence, the time complexity of `fun` is $ \Theta(n \log n) $.


## Question 6

Consider the following C function:

```python
def fun1(n):
    q = 0
    for i in range(1, n):
        p = 0
        j = n
        while j > 1:
            p += 1
            j //= 2
        
        k = 1
        while k < p:
            q += 1
            k *= 2
            
    return q

```

Which one of the following most closely approximates the return value of the function `fun1`?

### Choices 
- [ ] $n^3$
- [ ] $n(\log n)^2$
- [ ] $n \log n$
- [x] $n \log(\log n)$

#### Feedback
The outer loop runs $n - 1$ times. The first inner loop increments $p$ until $j$ becomes $1$, which takes $\log n$ iterations. The second inner loop increments $q$ until $k$ reaches $p$, which takes $\log p$ iterations. Therefore, the return value $q$ is closely approximated by $n \log(\log n)$.

## Question 7

Two alternative packages A and B are available for processing a database having $10k$ records. Package A requires $0.0001n^2$ time units, and package B requires $10n \log_{10} n$ time units to process $n$ records. What is the smallest value of $k$ for which package B will be preferred over A?

### Choices 
- [ ] $12$
- [ ] $10$
- [x] $6$
- [ ] $5$

#### Feedback
To determine when package B is preferred over package A, we set up the inequality:
$$10n \log_{10} n < 0.0001n^2k$$

Solving for $k$:
$$10 \cdot 10^4 \cdot 2^{-k} < k$$

By observation, when $k = 6$, $10 \cdot 10^4 \cdot 2^{-6} = \frac{10^5}{64} < 6$. Thus, $k$ needs to be at least $6$ for package B to be preferred over package A.

## Question 8

The running time of an algorithm is represented by the following recurrence relation:

$$ T(n) = \begin{cases} T\left(\frac{n}{3}\right) + cn & \text{if } n > 1 \\ T(1) & \text{otherwise} \end{cases} $$

Which of the following represents the time complexity of the algorithm?

### Choices 
- [x] $ \Theta(n) $
- [ ] $ \Theta(n \log n) $
- [ ] $ \Theta(n^2) $
- [ ] $ \Theta(n^2 \log n) $

#### Feedback
Using the master theorem to determine the time complexity:

Given:
- $a = 1$
- $b = 3$
- $f(n) = cn$

Master theorem conditions:
- $cn$ is $O(n^{0 - \epsilon})$ - Dissatisfied
- $cn$ is $O(n^{\log_3 1})$ - Dissatisfied
- $cn$ is $\Omega(n^{0 + \epsilon})$ - Satisfied

As $f(n/b) \leq \delta \cdot f(n)$ for $\delta = 1$:
$$ \frac{1 \cdot cn}{3} \leq 1 \cdot cn $$
$$ \frac{cn}{3} \leq cn $$
$$ \text{As } 3 < 1, \text{ the condition is not met.} $$

Hence, by the master theorem, $T(n)$ is $\Theta(n)$.

## Question 9

Consider the following recurrence relation:

$$ T(n) = \begin{cases} T\left(\frac{n}{2}\right) + T\left(\frac{2n}{5}\right) + 7n & \text{if } n > 0 \\ 1 & \text{if } n = 0 \end{cases} $$

Which one of the following options is correct?

### Choices 
- [ ] $T(n) = \Theta(n \log n)$
- [ ] $T(n) = \Theta(n^{5/2})$
- [x] $T(n) = \Theta(n)$
- [ ] $T(n) = \Theta(\log n)^{5/2}$

#### Feedback
Expanding the recurrence relation:

$$ T(n) = T\left(\frac{n}{2}\right) + T\left(\frac{2n}{5}\right) + 7n, \text{ if } n > 0 $$

Solving this recursively and analyzing the total time:

The total time complexity sums up to $O(n) = \Omega(n) = \Theta(n)$. Therefore, $T(n)$ has a time complexity of $\Theta(n)$.

## Question 10

Consider the recurrence function $T(n)$:

$$ T(n) = \begin{cases} 2T\left(\frac{n}{2}\right) + 1 & \text{if } n > 2 \\ 2 & \text{if } n \leq 2 \end{cases} $$

Then $T(n)$ in terms of $ \Theta $ notation is?

### Choices 
- [ ] $ \Theta(\log \log n) $
- [x] $ \Theta(\log n) $
- [ ] $ \Theta(n) $
- [ ] $ \Theta(n^2) $

#### Feedback
Breaking down the recurrence relation and solving for $T(n)$:

Given:
$$ T(n) = 2T\left(\frac{n}{2}\right) + 1 $$

1. $T(n) = 2T\left(\frac{n}{2}\right) + 1$ ... (1)
2. $T\left(\frac{n}{2}\right) = 2T\left(\frac{n}{4}\right) + 1$ ... (2)
3. $T(n) = 2[2T\left(\frac{n}{4}\right) + 1] + 1 = 4T\left(\frac{n}{4}\right) + 3$ ... (3)
4. $T\left(\frac{n}{2}\right) = 2T\left(\frac{n}{2^K}\right) + 1$ ... (4)
5. $K = \frac{1}{2} \cdot \log_2 n \Rightarrow 2^K = \sqrt{n}$
6. $T(n) = \log n \cdot T(2) + \log n - 1 = 2\log n + \log n - 1 = \Theta(\log n)$

Therefore, $T(n)$ in terms of $ \Theta $ notation is $ \Theta(\log n) $.

