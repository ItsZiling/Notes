# Propositional Logic

## Statement
- A sentence that can be assigned a truth value of either `true` or `false`.
- Not all sentences are statements 
	- However all statements by definition must be sentences
- It is also called "Proposition"



> [!TIP] 
> Example of Statement
> - 6 < 4
>	- This would be `false`. 6 is not less than 4
> - There exists some integer x such that x > 2
>	- This would be `true`. There does exist some integer (labeled x) that is greater than 2
> 
> Statements can also involve the future tense so if a statement is: 
> - Tommy will get an A in his next exam. 
>   - This is a statement, we just don't know if it's `true` or `false` yet. 



> [!NOTE]
> If the sentence contains any "ambiguous" words such as "she, he, they or them", they are not statement. The words must be specific. 
> - She lives at 1234 Main Street 
>   - This is not a statement. The word "she" is effectively treated like a free variable or unbound variable ***X***. This means that "she" is too vague and can be applied to any female. You would need to specify who "she" is for it to be considered a statement.

> [!caution]
> Also Note: 
> 
> Opinions are not statements
> - Chocolate ice cream is the best flavored ice cream
>   - This is objectively false by the way. Still an opinion.
> 
> Questions are not statements 
> - What is the weather today? 
>   - Try assigning a `true` or  `false` value to this one. You'll find its not possible.
> 
> Commands are not statements
> - Hey go close that door now!
>   - Once again, Try assigning a `true` or `false` value to this one.



## Logical Connectivity 
- They are used to connect statements together to form, according to my professor, more complex statements.

| Connectivity  | Meaning           |
| ------------- | ----------------- |
| $\wedge$      | and (conjunction) |
| $\vee$        | or (disjunction)  |
| $\sim (\neg)$ | not (negation)    |
### Some Simple Usage of Connectivity
Suppose $p$= `Jason has an A in CMSC250` and $q$= `Jason is in denial`
  - A simple form of connectivity can be $p \wedge q$
    - This would mean `Jason has an A in CMSC250 and is in denial`



> [!NOTE]
> Order of Precedence 
> - $\sim (\neg)$ takes precedence over $\wedge$ and $\vee$
> - $\wedge$ and $\vee$ have the same precedence.


> [!TIP] 
> Important
> - When dealing with $\wedge$ and $\vee$ parenthesis are needed to specify what comes first or else it is not considered a statement, unless it contains all the same connectivity. 
> 
> Example: 
> - Suppose we used the same example ***p*** and ***q*** above and introduce a new variable ***r***, suppose ***r*** = `I am angry.` 
>   - $p \wedge q \vee r$, is not a valid statement (Parenthesis is needed!!!). 
>	- $(p \wedge q) \vee r$, is a valid statement. 
>	- $p \wedge q \wedge r$, is also a valid statement since all the connectivity are the same.

## Translating English into Logic 
When we are given an English statement, we break the statement into parts and assign a variable to each part then connect the parts together with a logic connectivity.

We will translate the given statements into "logic": 
- "Tommy likes oranges and apples"
  - Let p = `Tommy likes oranges` and q = `Tommy likes apples`
    	- $p \wedge q$
- "Fruits are healthy but snacks are not"
  - Let p = `fruits are healthy` and q = `snacks are healthy` 
	- $p \wedge \sim q$
- Either Jim is sleepy or Jim is tired
  - Let p = `Jim is sleepy` and q = `Jim is tired`
	- $p \vee q$
- Neither Jim nor Timmy are sleeping 
  - Let p = `Jim is sleeping` and q = `Timmy is sleeping`
    - Note: Either of the two notations work here, they are equivalent. See [Law of Equivalance](../assests/Law%20of%20Equivalance.png)
	- $\sim p \wedge \sim q$ or
	- $\sim (p \vee q)$
- Neither Jim nor Timmy are angry but Tommy is. 
  - Let p = `Jim is angry` and q = `Timmy is angry` and r = `Tommy is angry`
	- $\sim p \wedge \sim q \wedge r$
## Truth Table 
Determines whether or not a statement is `true` or `false` under every possible interpretation. 
- We would use `T` for `true` and `F` for `false`.
- If we use binary, `1` would be `true` and `0` would be `false`.
	
