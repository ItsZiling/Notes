

# Set Definition

A set is defined with two curly bracket: <br> Examples: 
1. $A = \{1, 2, 3\}$
2. $A = \{y \in \Bbb Z: y \equiv_2 0\}$

> The second one reads "A is a set of all integers y such that y is congruent to 0 mod 2". The symbol ":" means "such that", "for which" or "with the property of". Sometimes, instead of a colon ":" it may be a vertical bar "|". Again math notation can be confusing.

Set ignore all duplicates, and order does not matter for its elements. As a matter of fact a set should not contain any repeats. If it does we just ignore it. Therefore,
- $\{1, 2, 3\} = \{3, 2, 1\} = \{3, 3, 3, 1, 2, 2\}$, they are all equal to each other.

## Cardinality

Denoted as n(A) or $|A|$, and no the $||$ does not mean absolute value for set. This means the number of elements in set A or the size of set A. Again, ignoring all repeats. 

## Other Set Definition
- The universal set is denoted as $U$ 
	- To clarify, the universal set is a set that contains all sets including itself, however, this is not allowed under the Russell's Paradox which states no set is an element of itself, meaning a set cannot contain itself as an element or member (proven true). So, to avoid this paradox most modern set theory mathematics does not allow the existence of an universal set through some strict rules or sometimes the universal set is actually not referred to as a "set" itself, but rather it is refer to as a class or a "collection" of all sets (classes are part of set theory) since the paradox only applies to set, not collection. In other non-standard set theory it restrict the property of a universal set so that it can exist. But until you actually read the Russell's Paradox there is no need to worry too much about the universal set (Everything here is just an oversimplification). Otherwise, the universal set only refers to all elements of all given sets for a particular scenario or problem.
- Set can be infinite or finite 
- We know that $\in$ means "is an element of" then $\notin$ means "is not an element of".
- The empty set is denoted as $\varnothing$, where $\varnothing = \{\}$ meaning it does not contain any elements.
## Subset 

If set $B$ contains all the elements of another set $A$ then $A$ is a subset of $B$. 
- Denoted as $A \subseteq B \leftrightarrow (\forall x \in U)[x \in A \to x \in B]$
	- In proof we often use $(A \subseteq B \wedge x \in B) \to x \in B$

If set $B$ does not contains all the elements of another set $A$ then $A$ is not a subset of $B$. 
- Denoted as $A \nsubseteq B \leftrightarrow (\exists x \in U)[x \in A \wedge x \notin B]$


Any elements that are member of a set then another set containing only those elements is a subset of that set. This is called the **Relationship between membership and subset** 
- So, if $x \in A$ then $\{x\} \subseteq A$, this reads "if x is in A then a set containing x is a subset of A".
	- Formal definition: $(\forall x \in U)[x \in A \to \{x\} \subseteq A]$

If two sets are equal then they are subset of each other. 
- $A = B \leftrightarrow A \subseteq B \wedge B \subseteq A$ 

### Proper Subset (Somewhat Useful)

A proper subset is defined where a set is subset of another set but they cannot be the same set meaning they cannot equal each other. 
- Denoted as $A \subset B$ means $A \subseteq B \wedge A \neq B$

>A set is a subset of itself but not a proper subset of itself.
