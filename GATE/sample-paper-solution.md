
# Gate Sample paper solutions

## Question 1

Let $\bf{b}$ be the branching factor of a search tree. If the optimal goal is reached after $\bf{d}$ actions from the initial state, in the worst case, how many times will the initial state be expanded for iterative deepening depth-first search (IDDFS) and iterative Deepening A* search (IDA*)?

### Options
- [x] (A) IDDFS - $d$, IDA* - $d$.
- [ ] (B) IDDFS - $d$, IDA* - $\bf{b}^{\bf{d}}$.
- [ ] (C) IDDFS - $\bf{b}^{\bf{d}}$, IDA* - $d$.
- [ ] (D) IDDFS - $\bf{b}^{\bf{d}}$, IDA* - $\bf{b}^{\bf{d}}$.

### Solution

A) IDDFS - $d$, IDA* - $d$.


## Question 2

Given 3 literals $A$, $B$, and $C$, the number of models for the sentence $A \lor \lnot B \lor C$ is ________. 

### Solution

8

Since 3 Boolean variables are there, totally $2^3= 8$ models.

## Question 3

Which one of the following first-order logic sentences matches closest with the sentence “All students are not equal”?

### Options
- [x] (A) $\forall x \exists y [Student(x) \land Student(y)] \Rightarrow \lnot Equal(x, y)$
- [ ] (B) $\forall x \forall y [Student(x) \land Student(y)] \Rightarrow \lnot Equal(x, y)$
- [ ] (C) $\forall x \exists y [Student(x) \land Student(y) \land \lnot Equal(x, y)]$
- [ ] (D) $\forall x \forall y [Student(x) \land Student(y) \land \lnot Equal(x, y)]$

### Solution

A) $\forall x \exists y[\text{student}(x) \wedge \text{student}(y)] \Rightarrow \neg \text{Equal}(x, y)$

- This translates to for all student x, there exists a student y who is different from him. Thus all students are not equal.

## Question 4

The mean of the observations of the first 50 observations of a process is 12. If the 51st observation is 18, then, the mean of the first 51 observations of the process, rounded off to two decimal places is ______.

### Options
- [ ] (A) 12.01
- [x] (B) 12.12
- [ ] (C) 12.36
- [ ] (D) 18.18

### Solution

B) 12.12

$$
\begin{align*}
\text{mean of 50 observations} &= 12 \\
\text{sum of 50 observations} &= 12 * 50  = 600 \\
\text{sum of 51 observations} &= 600 + 18 = 618 \\
\text{mean of 51 observations} &= 618/51 = 12.117 \approx 12.12 \\
\end{align*}
$$

## Question 5

The value of $\lim_{x\to 2} \frac{\sqrt{x} - \sqrt{2}}{x - 2}$ is:

### Options
- [ ] (A) 0
- [ ] (B) $\sqrt{2}$
- [x] (C) $\frac{1}{2\sqrt{2}}$
- [ ] (D) $\frac{}{\sqrt{2}}$ 

### Solution

C) $\frac{1}{2\sqrt{2}}$

$$
\begin{align*}
\lim_{x\rightarrow2} \frac{\sqrt{x}-\sqrt{2}}{x-2} &=  \lim_{x\rightarrow2} \frac{\frac{1}{2}x^{-\frac{1}{2}}}{1} \quad [\text{After applying L'Hospital's rule}]\\
&= \lim_{x\rightarrow2} \frac{1}{2}x^{-\frac{1}{2}}  = \frac{2^{-\frac{1}{2}}}{2} = \frac{1}{2\sqrt{2}}
\end{align*}
$$

## Question 6

Which among the following typically reduces overfitting in a supervised machine learning algorithm?

i) Increase model complexity.
ii) Reduce model complexity.
iii) Increase the number of training points.
iv) Reduce the number of training points.

### Options
- [ ] (A) i and ii
- [ ] (B) i, ii, and iii
- [x] (C) ii and iii
- [ ] (D) i, ii, iii, and iv

### Solution

(C) ii, and iii

- Reducing the model complexity reduces its ability to overfit.
- Increasing the training data makes the model focus on the prominent features hence avoid overfitting.

## Question 7

A fair coin is flipped twice, and it is given that at least one tail has been observed. The probability of getting two tails is:

### Options
- [ ] (A) $\frac{1}{2}$
- [ ] (B) $\frac{1}{3}$
- [ ] (C) $\frac{2}{3}$
- [ ] (D) $\frac{1}{4}$

### Solution

B) $\frac{1}{3}$

$$
\begin{align*}
P\left( TT\ \cap \ \text{Atleast One tail}\right) &=\ \frac{1}{4}\\
P\left(\text{Atleast One tail}\right) &=\ \frac{3}{4}\\
\therefore P\left( TT|\text{ Atleast One tail}\right) &=\ \frac{P\left( TT\ \cap \ \text{Atleast One Tail}\right)}{P\left(\text{Atleast One Tail}\right)}\\
&=\ \frac{1/4}{3/4} =\ \frac{1}{3}
\end{align*}
$$

## Question 8