### Interpretation
Each row of a truth table represents an interpretation.
An Interpretation is basically a combination of assignments of either `true` or `false` value for each variable.
- For example, suppose we have variable ***p*** and ***q***.
  - One interpretation can be ***p*** is `true` and ***q*** is `false`.
  - Given an Interpretation we can evaluate whether or not a statement is true under that specific interpretation, this is known as **"truth valuation"**.
  - Suppose ***p*** and ***q*** is connected by `and`, so $p \wedge q$
    - Under the interpretation above this statement would be `false` since ***p*** is `true` and ***q*** is `false`. 
   
> [!tip]
> - The only time that a statement connected by only $\wedge$ is true is if all the variables are true
> - The only time that a statement connected by only $\vee$ is false is if all the variables are false

### Truth Table Example
- I will be using `1` for `true` and `0` for `false`

|  $p$  |  $q$  | $\sim p$ | $p \wedge q$ | $p \vee q$ | $\sim p \vee q$ | $\sim(p \wedge q)$ |
| :---: | :---: | :------: | :----------: | :--------: | :-------------: | :----------------: |
|   1   |   1   |    0     |      1       |     1      |        1        |         0          |
|   1   |   0   |    0     |      0       |     1      |        0        |         1          |
|   0   |   1   |    1     |      0       |     1      |        1        |         1          |
|   0   |   0   |    1     |      0       |     0      |        1        |         1          |

## Logical Equivalence
Two statements are considered logically equivalent if they have the same truth value under every possible interpretation. 
- $q \equiv \sim \sim q$

>[!NOTE]
>The symbol $\equiv$ means "equivalent" or "congruent". Do note that  there is another symbol that specifically means "congruent" which is $\cong$ but for sake of this course the symbol $\equiv$ means both equivalent and congruent. Also note, that neither symbol means "equal to". "Equivalent" and "congruent" is the NOT same as "equal to". 

To check whether or not two statements are equivalent you can always write out a truth table. 
- But as you progress in this course you will starts to notice that it is very tedious to write out a truth table every time. 
  - If you are given that the two statements are not logically equivalent and you are required to show that they are not equivalent then you just have to find one interpretation where they don't match.
### Tautology
A statement is called a tautology if they are `true` under every possible interpretation. 
- Example
  - $q$ $\vee \sim q$

### Contradiction 
A statement is called a contradiction if they are `false` under every possible interpretation.
- Example
  - $q$ $\wedge \sim q$


## Laws of Equivalence
We can use the laws of equivalence to simplify statements
![Law of Equivalance.png](../assests/Law%20of%20Equivalance.png)

> [!IMPORTANT]
> Given the statement: $\sim (\sim p \wedge q) \wedge (p \vee \sim q)$.
> 
> We can simplify this statement to a more readable one using the following steps:
> 
> Simplification Steps: 
> - Apply DeMorgan Law 
> 	- $(\sim \sim p \vee \sim q) \wedge (p \vee \sim q)$
> - Apply Double Negative Law
> 	- $(p \vee \sim q) \wedge (p \vee \sim q)$ 
> - Apply Idempotent Law
> 	- $(p \vee \sim q)$

We can also use Laws of Equivalence to show if two statement are equivalent to each other

> [!important]
> Given the statement: $\sim(p \vee \sim q) \vee (\sim q \wedge \sim p)$ show that it is equivalent to $\sim p$
> 
> Steps(I will be combining some steps together because it is tedious to type everything out): 
> - Apply DeMorgan Law
> 	- $(\sim p \wedge \sim \sim q) \vee (\sim q \wedge \sim p)$
> - Apply Commutative Law and Double Negative Law
> 	- $(\sim p \wedge q) \vee (\sim p \wedge \sim q)$
> - Apply Distributive Law
> 	- $\sim p \wedge (q \vee \sim q)$
> - Apply Negation Law
> 	- $\sim p \wedge Tautology$
> - Apply Identity Law 
> 	- $\sim p$



