# Modular Operation, FTOA, and QRT

# Fundamental Theorem of Arithmetic (FTOA)

> Also known as the "Unique Prime Factorization Theorem"

> [!important] 
> The Theorem: 
>- For any $n > 1$, where $n \in \Bbb {N}^{>1}$, $n$ can be expressed as the product of primes (Existence) and there is only one way to express $n$ as product of primes (Uniqueness). 

So for example:
- $n = 2^{e_1} * 3^{e_2} * 5^{e_3} * ... * p_k^{e_k}$ (Some of the exponents may be 0)

or sometimes we just express the prime number as $p$ 
- $n = p_1^{e_1} * p_2^{e_2} * p_3^{e_3} * ... * p_k^{e_k}$

# Modular Operation 

In number theory, $a \mod n$ gives the remainder when $a$ is divided by $n$. The result is always between $0$ to $n-1$ (Inclusive). 

> Note: The result is never negative unless the divisor which is $n$ is negative but this is not important to us.

Example: 
- $16 \mod 4 = 0$
- $7 \mod 7 = 0$
- $18 \mod 5 = 3$ 
- $-17 \mod 5 = 3$ why?
	- When doing modular operation you really are just subtracting or adding by the divisor each time until the dividend is a positive number but smaller than the divisor. 
		- So, take $-17 \mod 5 = 3$ as an example. 
			- add by 5, $-17, -12, -7, -2, 3$ 
			- Or, $5 * 4 = 20, -17 +20 = 3$


## Modular Congruence
This has some weird notation used but you may see something like this: 
- $a = b (\mod n)$
	- This really just mean $a \mod n = b \mod n$ 
	- A better notation we use is $a \equiv_n b$

What the notation means is "$a$ is congruent to $b \mod n$"
- This means that if you take two numbers $a, b$ and did $a \mod n$ and $b \mod n$ then their result is the same. Therefore, $a$ is congruent to $b \mod n$. 

Examples: 
- $17$ is congruent to $1 \mod 4$ $(17 \equiv_4 1)$
	- $17 \mod 4 = 1$ and $1 \mod 4 = 1$, therefore 17 is congruent to 1 mod 4.
- $20$ is congruent to $10 \mod 5$ $(20 \equiv_5 10)$
	- $20 \mod 5 = 0$ and $10 \mod 5 = 0$, therefore 20 is congruent to 10 mod 5.
- Is $21$ congruent to $10 \mod 2$? $(21 \equiv_2 10)?$
	- No, $21 \mod 2 = 1$ and $10 \mod 2 = 0$, therefore 21 is not congruent to 10 mod 2. 

# Equivalence Theorem 
The followings are equivalent to each other (They all imply each other). For all $(a, b \in \Bbb {N})$
1. $a \equiv_n b$
2. $n|(a-b)$
3. $(\exists k \in \Bbb {Z})[a = b + kn]$


# Modular Arithmetic Theorem (MAT)

Let $a, b, c, d, n \in \Bbb Z$ and $n > 1$. Suppose $a \equiv_n b$ and $c \equiv_n d$. Then the following are true:
1. $(a + b) \equiv_n (b + d)$
2. $(a - b) \equiv_n (b - d)$
3. $ab \equiv_n bd$
4. $a^m \equiv_n c^m$ for all natural number $m$


Oftentimes, we use MAT to prove congruence in modular operation when dealing with large numbers.

