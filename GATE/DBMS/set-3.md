# GATE DBMS Set 3

## Question 1

Consider the following three relations in a relational database.
- Employee (eId, Name)
- Brand(bId, bName)
- Own(eId, bId )

Which of the following relational algebra expressions return the set of eIds who own all the brands?

### Choices 
- [x] \(\Pi_{eId} (\Pi_{eId, bId} (\text{Own}) / \Pi_{bId} (\text{Brand}))\)
- [x] \(\Pi_{eId} (\text{Own}) - \Pi_{eId} ((\Pi_{eId} (\text{Own}) \times \Pi_{bId} (\text{Brand})) - \Pi_{eId, bId} (\text{Own}))\)
- [ ] \(\Pi_{eId} (\Pi_{eId, bId} (\text{Own})/\Pi_{bId} (\text{Own}))\)
- [ ] \(\Pi_{eId} ((\Pi_{eId} (\text{Own}) \times \Pi_{bId} (\text{Own})) / \Pi_{bId} (\text{Brand}))\)

### Feedback
To find the set of eIds who own all the brands:
- The first expression (\(\Pi_{eId} (\Pi_{eId, bId} (\text{Own}) / \Pi_{bId} (\text{Brand}))\)) performs a division between the projection of eId and bId in Own and the projection of bId in Brand. This retrieves the eIds who own all brands.
- The second expression uses set difference and intersection operations to achieve the same result as the first expression, thereby also returning the correct set of eIds who own all brands.

Hence, choices a and b are the correct relational algebra expressions to obtain the set of eIds who own all the brands.

## Question 2

The following relation records the age of 500 employees of a company, where empNo {indicating the employee number} is the key:
\[ \text{empAge}(\text{empNo}, \text{age}) \]

Consider the following relational algebra expression:
\[ \Pi_{\text{empNo}}.(\text{empAge} \bowtie (\text{age} > \text{age1}) \rho \text{ empNo1, age1} (\text{empAge})) \]

What does the above expression generate?

### Choices 
- [ ] Employee numbers of only those employees whose age is the maximum
- [ ] Employee numbers of only those employees whose age is more than the age of exactly one other employee
- [x] Employee numbers of all employees whose age is not the minimum
- [ ] Employee numbers of all employees whose age is the minimum

### Feedback
Let's break down the given expression:

- \( \Pi_{\text{empNo}} \): Projection on the attribute empNo.
- \( \text{empAge} \): Relation containing the empNo and age of employees.
- \( \bowtie (\text{age} > \text{age1}) \): Semi-join operation using the condition age > age1.
- \( \rho \text{ empNo1, age1} (\text{empAge}) \): Renaming the attributes of empAge to empNo1 and age1.

The expression generates the employee numbers of all employees whose age is not the minimum. This is achieved by performing a semi-join on empAge with itself based on the condition that the age of an employee is greater than some other employee's age, thus excluding those with the minimum age. Therefore, the correct choice is (c) Employee numbers of all employees whose age is not the minimum.

## Question 3

Consider the following relations:

```
P(X, Y, Z)
Q(X, Y, T)
R(Y, V)

P        | Q       | R
X  Y  Z  | X  Y  T | Y  V
---------|---------|------
X1 Y1 Z1 | X2 Y1 2 | Y1 V1
X1 Y1 Z2 | X1 Y2 5 | Y3 V2
X2 Y2 Z2 | X1 Y1 6 | Y2 V3
X2 Y4 Z4 | X3 Y3 1 | Y2 V2
```

How many tuples will be returned by the following relational algebra query?
\[ \left[ \Pi_X \left( \sigma (P.Y=R.Y \land R.V=V2) (P \times R) \right) - \Pi_X \left( \sigma (Q.Y=R.Y \land Q.T > 2) (Q \times R) \right) \right] \]

### Answer
1

### Feedback
Let's break down the query:

1. \( \sigma (P.Y=R.Y \land R.V=V2) (P \times R) \): This performs a natural join between P and R where Y values match in P and R and where R.V = V2.
2. \( \sigma (Q.Y=R.Y \land Q.T > 2) (Q \times R) \): This performs a natural join between Q and R where Y values match in Q and R and where Q.T > 2.
3. \( \Pi_X (\sigma (P.Y=R.Y \land R.V=V2) (P \times R)) - \Pi_X (\sigma (Q.Y=R.Y \land Q.T > 2) (Q \times R)) \): This subtracts the result of the second operation from the first one based on the X attribute.

The query finds tuples where P.Y matches R.Y and R.V equals V2, then subtracts tuples where Q.Y matches R.Y and Q.T is greater than 2. The final result will have only 1 tuple after performing the subtraction operation.

## Question 4

Consider the relations \(r(A, B)\) and \(s(B, C)\), where \(s.B\) is a primary key and \(r.B\) is a foreign key referencing \(s.B\). Consider the query.
\[ Q: r \bowtie (\sigma_{B<5} (S)) \]
Let LOJ denote the natural left outer-join operation. Assume that \(r\) and \(s\) contain no null values. Which one of the following queries is NOT equivalent to Q?

### Choices 
- [ ] \( \sigma_{B<5} (r \bowtie s) \)
- [ ] \( \sigma_{B<5} (r \text{ LOJ } s) \)
- [x] \( r \text{ LOJ } (\sigma_{B<5} (s)) \)
- [ ] \( \sigma_{B<5} (r) \text{ LOJ } s \)

### Feedback
Let's analyze each query:

- (a) \( \sigma_{B<5} (r \bowtie s) \): Selects tuples from the natural join of r and s where B is less than 5.
- (b) \( \sigma_{B<5} (r \text{ LOJ } s) \): Selects tuples from the left outer-join of r and s where B is less than 5.
- (c) \( r \text{ LOJ } (\sigma_{B<5} (s)) \): Performs a left outer-join of r with tuples from s where B is less than 5. This is different from the original query Q.
- (d) \( \sigma_{B<5} (r) \text{ LOJ } s \): Selects tuples from r where B is less than 5 and then performs a left outer-join with s.

Hence, the query that is NOT equivalent to Q is (c) \( r \text{ LOJ } (\sigma_{B<5} (s)) \).

## Question 5

Consider a database that has the relation schema CR(StudentName, CourseName). An instance of the schema CR is as given below:

| Student Name | Course Name |
|--------------|-------------|
| SA           | CA          |
| SA           | CB          |
| SA           | CC          |
| SB           | CB          |
| SB           | CC          |
| SC           | CA          |
| SC           | CB          |
| SC           | CC          |
| SD           | CA          |
| SD           | CB          |
| SD           | CC          |
| SD           | CD          |
| SE           | CD          |
| SE           | CA          |
| SE           | CB          |
| SF           | CA          |
| SF           | CB          |
| SF           | CC          |

The following query is made on the database:
\[ T1 \leftarrow \Pi_{\text{course Name}} (\sigma_{\text{Student Name} = 'SA'} (CR)) \]
\[ T2 \leftarrow CR \div T1 \]

The number of rows in T2 is _____________.

### Answer
4

### Feedback
The query \( T1 \leftarrow \Pi_{\text{course Name}} (\sigma_{\text{Student Name} = 'SA'} (CR)) \) selects all the course names where the Student Name is 'SA', resulting in T1 containing course names 'CA', 'CB', and 'CC'.

The query \( T2 \leftarrow CR \div T1 \) performs division between CR and T1. The result T2 contains tuples from CR that have all the course names from T1.

The output steps:
1. \( CR \div \text{CA} \): Gives students SA, SC, SD, SE, SF.
2. \( CR \div \text{CB} \): Gives students SA, SC, SD, SE, SF.
3. \( CR \div \text{CC} \): Gives students SA, SC, SD, SF.

Taking the intersection of these outputs gives the students SA, SC, SD, SF, which results in 4 rows in T2.