Given n particles and m (> n) boxes, we place each particle in one of the boxes uniformly at random. What is the probability that no box receives more than one particle?

### Options
- [ ] (A)
    $$\frac{n!}{(m - n)!m^n}$$
- [ ] (B)
    $$\frac{m!}{(m - n)!m^n}$$
- [ ] (C)
    $$\frac{1}{m^n}$$
- [ ] (D)
    $$\frac{(m - n)!}{m!}$$

### Solution

<blank space for solution>


## Question 7
For two events $A$ and $B$, $A \subset B$, which one of the following is correct?

### Options
- [ ] $P(B | A) \geq P(A)$
- [ ] $P(B | A) \leq P(A)$
- [ ] $P(B | A) < 1$
- [ ] $P(B | A) = 0$

### Solution

<blank space for solution>

## Question 10

$X$ is a random variable with support $[-2, 2] \cup [99.5, 100.5]$. The PDF of $X$ is such that it is equal to a constant $c$ inside its support and $0$ outside. The expected value of $X$ is ________ .

### Solution


## Question 11

A binary classification dataset contains only 5% of positive instances. Which one of the following experimental design and performance measures is most suited for measuring the generalizability of a classifier trained on this dataset?

### Options
- [ ] (A) fixed training and test sets, accuracy
- [ ] (B) fixed training and test sets, area under the ROC curve
- [ ] (C) stratified cross-validation, accuracy
- [ ] (D) stratified cross-validation, area under the ROC curve

### Solution

## Question 12

Increasing the regularization coefficient value in ridge regression will typically  

i) Increase the bias of the resulting model.  
ii) Decrease the bias of the resulting model.  
iii) Increase the variance of the resulting model.  
iv) Decrease the variance of the resulting model.  

Which of the following statements are correct?

### Options
- [ ] (A) i and iii only
- [ ] (B) i and iv only
- [ ] (C) ii and iii only
- [ ] (D) ii and iv only

### Solution

## Question 13

A decision tree classifier learned from a fixed training set achieves 100% accuracy on the test set. Which of the following algorithms trained using the same training set is guaranteed to give a model with 100% accuracy?  
i) Logistic regression.  
ii) An SVM with a polynomial kernel.  
iii) k-Nearest neighbors.  
iv) Naïve Bayes classifier.  

### Options
- [ ] (A) i only
- [ ] (B) i and ii only
- [ ] (C) i, ii, iii, and iv
- [ ] (D) iv only

### Solution

## Question 14

Consider two relations $R(x, y)$ and $S(x,z)$. Relation $R$ has 100 records, and relation $S$ has 200 records. What will be the number of attributes and records of the following query?

```sql
SELECT * from R CROSS JOIN S;
```

### Options
- [ ] (A) 3 attributes, 20000 records
- [x] (B) 4 attributes, 20000 records
- [ ] (C) 3 attributes, 200 records
- [ ] (D) 4 attributes, 200 records


### Solution

In cross join the resulting table will consist of cartesian product of all the tuples in the tables and all the attributes from $R$ and $S$ will be present.  
Then the number of records = 100* 200 = 20000 records.
The number of attributes = 2 + 2 = 4 attributes.


## Question 15

Consider two relations $R(x, y)$ and $S(y)$, and perform the following operation: 

$$R(x,y) \text{ DIVIDE } S(y)$$

If $X$ is the relation returned by the above operation, which of the following option(s) is/are always TRUE?

### Options
- [ ] (A) $|X| \leq |R|$
- [ ] (B) $|X| \leq |S|$
- [ ] (C) $|X| \leq |R|$ AND $|X| \leq |S|$
- [ ] (D) $|X| > |S|$

### Solution


## Question 16

Which of the following statements is/are TRUE?

### Options
- [ ] (A) Every relation in BCNF is also in 3NF.
- [ ] (B) Every relation with two attributes is in BCNF.
- [ ] (C) No relation can be in both BCNF and 3NF.
- [ ] (D) Every relation in 3NF is also in BCNF.

### Solution


## Question 17

For matrix $A = \begin{bmatrix} 9 & -2 \\ -2 & 6 \end{bmatrix}$, one of the eigenvalues is 5. The other eigenvalue is  

### Options
- [ ] (A) 12
- [x] (B) 10
- [ ] (C) 8
- [ ] (D) 6

### Solution

sum of eigenvalues = trace = 9+6 = 15  
=> eigenvalue = 15-5 = 10


## Question 18

Two non-zero vectors $x$ and $y$ are perpendicular if  

### Options
- [x] (A) $x^T y = 0$
- [ ] (B) $x^T y > 0$
- [ ] (C) $x^T y < 0$
- [ ] (D) $x^T y \neq 0$

### Solution

Two non-zero vectors are perpendicular if there dot product is zero.

$$
\begin{align*}
x^Ty &= x\cdot y = |x||y|cos(\theta) = 0\\
\rArr cos(\theta)&=0 \quad \text{[since x and y are non-zero]} \\
\rArr \theta &=90^\circ
\end{align*}
$$
Thus the vectors are perpendicular