# Set Properties and Tuples

# Set Operation (Definition)


1. **Definition of Union:** $A \cup B = \{x \in U | x \in A \vee x \in B\}$
2. **Definition of Intersection:** $A \cap B = \{x \in U | x \in A \wedge x \in B\}$
3. **Definition of Complement:** $A^{c} = A' = \overline A = \{x \in U | x \notin A\}$
4. **Definition of Difference:** $A - B = \{x \in U | x \in A \wedge x \notin B\}$
	1. $A-b$ also means $A \cap B^{c}$, this is not the formal definition of difference but it is directly tie to the definition of complement.
>[!important]
>Suppose $A = \{1, 2, 4\}$ and $B = \{2, 3, 6\}$
>1. $A \cup B = \{1, 2, 3, 4, 6\}$
>2. $A \cap B = \{2\}$
>3. $A \cap B^c = \{1, 4\}$
>4. $A - B = \{1, 4\}$
>
> Observe that number 3 and 4 are the same. Think of $A - B$ as all the elements in A but if some of those elements exist in B remove them. 
# Venn Diagram

A Venn diagram is a illustrative way to demonstrates the region of a set. Each circle represent a set. 
- $A \cap B$ is the region where A and B overlap. 
- $A \cup B$ is the combination of both region including their intersection if there is any. 
- If set B is a subset of A then the union of A and B is just A. The intersection of A and B is just B. To show this draw a circle and label it A and draw another circle inside the circle A and label the inner circle B (showing B is subset of A). 
- $A - B$ is only the area of region A where it does not overlap with B. 
- $A^c$ is all the area where region A does not overlap with.  


# Empty Set Properties and the Universal Set

Recall that the empty set is denoted as $\varnothing$ and has no elements so $\varnothing = \{\}$

Suppose A is some set that contains some element.
1. The empty set is a subset of all sets. So, $\varnothing \subseteq A$.
	1. If A was empty then $\varnothing$ is not a proper subset of A.
2. Any set that intersect the empty set is the empty set. So, $\varnothing \cap A = \varnothing$
3. Any set that union the empty set is the set itself. So, $\varnothing \cup A = A$
4. Any set that intersect the complement of itself is the empty set. So, $A \cap A^c = \varnothing$
5. Any set that union the complement of itself is the universal set, So, $A \cup A^c = U$
6. The complement of the universal set is the empty set and vice versa.
	1. $U^c = \varnothing$
	2. $\varnothing^c = U$


# $n$-Tuples 

These are basically like list in programming. 
- The order matters and duplicates are allowed. They are denoted with parenthesis rather than with curly bracket. 
	- So, $(1, 2, 3, 3, 5) \neq (2, 1, 3, 3, 5) \neq (2, 1, 3, 5)$


A 2-tuples are called **ordered pairs** and a 3-tuples are called **ordered triples**. 

# Cartesian Product (Set of Ordered Pairs)

Do not confuse cartesian product with cross product from linear algebra. <br> 
Suppose A is a set and B is a set then the cartesian product is defined as: 
- $A \times B = \{(a, b) | a \in A \wedge b \in B\}$

Cartesian Product is not commutative so $A \times B \neq B \times A$.<br>
Suppose $A = \{R, Y, B\}$ and $B = \{2, 3\}$

Cartesian Product of $A \times B = \{(R, 2), (R, 3), (Y, 2), (Y, 3), (B, 2), (B, 3)\}$<br>
Cartesian Product of $B \times A = \{(2, R), (2, Y), (2, B), (3, R), (3, Y), (3, B)\}$

>Those sets are not the same, they contain 2-tuples (order pairs) as elements and order matters for tuples. So, $(2, R) \neq (R, 2)$. Think of it like a point on a graph where $(1, 3) \neq (3, 1)$ which is basically what 2-tuples are. 


## The Size of Cartesian Product

For any set $A, B$, the $|A \times B| = |A| \times |B|$ which is the same as n(A $\times$ B) = n(A) $\times$ n(B). Recall that $|A| =$ n(A). 

>So, if the size of set $A = 3$ and the size of set $B = 2$ then the size of $A \times B = 6$



# Disjoint Set

For any set $A, B$ if A and B have no elements in common then they are disjoint. Therefore, the intersection of A and B is the empty set. $A \cap B = \varnothing$.


