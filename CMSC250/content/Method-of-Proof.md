# Methods of Proof

# Definition of Common Domains

- $\Bbb {R}$ - All real numbers
- $\Bbb {Z}$ - All integers
- $\Bbb {Q}$ - All rational numbers, where $\dfrac {a}{b}$ where $a, b \in \Bbb {Z}$ and $b\neq 0$
- $\Bbb {N}$ - All natural numbers, 0 is counted 

> [!Note]
> 0 is not positive or negative. 0 is an even number. 


Irrational Number: 
- The formal way to denote irrational number is $\Bbb {R} - \Bbb {Q}$, this means take the set of all real numbers and subtract the set of all rational numbers and you end up with only irrational numbers. 
	- Sometimes it is denoted as $\Bbb {I}$ (Not formal mathematical notation). 

> At the time of writing this, Github markdown doesn't have the font to render domain symbols correcty. So, here is an image of they look like.

![Domains](../assets/Domains.png)

We can also restrict the domain:
- $\Bbb {R}^{+}$ - all positive real numbers
- $\Bbb {Z}^{even}$- all even integers.
- $\Bbb {N}^{prime}$- all prime natural numbers
- $\Bbb {Q}^{>2}$- all rational numbers greater than 2


# Closure

If you take two or more elements of a certain domain $(D)$ and apply a operation (subtracting, adding, multiplying, etc) and the result is still part of that domain $(D)$ then $D$ is close under that operation.

> [!important]
> - $\Bbb {Z}$ is close under subtraction, take any integers and subtract them you would get another integer. If we restrict this to only positive integer then it is not close under subtraction since you can take two positive integers and subtract them, you would sometimes get a negative integer.
> - Is $\Bbb {R}$ close under exponentiation?
>   - No, $-2^{1/2}$ is an imaginary number


# Number Theory

This is the study of the properties of Natural Numbers
- Perfect for writing proofs

It is used in a lot of Computer Science fundamentals

# Divisibility, and Factors 

Notation for divisibility is the vertical bar $|$ 
- $a|b$ means "a divides b" or
	- "a is a factor of b"
	- "b is divisible by a"

>[!tip]
> Formal Definition : $(\exists a, b, m \in \Bbb {N}) [a|b \leftrightarrow b = am]$

# Universal Generalization

This is one of the most important rules of inference that we used for this course. This involves all claims with universal quantifier.

Given a claim: $(\forall x \in D) [P(x)]$
- We select an arbitrarily element from the domain (D) then prove that $P(x)$ holds for the that arbitrarily element. Since the element was selected arbitrarily it means $P(x)$ holds for all elements in domain (D). 

>[!important] 
> Writing Proofs 
>
> - Start off with the claim at the beginning, then the proof. The beginning of the proof should start by saying some arbitrarily element in the domain. Clearly end the proof with some symbol such as a square.
>   - $Claim: (\forall x \in D) [P(x)]$
>   - $Proof:$ let $a \in D$, selected arbitrarily ........ 
>   - $P(a)$ holds $\therefore (\forall x \in D)[P(x)] \blacksquare$
>
> - Each step must follow logically.
> - Justification for each step should be clear.
>
> There are multiple ways to state a claim. You can write out plain English if you want.

> There are other rules of inference such as universal instantiation, existential generalization, and existential instantiation but these ones are not useful. You would probably use them instinctively in your proof anyways without realizing. 


# Even and Odd Definition (formal)

Definition for a even number: 
- $n \in \Bbb {Z}$ is even $\leftrightarrow (\exists k \in {Z})[n = 2k]$

Definition for a odd number: 
- $n \in \Bbb {Z}$ is odd $\leftrightarrow (\exists k \in {Z})[n = 2k +1]$

# Constructive Proof

Proof that involve using one example to prove a claim. These involves claim with existential quantifier. 

>[!tip]
> Example:
> 
> $Claim : (\exists a, b, c \in \Bbb {Z}) [a^2 + b^2 = c^2]$
> 
> $Proof :$ Let a = 3, b = 4 and c = 5
> 
> $a^2 + b^2 = 9 + 16 = 25 = c^2$
> $\blacksquare$ 


>[!important] 
> Counterexample: 
>
> If you think a claim is false. Provide an example to show it. This means assign some values and show the claim is false. 
> - Generally speaking, it is easy to disprove an universal quantifier since you just have to find one example in which the proposition (statement) does not hold but hard to disprove an existential quantifier because you have to prove the proposition does not hold for all elements in the domain. 


# Proof by Exhaustion (Brute Force)

Proof by exhaustion is basically you take all possible cases of a claim and prove that each cases work. Hence, you exhaust all possible cases therefore the claim holds true.
- Can be very boring. However, sometimes it is easier to break a claim into multiple cases.

