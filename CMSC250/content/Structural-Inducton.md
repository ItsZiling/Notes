
# Structural Induction
This induction is apply to a set of elements that is "recursively defined". This means it is used for any structure that defines itself or based on elements of the same set. 

Some examples of recursively defined set are: 
- Linked-List
- Tree
- Formal Language
  - Formal language are languages that has precise rules for its semantic and syntax, in other words, it is the grammar of a defined language. In computer science it is used to define the semantic and syntax used for a programming language.


# Steps

In structural induction, the inductive hypothesis is never stated but it is used in constructor case. 
- An constructor case describe how a new element or "widget" (we like to call it) can be created from a collection of smaller elements or "widgets". 

There can be one or more constructor case(s) and you need to prove each one but first a recursive definition needs to be defined. 

**Defining Recursive Definition:**
1. **Base Case:** The base case is basically an element or "widget" that is not built from collection of smaller widget (Ex. a single node of a binary tree). 
2. **Constructor Case 1:** describe a way a new widget can be created from an collection of smaller widgets.
3. **Constructor Case 2:** describe another way a new widget can be created from an collection of smaller widgets.
4. ......
5.  **Constructor Case $n$:** describe yet another way a new widget can be created from an collection of smaller widgets.
6. This can be repeat $n$ times


### Actual Proof
Given a claim, prove the claim for the base case and each constructor case(s).

1. **Base Case:** Prove the claim for the base case
2. **Inductive Hypothesis:** never actually stated, however, it is used in the inductive step. Basically, you assume the claim is true for each constructor case and using your assumption to help prove the each constructor case.
3. **Inductive Step:**
	1. Prove the claim for constructor case 1
	2. Prove the claim for constructor case 2
	3. ......
	4. Prove the claim for constructor case $n$

# Proof Examples

### 1. $k$-ary Tree
A $k$-ary is a tree where each node contain at most $k$ children. For example, a binary tree is a tree where each node has at most 2 children.

**Claim:** The number of nodes in a $k$-ary tree is no more than $\dfrac {k^{h}-1}{k-1}$
There is no such thing as a one-ary tree so the domain is all natural number greater than 1.

Given the recursive definition prove the claim for each constructor case: 
**Recursive Definition:**
- Base Case: A single node is a tree 
- Constructor Case: Given a collection of tree $\{T_1, T_2, T_3..... T_k\}$, and a node, $N$, we can build a bigger tree. 

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>I will apply structural induction on $k$-ary trees
>Let $k \in \Bbb N^{>1}$, selected arbitrarily
>Base Case: a single node
>- The height is 1 (depending how it is defined in most scenario the height of the root node is 0 in Computer Science but here we are counting that as one since it fit with the formula otherwise change the formula to $\dfrac {k^{h+1}-1}{k-1}$) and there is only 1 elements. Therefore, $1 \leq \dfrac {k^{1}-1}{k-1} \checkmark$
>  
>Inductive Step (There is only one constructor case): 
>- Suppose we have a $k$-ary tree with a root node, R, and it has up to $k$ amount of $k$-ary subtree. Let $h$ be the height of our tree. It suffices to show that the number of nodes in our tree is no more than \dfrac {k^{h}-1}{k-1}$.
>- The height of each subtree can be no more than $h-1$ since $h$ is the height of our tree. Therefore, we assume that the number of nodes in each subtree is no more than $\dfrac {k^{h-1}-1}{k-1}$ (This is the Inductive Hypothesis that is not stated). 
>- Since we have $k$ amount of subtrees the total number of nodes in all subtree combined is no more than: $k (\dfrac {k^{h-1}-1}{k-1}) = \dfrac {k^{h}-k}{k-1}$. 
>- Adding one for the root node, R. 
>- $\dfrac {k^{h}-k}{k-1} + 1 = \dfrac {k^{h}-1}{k-1}$, as desired $\blacksquare$
> </details>

### 2. Full Binary Tree

A full binary-tree is tree where each node has either zero or two children.<br> 
a. Define the recursive definition

>[!tip]
> <details>
> <summary>Proof</summary>
> 
>Base Case: A single node, $N$, (which has no children) is a full binary tree<br> 
>Constructor Case: Given two full binary trees $L$, $R$, and a single node, $N$ we can make a new full binary tree with $N$ as the root node and $L$ as the left children and $R$ as the right children.
> </details>

b. Prove the claim that a full binary tree has odd number of nodes using the recursive definition.

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $T$ be some full binary tree selected arbitrarily<br> 
>I will apply structural induction on $T$<br> 
>Base Case: A single node. The tree has one node therefore is odd $\checkmark$<br> 
>Inductive Step: 
>- Consider two full binary tree $L, R$ and a root node $N$ where $L$ is the left subtree and $R$ is the left subtree. 
>- Assume that the subtrees have odd number of nodes
>	- So $L$ has $2k + 1$  nodes for some $k \in \Bbb Z$
>	- and $R$ has $2m + 1$ nodes for some $m \in \Bbb Z$
>- The total number of nodes in the entire tree $T$ is $2k +1 + 2m + 1$ and plus 1 for the root node, $N$. So, $2k + 1 + 2m + 1 + 1 = 2k + 2m + 2 + 1 = 2(k + m + 1) + 1$. 
>- Note: $k + m + 1 \in \Bbb Z$
>- As we can see the number of nodes in $T$ is 2 times an integer plus one therefore it is odd, as desired $\blacksquare$ 
> </details>


### 3. Formal Language (Very Simple Example)
 
Normally, we would define a set that will be used but we will skipped that.<br>
Suppose $W$ is a set containing all strings where $W$ is closed under concatenation

Given the recursive definition prove the claim that no string can contain the letter "c".

**Recursive Definition:**
1. Base Case: an empty string denoted as $\lambda$ (lambda) is contain in the set of string $W$. Don't why computer scientist use this to define an empty string. 
2. Constructor Cases: Assuming $P, Q \in W$ 
	1. Constructor Case 1: $Pa \in W$ (Notation is weird I know $Pa$ means append the letter "a" to the end of the string $P$, who made this notation I do not know)
	2. Constructor Case 2: $abP \in W$ ($abP$ means append "ab" to the start of the string $P$)
	3.  Constructor Case 3: $PQ \in W$ ($PQ$ means append the string $Q$ to the end of the string $P$)
>[!tip]
> <details>
> <summary>Proof</summary>
> 
>Base Case: The empty string $\lambda$ does not contain any "c" $\checkmark$<br>
>Inductive Step: 
>1. Constructor Case 1: Assume $P$ does not contain any "c" (This the inductive hypothesis we are assuming the claim holds true for any strings $\in$ W), so $Pa$ does not contain any "c" $\checkmark$
>2. Constructor Case 2: Assume $P$ does not contain any "c", so $abP$ does not contain any "c" $\checkmark$
>3. Constructor Case 3: Assume $P$ and $Q$ does not contain any "c", therefore $PQ$ does not contain any "c" $\checkmark$
>$\blacksquare$
> </details>
