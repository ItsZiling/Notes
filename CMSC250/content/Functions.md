
# Functions
A function in math is denoted as $f(x)$ where given an input it produces an output.<br>
More formally, a function is assigning members of a set (domain) to the members of another set (codomain).
- The range of the function is not to be confused with codomain. The range consists of members of the codomain that are hit or have a member of the domain assigned to them. 
- The range is a subset of the codomain. 

> Function can be think of like a map in computer science. Where each key is assigned a value.

To defined a function the notation is used as follow $f : X \to Y$. This reads a "f is a function whose domain is the set X and codomain is the Y where members of the X is mapped to members of Y".

![Function.png](../assests/Function.png)

1. The domain of the function above is {2, 3, 4, 7}
2. The codomain of the function above is {5, 9, 10}
3. The range of the function above is {5, 10}


# Function vs Not a Function

A function is a function if and only if a member of the domain is assigned only one member of the codomain. Meaning a function cannot have a member of the domain where that member is mapped to more than one members of the codomain. 
- Remember the vertical line test.
- Multiple members of the domain can be mapped to a single member of the codomain. For example, the function above shows that 5 (a member of the codomain Y) has both 2 and 3 (members of the domain X) mapped to itself.

> Using a map in Computer Science, a key cannot be mapped to more than one value. But multiple different keys can map to the same value. 

# Expressing Function

There are multiple ways to express a function:<br>
Suppose we have the sets: $A = \{1, 2, 3, 4\}, B = \{3, 6, 9, 12\}$
1. $f : A \to B$ such that for all $a \in A, f(a) = 3a$
2. $f : A \to B$ such that $a \mapsto 3a$
3. $f = \{(1, 3), (2, 6), (3, 9), (4, 12)\}$
	1. Order pairs on a graph



# Total vs Partial

- A total function assigns every member of the domain to an element of the codomain. 
	- Just the word "function" means "total function". The word "total" is used in cases where it may not be obvious from the context that we are only talking about "total function". 
- A partial function **may not** assign every member of the domain
	- This is ambiguous as total functions are also partial functions but the converse is not true. So, if a function is not total, mathematician just say it is "not a total" function.


# Injective Function (one-to-one)
A function is injective if and only if every member of the range is associated with exactly one member from the domain. Meaning an injective function cannot have more than one member of the domain mapping to the same member of the range. 
- This is also called a "one-to-one relation"; a function that is one-to-one 
# Surjective Function (onto)
A function is surjective or onto if and only if every member of the codomain is associated with a member of the domain. Meaning if the range is the entire codomain.

# Bijective Function

A function is bijective if it is both injective and surjective.
- Sometimes called a "one to one correspondence"


>[!note]
>Given a function such as $\cos(x)$, in order to determine if the function is surjective, injective or bijective, a domain and codomain needs to be given.




# Inverse Image

Suppose $y$ is some element of the codomain.
- The inverse image of $y$ is a subset of the domain that maps to $y$

![Function.png](../assests/Function.png)

Given the function above again:
1. The inverse image of 5 is {2, 4}
2. The inverse image of 10 is {3}
3. The inverse image of 9 is {} or $\varnothing$, the empty set since nothing is mapped to 9.


# Inverse Function

The inverse of a function is denoted as $f^{-1}$. This reverse the input and the output.<br> 
- e.g.:  If $f(7) = 8$ then $f^{-1}(8) = 7$. The converse is also true.
- So $f(7) = 8 \leftrightarrow f^{-1}(8)= 7$

Not all functions have inverses.
- If a function is not one-to-one then it does not have a inverse.
- Think horizontal line test