>[!important]
>
>1. What is $12^6 \mod 5$? 
>		1. Well we know that $12 \mod 5 = 2$ which means $(12 \equiv_5 2)$. 
>		2. By number 4 on MAT, we can say $12^6 \equiv_5 2^6 = 64 \equiv_5 4$, therefore $12^6 \mod 5 = 4$
>			1. Note the difference between $\equiv_5$ and $=$. The above is saying that $2^6 = 64$ and 64 is congruent to 4 mod 5 (when in doubt just use $\equiv_5$, since saying $2^6 \equiv_5 64$ is still correct. Just don't saying something like $12^6 \equiv_5 2^6 = 64 = 4$, that is not correct, 64 is not equal to 4).
>2. What is $10^{12} \mod 9$? Use the same strategy.
>		1. We know that $10 \equiv_9 1$
>		2. By number 4 on MAT, we can say $10^{12} \equiv_9 1^{12} = 1$ (Again you can say $1^{12} \equiv_9 1$ and that will still be correct), $10^{12} \mod 9 = 1$
>3. How about $25^{777} \mod 13$?
>		1. We know that $25 \equiv_{13} 12$ but this isn't helpful
>		2. So what about $25 \equiv_{13} -1$ (Since 25 mod 13 = 12 and -1 mod 13 = 12 or start at 25 and count down by 13: 25, 12, -1)
>		3. By MAT, we can say $25^{777} \equiv_{13} (-1)^{777} \equiv_{13} -1 \equiv_{13} 12$, therefore $25^{777} \mod 13 = 12$
> 4. What is $2^{81} \mod 5$? (Hard one)
>   
> - <details>
> 	<summary>Solution</summary>
> 
> 	1. $2^{81} = (2^4)^{20}(2) = (16)^{20}(2)$
> 	2. Note : $16 \equiv_5 1$
> 	3. So by MAT, $2^{81} \equiv_5 (16)^{20}(2) \equiv_5 1^{20}(2) = 2$
>
> 	Answer: 2
> </details>


# Quotient-Remainder Theorem (QRT)

This really just means "what is the remainder?". Nothing fancy

Formal Definition (This is a mouthful) : $(\forall a \in \Bbb Z)(\forall n \in \Bbb Z^+)(\exists q,r \in \Bbb Z)[(a = nq+ r) \wedge (0 \leq r < n)]$

Summarizing what is saying above (in layman's terms): Suppose there is a number $a$ and a positive integer $n$, where $n$ is the divisor. Therefore, $a$ is equal to some number $q$ times the divisor $n$ plus some remainder $r$ where $r$ is between 0 and $n-1$ (Inclusive).
- For example, if $n = 4$ 
	- Then $a$ satisfy any of the following cases when $n = 4$
		1. $a = 4q$
		2. $a = 4q + 1$
		3. $a = 4q + 2$
		4. $a = 4q + 3$
	

>Very useful when proving "something about mod n" in exhaustive proof (Brute Force).


Example with QRT: 
- Let $a = 50$ and $n = 4$
	- $a = n(12) + 2$, remainder $r$ is 2 and $q$ is 12.

>[!tip] 
> "Fun Question": is $23^{81} - 13$ divisible by 12?
>
>1. Note: $23 \equiv_{12} -1$ (Since 23 mod 12 = 11 and -1 mod 12 = 11)
>2. Also note: $13 \equiv_{12} 1$, not really needed just here to showcase MAT
>3. So by MAT, $23^{81} - 13 \equiv_{12} (-1)^{81} - 1 = 0$
>
>The remainder is 0 so yes it is divisible by 12. 



# Proof Examples: 

#### 1. Claim: For all natural number $n$: $n$ is divisible by 9 if and only if the sum of the digits of $n$ is divisible by 9. 


> [!tip]
> <details> 
> <summary>Proof</summary>
> 
>Let $n \in \Bbb N$, selected arbitrarily
>1. Suppose we express the digit of $n$ as $d_0, d_1, d_2,....d_k$
>2. $n = 10^kd_k + 10^{k-1}d_{k-1} + .... + 10^2d_2 + 10d_1 + 10^0d_0$
>3. Observe that $10 \equiv_9 1$
>4. $n \equiv_9 d_k + d_{k-1} + .... + d_2 + d_1 + d_0$
>5. We may now reason as follow: 
>		1. $9|n \leftrightarrow n \equiv_9 0$ 
>			1. $\leftrightarrow d_k + d_{k-1} + .... + d_2 + d_1 + d_0 \equiv_9 0$
>			2. $\leftrightarrow 9 | d_k + d_{k-1} + .... + d_2 + d_1 + d_0$
>$\blacksquare$
> </details>



#### 2. Claim: n is not congruent to $n^2 - 4 \text { (mod) } 3$

> [!tip]
> Use QRT
> <details> 
> <summary>Proof</summary>
> 
>By QRT there exist a integer $q$ such that one of the following cases holds.<br> 
>Case $n = 3q$ which means $n \equiv_3 0$
>1. By MAT $(n^2 − 4) \equiv_3 (0^2 − 4) = -4 \equiv_3 2$
>2. $n \equiv_3 0$ but $(n^2 - 4) \equiv_3 2$, so $n \not\equiv_3 (n^2 -2) \checkmark$
>   
>Case $n = 3q + 1$ which means $n \equiv_3 1$
>3. By MAT $(n^2 − 4) \equiv_3 (1^2 − 4) = -3 \equiv_3 0$
>4. $n \equiv_3 1$ but $(n^2 - 4) \equiv_3 0$, so $n \not\equiv_3 (n^2 -2) \checkmark$
>   
>Case $n = 3q + 2$ which means $n \equiv_3 2$
>5. By MAT $(n^2 − 4) \equiv_3 (2^2 − 4) = 0 \equiv_3 0$
>6. $n \equiv_3 2$ but $(n^2 - 4) \equiv_3 0$, so $n \not\equiv_3 (n^2 -2) \checkmark$
>
>These cases are exhaustive $\blacksquare$
> </details>

#### 3. Claim: $\sqrt 5$ is irrational

> [!tip]
> Use FTOA
> <details>
> <summary>Proof</summary>
>Suppose BWOC $\sqrt 5$ is rational (meaning $\sqrt 5 \in \Bbb Q$)
>1. $\sqrt 5 = \dfrac {a}{b}$ for some $a,b \in \Bbb Z$ where $b \neq 0$
>2. Without the loss of generality (WLOG) and $\sqrt 5$ cannot be negative so we can assume $a > 0$ and $b > 0$
>3. $\sqrt 5 = \dfrac {a}{b}$
>4. $5 = \dfrac {a^2}{b^2}$
>5.  $5b^2 = a^2$
>
>$a$ and $b$ can both be expressed as the product of primes (FTOA Existence): 
>1. $a = 2^{e_1} * 3^{e_2} * 5^{e_3} * ... * p_k^{e_k}$
>2. $a^2 = 2^{2e_1} * 3^{2e_2} * 5^{2e_3} * ... * p_k^{2e_k}$
>3. $b = 2^{f_1} * 3^{f_2} * 5^{f_3} * ... * p_k^{f_k}$
>4. $b^2 = 2^{2f_1} * 3^{2f_2} * 5^{2f_3} * ... * p_k^{2f_k}$
>   
>   Going back to the equation $5b^2 = a^2$: 
>   1. The number of 5's on the LHS is $2f_3 + 1$
>   2. The number of 5's on the RHS is $2e_3$
>
>The FTOA states that prime factors has to be unique so the LHS must equal to the RHS but this impossible since LHS has a odd number of 5's while the RHS has a even number of 5's therefore $\sqrt 5$ must be irrational. $\blacksquare$
> </details>