## Implications (Conditional Statement)
Implication is defined with an arrow $$\to$$.
 In plain English that means "implies". In programming, its akin to an "if then" statement.

 So if we have the statement $p \to q$
- In English that means "p implies q" or "if p then q" 
- Using the definition of arrow $(\rightarrow)$ above in the laws of equivalence chart it is equivalent to 

$$\sim p \vee q$$

> [!note]
> The arrow $\to$ has a lower precedence than $\vee$ and $\wedge$
> 
> So if we have the statement $p \wedge q \to r$
> - You would do the "and" first then the "arrow" so you can look at it as: 
> $$(p \wedge q) \to r$$

When drawing a truth table for implication, the only interpretation that makes the arrow `false` is if the left hand side of the arrow is `true` but the right hand side is `false`. However, if the left hand side of the arrow is `false` then we do not care if the right hand side is `true` or `false`.The statement is automatically `true`.
- For further justification, the arrow represents implication. Imagine the statement "p implies q". If p is `true` then it must mean that q is `true` for the statement to be `true`, however, if p is `true` and q is `false`, then that statement is `false`. Respectively, if p is `false` then we do not care if q is `true` or `false` the statement is `true` either way.
  - Consider the statement, "If the floor is wet then the floor is slippery".
    - The only time the statement is `false` is if the floor is wet but the floor is not slippery.
    - If the floor is not wet then we do not care if it is slippery. The statement is `true` because if the floor is not wet then it may or may not imply that it is slippery. 

> When translating implication into logic, they follow the same steps of breaking the statement apart and assign a variable to each parts.
> 
>  Example: "If the floor is wet then the floor is slippery"
> - Let p = `floor is wet` and q = `floor is slippery`
> 	- $p \rightarrow q$

### Example of Implication using Truth Table

|  $p$  |  $q$  | $\sim p$ | $p \to q$ | $\sim p \vee q$ |
| :---: | :---: | :------: | :-------: | :-------------: |
|   1   |   1   |    0     |     1     |        1        |
|   1   |   0   |    0     |     0     |        0        |
|   0   |   1   |    1     |     1     |        1        |
|   0   |   0   |    1     |     1     |        1        |

> Observe that $p \to q$ and $\sim p \vee q$ are equivalent thus we have prove the Definition of $\rightarrow$ from the Laws of Equivalence chart.

### Converse, Inverse and Contrapositive Definition for Implication
Suppose we have p and q where p = `floor is wet` and q = `floor is slippery` and $p \to q$ so "if the floor is wet then the floor is slippery"
- The converse will be: $q \to p$
  - This means "if the floor is slippery then the floor is wet"
- The inverse will be: $\sim p \to \sim q$
  - This means "if the floor is not wet then the floor is not slippery"
- The contrapositive will be: $\sim q \to \sim p$
  - This means "if the floor is not slippery then the floor is not wet"

Converse means you flip them, inverse means you negate both, contrapositive means you negate both then flip them. Pretty self-explanatory.

> [!tip]
> - The original statement is equivalent to its contrapositive
> - The converse is equivalent to the inverse
> 
> You can draw out a truth table for each one to confirm it yourself but I am too lazy to do one.
> 
> Editor Note: What the bossman said. I don't wanna write a table either. Latex is pain.

## Biconditional Statement (if and only if)
Biconditional statement is defined with a double arrow: $\leftrightarrow$
- This is the same thing as saying the LHS (left hand side) implies the RHS (right hand side) and the RHS implies the LHS. 
  - In simple terms you can say RHS if and only if LHS
    - Suppose we have the statement: $p \leftrightarrow q$
    - This is equivalent to $ (p \to q) \wedge (q \to p)$
    - This is effectively saying that both p and q have to be `true` or they both have to be `false`. So this is also equivalent to $(p \wedge q) \vee (\sim p \wedge \sim q)$

Using a truth table we have

|  $p$  |  $q$  | $p \leftrightarrow q$ |
| :---: | :---: | :-------------------: |
|   1   |   1   |           1           |
|   1   |   0   |           0           |
|   0   |   1   |           0           |
|   0   |   0   |           1           |
## Arguments
By definition, an argument is a conjecture that states "if you make certain assumptions, then a particular statement must logically follow." - Fawzi 
- The assumptions are called **premises**.
- The particular statement that must follow is the **conclusion**.