>[!note] 
> Proof by Computer
> 
> - You can use a computer program to prove a claim. As a matter of fact some claims were proven using computer programs. 

# Proof by Contradiction
Sometimes it is hard to prove a claim directly, so instead we assume negation of the claim and if the proof leads to a contradiction then the original claim must be true. 


> [!important]
>
> $Claim :$ $p$
> 
> $Proof :$ 
> - Assume $\neg p$
>	- .... leads to a contradiction
> - therefore, $p$.

# Proof involving Implications

Claim involving implication generally goes something like this: if something then something else. 
- When proving claim with implication we assume the LHS is true and try to derive the RHS. 
	- We can use our assumption of the LHS to help derive the RHS.

>Why assume the LHS? Because what is the point of proving a claim if the LHS is false. If the LHS is false then the statement is automatically true. 

> [!important]
>
> $Claim :$ If $p$ then $q$
>
> $Proof :$ 
> - Assume $p$ 
>	- derive $q$
> - Therefore, $p \to q$


## Proof by Contraposition
Recall that a statement with implication is equivalent to its contrapositive. Sometimes it is hard to prove the original statement so instead we prove its contrapositive. 

> [!important]
>
> $Claim :$ If $p$ then $q$
> 
> $Proof :$ Prove by Contraposition
> - Assume $\neg q$ 
>	- derive $\neg p$
> - Therefore, $p \to q$

## Contradiction with Implication

This is also valid. We can assume the LHS but negate the RHS side if the proof leads to contradiction then the claim must be true.

> [!important]
>
> $Claim :$ If $p$ then $q$
> 
> $Proof :$ 
> - Assume $p$
>	- Suppose by the way of contradiction (BWOC), assume $\neg q$
>	- ...... leads to a contradiction 
>	- therefore $q$.
> - Therefore, $p \to q$

# Proof by Equivalence

Two methods to do this

Method 1: We can either just go down one by one: 

> [!important]
>
> $Claim :$ $p$ if and only if $q$
> 
> $Proof :$ 
> - $p \leftrightarrow s1$
>	- $\leftrightarrow s2$
>	- $\leftrightarrow s3$
>	- $\leftrightarrow s4$
>	- $\leftrightarrow q$
> - Therefore $p \leftrightarrow q$


> [!caution]
> 
> Problem with the method above: 
> - It does not always works
> - It must work backward (Sometimes it works forward but not backward)
> - Easy to make mistake


Method 2: The second method will always work. Basically, we break it into two parts. Assume the LHS then derive the RHS (part 1) and then assume the RHS then derive the LHS (part 2).

>[!important ]
>
> $Claim :$ $p$ if and only if $q$
> 
> $Proof :$ 
> - Part I : show $p \to q$
>	- ....
> - Part II : show $q \to p$
>	- ....


# Proof Examples 

#### 1. Claim: $(\forall x, y \in \Bbb Z)[\text {If x is even and y is odd then xy is even}]$

> [!tip]
> <details> 
> <summary>Proof</summary>
>
> Let $x, y \in \Bbb Z$ selected arbitrarily<br />
> It suffices to show that $xy$ is even<br />
> Assume $x$ is even and $y$ is odd
> 1. Since $x$ is even, $x = 2k$, for some $k \in \Bbb Z$ 
> 2. Since $y$ is odd, $y = 2m + 1$, for some $m \in \Bbb Z$
> 3. $xy = 2k(2m+1) = 4km + 2k = 2(2km + k)$
> 4. Note: $2km + k \in \Bbb Z$
> 
> We have written $xy$ as 2 times some integer therefore $xy$ is even, as desired $\blacksquare$
> </details>



#### 2. Claim: $(\forall n \in \Bbb N) [n^2 + n \text { is even}]$
Consider two cases when n is even and when n is odd.


>[!tip]
> <details> 
> <summary>Proof</summary>
> 
> Let $a \in \Bbb N$, selected arbitrarily, it suffices to show $a^2 + a$ is even<br>
> Case $a$ is even: 
> 1. Since $a$ is even, $a = 2k$, for some $k \in \Bbb Z$
> 2. $a^2 + a = (2k)^2 + 2k = 4k^2 + 2k = 2(k^2 + k)$, therefore $a^2 + a$ is even $\checkmark$
>   
> Case $a$ is odd: 
> 1. Since $a$ is odd, $a = 2m +1$, for some $m \in \Bbb Z$
> 2. $a^2 + a = (2m + 1)^2 + 2m + 1 = 4m^2 + 4m + 1 + 2m + 1 = 4m^2 + 6m + 2 = 2(2m^2 + 3m + 1)$, therefore $a^2 + a$ is even $\checkmark$
>   
>   These cases are exhaustive, hence $a^2 + a$ is even, as desired $\blacksquare$
> </details> 


