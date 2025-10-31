
# Proving Set Relationship

# Proving Subset Relationship

Recall that for any set $A, B, (A \subseteq B) \leftrightarrow (\forall x \in U)[x \in A \to x \in B]$
- Therefore, to prove that A is a subset of B we need to prove that all the elements in A are also in B.


>[!important]
> 
>Claim: $A \subseteq B$
> 
>Proof: 
>- Let $x \in A$
>	- ......
>	- $x \in B$
>- Therefore, $A \subseteq B$

# Proving Set Equivalence

A set is equivalence to another set if and only if they have the same elements. This involves using definition of intersection, union, etc. See [[6.1 Set Properties and Tuples (Or List)]].

Three Methods to do this (This is similar to the proof by equivalence):

Method 1: 
>[!important]
>
>Claim: A = B
> 
>Proof: 
>- $x \in A \leftrightarrow S1$
>	- $\leftrightarrow S2$
>	- $\leftrightarrow S3$
>	- .....
>	- $\leftrightarrow B$
>- Therefore $A = B$

> - Doesn't always work
> - It must work backward



Method 2: Break it into two parts
>[!important]
> 
>Claim: A = B
>
>Proof: 
>- Part 1: show $A \subseteq B$ using subset relationship proof
>.......
>- Part 2: show $B \subseteq A$ using subset relationship proof
>.........
>Combine part 1 and part 2 therefore $A = B$

Method 3: Using set rules. 

The set rules are: 

![setRules.png](../assets/setRules.png)


>[!important]
> 
>Claim: $A = B$
>
>Proof: 
>- $A = X$
>	- $= Y$
>	- $= Z$
>	- .....
>	- $= B$
>
>Therefore, $A = B$

Generally speaking, if you can prove the claim using set rules you can prove it using the first method but this is not always the case. It also doesn't really matter which side you start LHS or RHS sometimes it's easier to start on one side than the other.
## Venn Diagram 

A good way to disprove a claim if you suspect that the two sets are not equal is using a Venn diagram. 

Draw a Venn diagram for the LHS and shade in the regions then draw one for the RHS and shade in the regions if there is a certain region where they do not agree then they are not equal. Your counterexample will be assigning collection of elements to each set and show that the LHS $\neq$ RHS.

> Note: Venn Diagram is there to help you determine a set of elements to show that LHS $\neq$ RHS. Do not use the Venn Diagram in your proof or as a counterexample. 



## Proof involving Power sets

Recall that for any set A, a member of the power set A is a subset of A. 
- $x \in \mathcal P(A) \leftrightarrow x \subseteq A$

When proving something about a power set it will normally involve that definition.



# Proof Examples: 

#### 1. Claim: For all sets $A, B, \text { and } C, (A - B) \cap C \subseteq A \cap C$

>[!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $x \in (A - B) \cap C$, it suffices to show $x \in A \cap C$
>1. $x \in (A - B) \wedge x \in C$, definition of intersection
>2. $(x \in A \wedge x \notin B) \wedge x \in C$, definition of difference
>	- Disclaimer: line 1 and 2 are not interchangeable you need to do the line 1 first before line 2. This is because the logic $\wedge$ applies to statements not sets and $\cap$ applies to sets not statements. So, if you do difference first then that is wrong. $(x \in A \wedge x \notin B) \cap C$ is not correct since the LHS of $\cap$ is a statement that can be proven while the RHS is a set. 
>3. $x \in A \wedge x \in C$, specialization (yes, you can use rules of inteferences and logic rules)
>4. $x \in (A \cap C)$, definition of intersection, as desired $\blacksquare$
> </details>

#### 2. Claim: For all sets $A, B, \text { and } C, A^c \cup B^c \subseteq (A \cap B \cap C)^c$

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $x \in A^c \cup B^c$, it suffices to show $x \in (A \cap B \cap C)^c$
>1. $x \notin A \vee x \notin B$, definition of complement
>2. $x \notin A \vee x \notin B \vee x \notin C$, generalization 
>3. $\neg(x \in A \wedge x \in B \wedge x \in C)$, DeMorgan 
>4. $\neg (x \in (A \cap B \cap C))$
>5. $x \notin (A \cap B \cap C)$
>6. $x \in (A \cap B \cap C)^c$, definition of complement
>$\blacksquare$
> </details>



#### 3. Claim: For all sets $A, B, \text { and } C, (B \cup C) - A = (B - A) \cup (C - A)$

I will prove this two ways. First, with the equivalence and second with the set rules. 

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $x \in (B \cup C) - A$
>1. $\leftrightarrow x \in (B \cup C) \wedge x \notin A$
>2. $\leftrightarrow (x \in B \vee x \in C) \wedge x \notin A$, definition of union
>3. $\leftrightarrow (x \in B \wedge x \notin A) \vee (x \in C \wedge x \notin A)$, distribution
>4. $\leftrightarrow (x \in B - A) \vee (x \in C - A)$, definition of difference
>5. $\leftrightarrow x \in B - A) \cup (C - A)$, definition of union
>  
>As you can each step also works backwards. The only times it really doesn't is when it involves specialization or generalization those are only one way.
>$\blacksquare$
> </details>

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>1. $(B \cup C) - A$
>2. $= (B \cup C) \cap A^c$, alternate set difference
>3. $= (B \cap A^c) \cup (C \cap A^c)$, distribution
>4. $= (B - A) \cup (C - A)$, alter. set diff $\blacksquare$
> </details>