### Validity
We can check whether or not the given argument is valid using either a truth table, or with the [Law of Equivalence](../assests/Law%20of%20Equivalance.png) chart and the [Rules of Inferences](../assests/Rules%20of%20Inference.png) chart.

In order for an argument to be valid, every interpretation in which all the premises are true, the conclusion must also be true. 
- For the sake of less typing I will denote premise 1 as P1, premise 2 as P2 and so on 
  - So if an argument is valid then it means that: $(P1 \wedge P2 \wedge P3 \wedge ...) \rightarrow Conclusion$

|            | Example 1: Suppose we have the argument |     |
| ---------- | --------------------------------------- | --- |
| P1         | $p \vee q$                              |     |
| P2         | $q \to r$                               |     |
| P3         | $\sim p$                                |     |
| Conclusion | $r$                                     |     |
Is the argument valid? Lets find out using a truth table

|  $p$  |  $q$  | (conclusion) </br> $r$ | (P3) </br> $\sim p$ | (P1)</br> $p \vee q$ | (P2)</br> $q \to r$ |
| :---: | :---: | :--------------------: | :-----------------: | :------------------: | :-----------------: |
|   1   |   1   |           1            |          0          |          1           |          1          |
|   1   |   1   |           0            |          0          |          1           |          0          |
|   1   |   0   |           1            |          0          |          1           |          1          |
|   1   |   0   |           0            |          0          |          1           |          1          |
|   0   |   1   |         ==1==          |        ==1==        |        ==1==         |        ==1==        |
|   0   |   1   |           0            |          1          |          1           |          0          |
|   0   |   0   |           1            |          1          |          0           |          1          |
|   0   |   0   |           0            |          1          |          0           |          1          |

> I have highlighted (with the ==) all the rows where the premises are all true, which there is only one row but the point is as long as the conclusion is true for all the rows where all the premises are true then the argument is valid. 

Lets consider another example: 

| Example 2  |            |
| ---------- | ---------- |
| P1         | $p \to r$  |
| P2         | $q \to r$  |
| P3         | $r$        |
| Conclusion | $p \vee q$ |
With a truth table

|  $p$  |  $q$  | (P3)<br>$r$ | (P1)<br>$p \to r$ | (P2)<br>$q \to r$ | (conclusion)<br> $p \vee q$ |
| :---: | :---: | :---------: | :---------------: | :---------------: | :-------------------------: |
|   1   |   1   |    ==1==    |       ==1==       |       ==1==       |            ==1==            |
|   1   |   1   |      0      |         0         |         0         |              1              |
|   1   |   0   |    ==1==    |       ==1==       |       ==1==       |            ==1==            |
|   1   |   0   |      0      |         0         |         1         |              1              |
|   0   |   1   |    ==1==    |       ==1==       |       ==1==       |            ==1==            |
|   0   |   1   |      0      |         1         |         0         |              1              |
|   0   |   0   |    ==1==    |       ==1==       |       ==1==       |            ==0==            |
|   0   |   0   |      0      |         1         |         1         |              0              |
> Now the example above is not a valid argument because on the second to last row, all the premises are true but the conclusion is false. 

Instead of drawing a truth table out each time we do a formal proof using Laws of Equivalence and Rules of Inferences. Here is the chart for Rules of Inferences: 
![public/Discrete-Math/Resources/Rules-of-Inference.png](../assests/Rules%20of%20Inference.png)


Suppose we used example 1 above: 

| Line Number |   Proof    | Rules or Laws used | Line used |
| :---------: | :--------: | :----------------: | :-------: |
|     P1      | $p \vee q$ |       Given        |           |
|     P2      | $q \to r$  |       Given        |           |
|     P3      |  $\sim p$  |       Given        |           |
|      1      |    $q$     |    Elimination     | P1 and P3 |
|      2      |    $r$     |    Modus Ponens    | P2 and 1  |
> As you can see we arrive at the conclusion, $r$, at line 2 which is the fifth row. This is also a relatively easy proof. 