#### 3. Claim: There are no primes strictly between 113 and 127
You can either prove that all numbers strictly between 113 and 127 are no prime or you can can cut down half of the cases by only having to consider odd numbers.

>[!tip]
> <details>
> <summary>Proof</summary>
>All even numbers between 113 and 127 are divisible by 2 therefore they are composite so we just need to consider the odd numbers between 113 and 127. 
>
>1. Case 115: $115 = 5 * 23$, not prime $\checkmark$
>2. Case 117: $117 = 9 * 13$, not prime $\checkmark$
>3. Case 119: $119 = 7 * 17$, not prime $\checkmark$
>4. Case 121: $121 = 11 * 11$, not prime $\checkmark$
>5. Case 123: $123 = 3 * 41$, not prime $\checkmark$
>6. Case 125: $115 = 5 * 23$, not prime $\checkmark$
>
>These cases are exhaustive therefore there are no primes strictly between 113 and 127, as desired $\blacksquare$
> </details>

#### 4. Claim: $(\forall x \in \Bbb I^+)[\sqrt x \text { is irrational}]$
It is hard to prove something is irrational directly so instead use contradiction.

> [!tip]
> <details> 
> <summary>Proof</summary>
> 
>Let $x \in \Bbb I^+$, selected arbitrarily, it suffices to show that $\sqrt x$ is irrational (you can recycle variable)<br> 
>Suppose BWOC $\sqrt x$ is rational (meaning $\sqrt x \in \Bbb Q$)
>1. $\sqrt x = \dfrac {a}{b}$ for some $a,b \in \Bbb Z$ where $b \neq 0$
>2. Without the loss of generality (WLOG) since $x$ is positive and $\sqrt x$ cannot be negative we can assume $a > 0$ and $b > 0$
>3. $\sqrt x = \dfrac {a}{b}$
>4. $x = \dfrac {a^2}{b^2}$
>5. Note: $b^2 \neq 0$ since $b \neq 0$ and $a, b$ are both integers and integers is closed under multiplication. 
>6. So, $x \in \Bbb Q$ but this contradict our decision where $x \in \Bbb I^+$ therefore it must be that $\sqrt x$ is irrational. $\blacksquare$
> </details>


#### 5. Claim: $(\forall a, b \in \Bbb Z)[\text {if } ab \text { is even then a is even or b is even}]$


> [!tip]
> Use Contraposition.
> <details> 
> <summary>Proof</summary> 
> 
>Let $a, b \in \Bbb Z$, selected arbitrarily<br>
>I will prove this with contraposition<br> 
>Assume $a$ is odd AND $b$ is odd, it suffices to show ab is odd. 
>1. Since $a, b$ are both odd, 
>2. $a = 2k + 1$, for some $k \in \Bbb Z$
>3. $b = 2m + 1$, for some $m \in \Bbb Z$
>4. $ab = (2k + 1)(2m + 1) = 4km + 2k + 2m + 1 = 2(2km + k + m) + 1$, so $ab$ is odd. 
>
>$\therefore$ by contraposition if $ab$ is even then $a$ is even or $b$ is even $\blacksquare$
> </details>


#### 6 Claim: $(\forall n \in \Bbb Z)[n \text { is even} \leftrightarrow n^2 \text { is even}]$


> [!tip]
> Prove it using two parts
> <details>
> <summary>Proof</summary>
> 
>Let $n \in \Bbb Z$, selected arbitrarily<br>
>
>Part 1: show $n$ is even $\to n^2$ is even
>1. Assume $n$ is even, it suffices to show $n^2$ is even
>2. Since $n$ is even, $n = 2k$, for some $k \in \Bbb Z$
>3. $n^2 = (2k)^2 = 4k^2 = 2(2k^2)$, so $n^2$ is even $\checkmark$
>
>Part 2: how $n^2$ is even $\to n$ is even
>1. I will prove this using contraposition
>2. Assume $n$ is odd, it suffices to show $n^2$ is odd
>3. since $n$ is odd, $n = 2m + 1$, for some $m \in \Bbb Z$
>4. $n^2 = (2m + 1)^2 = 4m^2 + 4m + 1 = 2(2m^2 + 2m) + 1$, so $n^2$ is odd
>5. Therefore, by contraposition $n^2$ is even $\to n$ is even $\checkmark$
>
>Combining both parts, we can see that $n \text { is even} \leftrightarrow n^2 \text { is even}$
> </details>