#### 4. Claim: If $A \cap B = A$ then $A \cup B = B$

> [!tip]
> <details>
> <summary>Proof</summary>
>  
>Assume $A \cap B = A$<br> 
>Part 1: show $A \cup B \subseteq B$
>1. Let $x \in A \cup B$
>2. $x \in A \vee x \in B$
>3. $x \in (A \cap B) \vee x \in B$, by our assumption
>4. $(x \in A \wedge x \in B) \vee x \in B$
>5. $(x \in A \vee x \in B) \wedge (x \in B \vee x \in B)$, distribution
>6. $(x \in B \vee x \in B)$, specialization
>7. $(x \in B) \checkmark$
>
>Part 2: show $B \subseteq A \cup B$
>1. Let $x \in B$
>2. $x \in B \vee x \in A$, generalization 
>3. $x \in A \cup B \checkmark$
>
>Therefore, combining part 1 and 2, the claim holds. $\blacksquare$
> </details>

#### 5. Claim: $\mathcal P(A) \cup \mathcal P(B) \subseteq \mathcal P(A \cup B)$

> [!tip]
> <details>
> <summary>Proof</summary>
>  
>Let $x \in \mathcal P(A) \cup \mathcal P(B)$, it suffices to show that $x \in \mathcal P(A \cup B)$
>1. $x \in \mathcal P(A) \vee x\in \mathcal P(B)$
>2. $x \subseteq A \vee x \subseteq B$, definition of power set
>3. let $y \in x$
>4. since $x \subseteq A \vee x \subseteq B, y \in A \vee y \in B$
>5. $y \in A \cup B$
>6. $y \in x \to y \in A \cup B$, so $x \subseteq A \cup B$
>7. $x \in \mathcal P(A \cup B)$, definition of power set $\blacksquare$
> </details>

#### 6. Claim: $((A \cup B) − C) \cup (A \cap B) = ((A − B) \cup (B − A)) − C$

> [!tip]
> <details>
> <summary>Proof</summary>
>  
>This is false: 
>
>Let:
>1. $A = \{1, 2\}$
>2. $B = \{2\}$
>3. $C = \{3\}$
>4. $((A \cup B) - C) \cup (A \cap B) \overset{?}{=} ((A - B) \cup (B - A))-C$
>5. $(\{1, 2\} - \{3\}) \cup (\{2\}) \overset{?}{=} ((\{1, 2\} - \{2\}) \cup (\{2\} - \{1, 2\}))-\{3\}$
>6. $\{1, 2\} \overset{?}{=} (\{1\} \cup \varnothing)-\{3\}$
>7. $\{1, 2\} \overset{?}{=} \{1\}-\{3\}$
>8. $\{1, 2\} \neq \{1\} \blacksquare$
> </details>


#### 7. Claim: $(A - B) - C = (A - C) - (B - C)$

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Start at the RHS:
>1. $(A - C) - (B - C)$
>2. $= (A \cap C^c) \cap (B \cap C^c)^c$
>3. $= (A \cap C^c) \cap (B^c \cup C)$
>4. $= (A \cap C^c \cap B^c) \cup (A \cap C^c \cap C)$
>5. $= (A \cap C^c \cap B^c) \cup (A \cap \varnothing)$
>6. $= (A \cap C^c \cap B^c) \cup \varnothing$
>7. $= (A \cap C^c \cap B^c)$
>8. $= (A - C) - B$ 
> </details>