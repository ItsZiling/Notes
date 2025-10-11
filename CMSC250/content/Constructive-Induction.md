
# Constructive Induction
This is not an induction that we use for proof but rather a gimmick that we used to create claim. 
- Given a "hypothesis". We will sketch a proof that will help us come up with a claim that fits the hypothesis. 
- We will use strong induction to help us. 

> This is not a proof but rather like a sketch of a proof.

>[!important]
>Given the recurrence relation:<br> 
>$a_0 = 4, a_1 = 7$<br> 
>$(\forall k \in \Bbb N^{>1})[a_k = 2a_{k-1} + 5a_{k-2}]$<br> 
>Find integer constant $A, B$ such that $(\forall n \geq 0)[a_n \leq AB^n]$<br>
>Sketch of Proof:
>I will apply strong induction on $n$<br>
>- Base Case: $n = 0, 1$
>	- $n=0 : a_0 = 4 \leq AB^0=A$, so $4 \leq A$
>	- $n=0 : a_1 = 7 \leq AB^1$, so $7 \leq AB$
>		- The above are our constraints that we must satisfy 
>- Inductive Hypothesis: for some $k \geq 1$, assume that for all $i \leq k, a_i \leq AB^i$
>- Inductive Step: It suffices to show that $a_{k+1} \leq AB^{k+1}$
>	1. $a_{k+1}= 2a_{k} + 5a_{k-1}$ (By definition of Recurrence)
>	2. $\leq 2AB^k + 5AB^{k-1}$ (by I.H.)
>	3. (I want to be able to derive $\leq AB^{k+1}$)
>	4. $2AB^k + 5AB^{k-1} \leq AB^{k+1}$
>	5. Divide everything by $AB^{k-1}$
>	6. $2B + 5 \leq B^2$
>	7. get everything to one side
>	8. $0 \leq  B^2 - 2B - 5$
>	9. What value of $B$ makes the equation true? Since $B$ has to be an integer, $B$ has to be at least 4
>	10. So $B \geq 4$
>- Summary of our constraints: 
>	- $4 \leq A$
>	- $7 \leq AB$ (This is not needed since $A \geq 4$ and $B \geq 4$, the minimum value of $AB$ is 16, cannot not be less than that)
>	- $4 \leq B$ 
>
>Conclusion: The claim can be $(\forall n \geq 0)[a_n \leq 4(4)^n]$
