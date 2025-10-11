


> [!note]
> Read [Modular Operation, FTOA, and QRT] first. 


Sometimes, universal generalization does not help us prove some claims so instead we use induction. There are three induction methods we can use (there are actually more than 3 but this is an introductory course so only 3 is covered). 
- Induction (people like to call this weak induction)
- Strong Induction 
- Structural Induction

A common use of induction is proving summation formula.

>A use of induction in Computer Science program is recursion.


# Steps
There are three steps in an induction proof. At the beginning of the proof state "I will induct on $n$" or any variable you are inducting on. 

1. **Base Case:** Given a claim directly prove the base case(s) (Usually obvious what the base case(s) are from context)
2. **Inductive Hypothesis:** Assume that the claim is true for some arbitrarily element, suppose $k$. 
3. **Inductive Step:** Prove that the claim holds true for the next element therefore, $k+1$, this is where you actually prove the claim. Somewhere in this step you would use the inductive hypothesis. Proving $k+1$ means that every elements after must also follow since $k$ was chosen arbitrarily. 


>[!example]
>
>Best way to show induction is the use of domino effect.<br>
>Consider the Claim: For all $n > 0$ (Natural Number), domino number $n$ will fall<br>
>Proof:
>- Base Case: n = 1, domino number 1 will fall because I knock it over
>- Inductive Hypothesis: Assume for some (arbitrarily) $k > 0$, domino number $k$ will fall
>- Inductive Step: It suffices to show that domino number $k+1$ (the next domino after domino number $k$) will fall 
>	- Since domino number $k$ falls (by the inductive hypothesis), it will knock over domino number $k+1$ causing it to fall, as desired (assuming nothing weird happens with physics). $\blacksquare$

>[!important]
>Induction is very useful when dealing with infinite list such as all natural numbers. Generally speaking, we like to use natural number with induction since it blends well with the base case and inductive hypothesis. This is because natural number starts at 0 then 1, 2, 3.... etc (like dominos). Therefore, in most cases the domain is all natural numbers when dealing with induction proof. There is no need to explicitly state it, it is obvious from the context. 

>[!important] Also important: Recurrence Relation
>If you do not already know what this is. A recurrence relation is basically what defines a sequence where some $k$-th term within the sequence is equal to some previous terms in the sequence. For example, a recurrence relation could be the following definition of a sequence where suppose $\forall k > 2, a_k = a_{k-1} + a_{k-2}$. This means that a term within the sequence is the sum of its previous two terms.
>
>> This is used often with induction




# Proof Examples: 

#### 1. Claim: $(\forall n \geq 1)[\displaystyle \sum_{i = 1}^{n} i = \dfrac {n(n+1)}{2}]$

>[!success]- Proof:
>I will induct on n<br> 
>Base case n = 1: $\displaystyle \sum_{i = 1}^{n} i = 1 = \dfrac {1(1+1)}{2} = \dfrac {n(n+1)}{2}$<br> 
>Inductive Hypothesis: assume $\displaystyle \sum_{i = 1}^{k} i = \dfrac {k(k+1)}{2}$, for some $k \geq 1$<br>
>Inductive Step: it suffices to show $\displaystyle \sum_{i = 1}^{k + 1} i = \dfrac {(k+1)(k+2)}{2}$
>1. $\displaystyle \sum_{i = 1}^{k + 1} i = \displaystyle \sum_{i = 1}^{k} i + k + 1$
>2. $= \dfrac {k(k+1)}{2} + k +1$, by the Inductive Hypothesis (I.H.)
>3. $= \dfrac {k(k+1) + 2(k + 1)}{2}$
>4. Factoring the numerator yields
>5. $= \dfrac {(k + 1)(k + 2)}{2}$, as desired $\blacksquare$



#### 2. Claim: $(\forall n \geq 1)[\displaystyle \sum_{i = 1}^{n} \dfrac {1}{i^2} \leq 2 - \dfrac {1}{n}]$
>[!success]- Proof: 
>I will induct on<br>
>Base case n = 1: $\displaystyle \sum_{i = 1}^{n} \dfrac {1}{i^2} = 1 \leq 2 - \dfrac {1}{1} = 2 - \dfrac {1}{n}$
>Inductive Hypothesis: for some $k \geq 1$, assume $\displaystyle \sum_{i = 1}^{k} \dfrac {1}{i^2} \leq 2 - \dfrac {1}{k}$<br> 
>Inductive Step: It suffices to show  $\displaystyle \sum_{i = 1}^{k+1} \dfrac {1}{i^2} \leq 2 - \dfrac {1}{k+1}$
>1. $\displaystyle \sum_{i = 1}^{k+1} \dfrac {1}{i^2} = \displaystyle \sum_{i = 1}^{k} \dfrac {1}{i^2} + \dfrac {1}{(k+1)^2}$
>2. $\leq 2 - \dfrac {1}{k} + \dfrac {1}{(k+1)^2}$, by I.H.
>3. $= 2 - \dfrac {(k + 1)^2 + k}{k(k+1)^2}$
>4. $= 2 - \dfrac {k^2 + 2k + 1 + k}{k(k+1)^2}$
>5. $= 2 - (\dfrac {k^2 + k}{k(k+1)^2} + \dfrac {2k +1}{k(k+1)^2})$
>6. $= 2 - \dfrac {1}{(k+1)} - \dfrac {2k +1}{k(k+1)^2}$
>7. $\leq 2 - \dfrac {1}{k+1}$ since $k \geq 1$ and $0 > -\dfrac {2k +1}{k(k+1)^2}$, as desired $\blacksquare$


#### 3. Claim: For all $n \geq 0 : 6 | 7^n - 1$ 

>[!success]- Proof: 
>Base case n = 0: $7^0 - 1 = 0, 6|0 \checkmark$<br> 
>Inductive Hypothesis: for some $k \geq 0$, assume $6|7^k -1$<br> 
>Inductive Step: It suffices to show $6 | 7^{k+1} -1$
>1. By the inductive hypothesis, we know that $6|7^k - 1$ therefore $7^k -1 = 6m$ for some $m \in \Bbb Z$. Rearranging we get $7^k = 6m +1$
>2. $7^{k + 1} - 1= 7(7^k) -1$
>3. $= 7(6m + 1) - 1$, by the I.H and substitution from 1
>4. $= 42m + 7 - 1$
>5. $= 42m + 6$
>6. $= 6(7m + 1)$
>
>We have shown that $7^{k+1} - 1$ can be written as $6$ times some integer therefore $6|7^{k+1} - 1$, as desired $\blacksquare$