# Set containing other Sets

A set can contain other sets as it element.

For any set $A, B, C, D$, we can have: 
- $D = \{A, B\}$
- $C = \{A, \varnothing \}$

> The set C contains the set A as its elements and an empty set as its element meaning it has two elements in itself although one of the elements is a empty set. 

Suppose we have the following sets: 
1. $\varnothing$ 
2. $\{\varnothing\}$
3. $\{\varnothing, \{\varnothing\}\}$

What does each of the above mean?

1. The empty set is just the empty set that contains no element so, $\varnothing = \{\}$ and $|\varnothing| = 0$.
2. This is a set that contains the empty set as its element, so the size of this set is 1. Therefore, $\{\varnothing\} = \{\{\}\}$ and $|\{\varnothing\}| = 1$.
3. This is a set that contains the empty set as one of its elements but it also contains another element which is another set that contains the empty set, so the size of this set is 2. Therefore, $\{\varnothing, \{\varnothing\}\} = \{\{\}, \{\{\}\}\}$, and $|\{\varnothing, \{\varnothing\}\}| = 2$.


# Power set

For any set A, the power set of A is denoted as $\mathcal P(A)$, (Yes fancy looking P).
- The power set of A is a set that contains all the subsets of A (which also include A itself).
For example, suppose $A = \{1, 2, 3\}$
- Then, $\mathcal P(A) = \{\varnothing, \{1\}, \{2\}, \{3\}, \{1, 2\}, \{1, 3\}, \{2, 3\}, \{1, 2, 3\}\}$
	- Don't forget to include the empty set. The empty set is a subset of all sets. 

The cardinality (size) of a power set: n$(\mathcal P(A)) = |\mathcal P(A)| =  2^{|A|}$ .

More examples: 
- $\mathcal P(\varnothing) = \{\varnothing\}$
- $\mathcal P(\{\varnothing\}) = \{\varnothing, \{\varnothing\}\}$
- $\mathcal P(\{\varnothing, \{\varnothing\}\}) = \{\varnothing, \{\varnothing\}\, \{\{\varnothing\}\}, \{\varnothing, \{\varnothing\}\}$
	- It easier to do this one if you assign a variable to each element first before finding the powerset so let $x = \varnothing$ and $y = \{\varnothing\}$.

## Definition of Power set
A member of the power set A is a subset of A and vice versa.<br> 
So, $x \in \mathcal P(A) \leftrightarrow x \subseteq A$

# Other Properties

**Inclusion:**
- $A \cap B \subseteq B$
- $A \cap B \subseteq A$
- $A \subseteq A \cup B$
- $B \subseteq A \cup B$

**Transitivity:** 
- $A \subseteq B \wedge B \subseteq C \to A \subseteq C$



# Partitions of a Set

For any set $A$, a set of non-empty sets $\{A_1, A_2, A_3, ..., A_n\}$ is a partition of set $A$ if and only if: 
1. $A = A_1 \cup A_2 \cup A_3 \cup ... \cup A_n$
2. $A_1, A_2, A_3, ..., A_n$ are mutually disjoint. 

>Basically, a partition is a set that contains subsets of the original set where all subsets are mutually disjoint. 


Given $A = \{1, 2, 3\}$<br>
The partitions of set $A$ which has 3 elements are:
1. $\{\{1\}, \{2\}, \{3\}\}$
2. $\{\{1, 2\}, \{3\}\}$
3. $\{\{1, 3\}, \{2\}\}$
4. $\{\{1\}, \{2, 3\}\}$
5. $\{\{1, 2, 3\}\}$

So, there are five partitions of set $A$ in total.<br> 
A partition can be infinite or finite. A infinite set can also be partitioned.

For example, 
- The set of all integer numbers $\Bbb Z$ can be partitioned as even numbers and odd numbers. So, $\Bbb Z = \{\{ \text{Even number}\},\{ \text{Odd number}\}\}$, the partition is a finite set since it contains two sets as it elements. 
- Natural number can be partitioned as a set containing infinite singleton sets of integer number greater than or equal to zero. $\Bbb N = \{\{k\ : k \in \Bbb Z^{\geq 0}\}\}$. This would be an infinite partition since the set would contain infinite number of singleton sets. 
	
