
# Weak vs Strong Induction

The only difference between (weak) induction and strong induction is the inductive hypothesis. Strong induction also usually involves a lot more base cases.
- Anything that can be proven using (weak) induction can be proven using strong induction but not the other way around. If (weak) induction works then it often better to prove using (weak) induction since it is less messy than strong induction. 

> Strong induction is commonly used a lot with recurrence relation (See [Proof by (Weak) Induction](./Proof-by-Weak-Induction.md) on recurrence relation) when dealing with a sequence where each term is based on a lot more of its previous terms. When this happens (weak) induction doesn't work since the inductive hypothesis is not strong enough.

# Steps
At the beginning of the proof state "I will apply strong induction on $n$" or any variable you are inducting on. 

1. **Base Case:** Given a claim directly prove the base case(s) (Usually obvious what the base case is from context)
2. **Inductive Hypothesis:** Instead of assuming one thing, we will assume the claim holds for all elements up until the "last" base case. Then choose some arbitrarily element, suppose $k$, where $k$ that is greater than or equal to last base case and assume for all $i \leq k$ holds true (This is where we are assuming everything is true up until the last base case). This is a stronger hypothesis than (weak) induction.
	1. For example, if the last base case is $n =4$ then we choose some $k \geq 4$, and assume for all $i \leq k$ is true.
		1. It is wrong to say "choose some $k > 4$" because then we are assuming that $n =5$ is true but we never proven $n=5$ (as a matter of fact that is $k+1$ which is what we are trying to prove) as one of our base case(s) since we only proved everything up till $n=4$.
			1. Lets say $k$ is 4 then we have to prove $k+1$ which is 5. Since we have proven 4 in our base case we are allowed to prove 5 then we can use 5 to prove 6 and so on therefore $k+1$ is true and everything else after must be true. However, suppose $k$ was 5 instead then $k+1$ is 6 and suppose we manage to prove $k +1$ therefore everything after must follow but this proof is **INVALID!** This is because we proved everything AFTER 5 but 5 was never proven to be true, not in our base case and certainly not in the inductive step. 
3. **Inductive Step:** Prove that the claim holds true for the next element therefore, $k+1$. If $k+1$ is true then everything else must follow since $k$ was chosen arbitrarily. 

# Proof Examples: 

#### 1. Claim: Prove that for all $n \geq 0:$ $𝑎_𝑛 = 5 * 3𝑛 + 7 * 2𝑛$
Given the recurrence definition: 
- $a_0 = 12, a_1 = 29$, and for all $n \geq 2, 𝑎_𝑛 = 5𝑎_{𝑛−1} − 6𝑎_{n−2}$

> [!tip]
> <details>
> <summary>Proof</summary>
> 
> I will apply strong induction on $n$<br> 
> Base case $n = 0, 1$: 
> 1. $a_0 = 12 = 5 * 3(^0) + 7 * 2(^0) \checkmark$
> 2. $a_1 = 29 = 5 * 3(^1) + 7 * 2(^1) \checkmark$
>
>Inductive Hypothesis: For some $k \geq 1$, assume that for all $i \leq k$, $a_i = 5(3^i) + 7(2^i)$<br>
> Inductive Step: It suffices to show to $a_{k+1} = 5(3^{k+1}) + 7(2^{k+1})$
> 1. $a_{k+1} = 5a_{k} - 6a_{k-1}$, by definition of recurrence
> 2. $= 5(5(3^k) + 7(2^k)) - 6(5(3^{k-1}) + 7(2^{k-1}))$, by the I.H.
> 3. $= 25(3^k) + 35(2^k) - (30(3^{k-1}) + 42(2^{k-1}))$
> 4. $= 25(3^k) + 35(2^k) - 10(3^{k}) - 21(2^{k})$
> 5. $= 15(3^k) + 14(2^k)$
> 6. $= 5(3)(3^k) + 7(2)(2^k)$
> 7. $= 5(3^{k+1}) + 7(2^{k+1})$, as desired $\blacksquare$
> </details>


#### 2. Claim: Prove that for all $n \geq 0:$ $a_n \leq 3^n$
Given the recurrence definition: 
- $a_0 = 1, a_1 = 2, a_2 = 3$ and for all $n \geq 2, a_n = a_{n-1} + a_{n-2} + a_{n-3}$

> [!tip]
> <details>
> <summary>Proof</summary>
> I will apply strong induction on $n$<br> 
>
>Base Case n = 0, 1, 2:
>1. $a_0 = 1 \leq 3^0 \checkmark$
>2. $a_1 = 2 \leq 3^1 \checkmark$
>3. $a_2 = 3 \leq 3^2 \checkmark$
>
>Inductive Hypothesis: For some $k \geq 2$, assume that for all $i \leq k, a_i \leq 3^i$<br>
>Inductive Step: It suffices to show $a_{n+1} \leq 3^{n+1}$
>1. $a_{n+1} =  a_{n} + a_{n-1} + a_{n-2}$ by the definition of recurrence
>2. $\leq 3^n + 3^{n-1} + 3^{n-2}$ by the I.H.
>3. $\leq 3^n + 3^n + 3^n$, since $3^n \geq 3^{n-1} \text { and } 3^n \geq 3^{n-2}$
>4. $= 3(3^n)$
>5. $= 3^{n+1}$, as desired $\blacksquare$
> </details>
