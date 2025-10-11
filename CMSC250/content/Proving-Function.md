# Proving Functions


# Proving Injection

To prove that a function is injective we must show that if given two inputs and the output that comes out is the same then the inputs must be the same as well.

- $f : A \to B \text { is one to one } \leftrightarrow (\forall a, b \in A), (f(a)= f(b)) \to (a = b)$

>[!important]
>
>Let $f: A \to B$ such that..... $f$ is defined as some function<br>
>Claim: $f$ is one to one
>
>Proof: 
>- Let $a, b \in A$ such that $f(a) = f(b)$
>- .....
>- show that $a = b$
>
>Therefore, $f$ is one to one

## Disproving

To prove that a function is not injective find two distinct elements of the domain and if the output is the same then the function is not injective.

>[!important]
>
>Let $f: A \to B$ such that..... $f$ is defined as some function<br>
>Claim: $f$ is not one to one
>
>Proof: 
>- Find two distinct elements $a, b \in A$ where $a \neq b$
>- ....
>- Show $f(a) = f(b)$
>
>Therefore, $f$ is not one to one


# Proving Surjection

To prove function is surjective we must show that for every element in the codomain there exists an element of the domain that maps to that element of the codomain.

- $f : A \to B \text { is onto } \leftrightarrow (\forall y \in B), \text { there exists } x \in A \text { such that } f(x) = y$

>[!important]
>Let $f: A \to B$ such that..... $f$ is defined as some function<br>
>Claim: $f$ is onto
>
>Proof: 
>- Let $y \in B$, selected arbitrarily
>- Let $x =$ to some expression which is typically $f^{-1}$, so set $y = f$ then solve for $x$ that will give you the inverse. Doesn't always have to be the inverse.
>- Note that $x \in A$ because....
>- ....
>- show that $f(x) = y$
>
>Therefore, $f$ is onto

## Disproving 

To prove that a function is not surjective find an element of the codomain such that there is no elements in the domain that maps to that element of the codomain.


>[!important]
>Let $f: A \to B$ such that..... $f$ is defined as some function<br>
>Claim: $f$ is not onto
>
>Proof: 
>- Find a element $y \in B$
>- Show that for all $x \in A, f(x) \neq y$
>
>Therefore, $f$ is not onto

# Proving Bijection 

Do 2 parts: 
1. One for proving injection 
2. And another for proving surjection

>[!important]
>Let $f: A \to B$ such that..... $f$ is defined as some function<br>
>Claim: $f$ is bijective
>
>Proof: <br>
>- Part 1: prove that $f$ is injective
>- Part 2: prove that $f$ is surjective
>
>Therefore, $f$ is bijective

# Examples

#### 1. Claim: $f : \Bbb N \to \Bbb R$ such that $f(n) = \dfrac {4}{n + 3}$ is one to one

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $a, b \in \Bbb N$ such that f(a) = f(b). It suffices to show that $a = b$
>1. $\dfrac {4}{a + 3} = \dfrac {4}{b + 3}$
>2. Since $a \in \Bbb N, a \geq 0$ therefore $a + 3 > 0$
>3. Since $b \in \Bbb N, b \geq 0$ therefore $b + 3 > 0$
>4. So we can multiply both sides by $a + 3$ and $b + 3$
>5. $4(b + 3) = 4(a +3)$
>6. $(b+3) = (a +3)$
>7. $a = b$, as desired $\blacksquare$
> </details>

#### 2. Claim: $f : \Bbb Z \to \Bbb Z$ such that $f(x) = x \mod 4$ is not one to one

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Consider the value 0 and 4 which are both part of the domain 
>1. $f(0) = 0 \mod 4 = 0$
>2. $f(4) = 4 \mod 4 = 0$
>3. Since $f(0) = f(4), f$ is not one to one. $\blacksquare$
> </details>

#### 3. Claim: $f : \Bbb R \to \Bbb R$ such that $f(x) = 5x - 8$ is onto

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $y \in \Bbb R$, selected arbitrarily, I must show $f(x) = y$<br>
>Let $x = \dfrac {y + 8} {5}$, it suffices to show that $f(x) = y$<br>
>Note that $x \in \Bbb R$ due to closure of $\Bbb R$ under division by non-zero number and addition.
>1. $f(x) = 5 (\dfrac {y + 8}{5}) - 8$
>2. $= y + 8 - 8 = y$, as desired $\blacksquare$
> </details>


#### 4. Claim $f : \Bbb N \to \Bbb R$ such that $f(n) = \dfrac {4}{n + 3}$ is not onto

> [!tip]
> <details>
> <summary>Proof</summary>
> 
>Consider the value $-1$ which is an element of the codomain<br>
>Show that for all $n \in \Bbb N, f(n) \neq -1$<br>
>Let $a \in \Bbb N$, selected arbitrarily, it suffices to show $f(a) \neq -1$
>1. Suppose BWOC $f(a) = -1$
>2. $\dfrac 4 {a + 3} = -1$
>3. since $a \in \Bbb N, a \geq 0$ so $a + 3 > 0$
>4. We can multiply both sides by $a + 3$
>5. $4 = -(a + 3)$
>6. $4 = -a - 3$
>7. $7 = -a$
>8. $a = -7$ but this is a contradiction since $a \in \Bbb N, a$ cannot be negative since the $\Bbb N$ does not contains negative numbers. Therefore, $f(a) \neq -1, f$ is not onto. $\blacksquare$
> </details>