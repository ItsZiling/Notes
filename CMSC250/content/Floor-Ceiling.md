


> [!important] 
> ## Floor Definition:
> 
> Suppose we have $x$
>- The floor of $x$ is denoted as follow : $\lfloor x \rfloor$
>
>Suppose $n = \lfloor x \rfloor$ then for all $x \in \Bbb R, n \in \Bbb Z$
>- $n = \lfloor x \rfloor \leftrightarrow n \leq x < n + 1$
>
>Flooring a number means round down so: 
>-  $\lfloor 6.7 \rfloor = 6$
>-  $\lfloor 9 \rfloor = 9$



> [!important]
> ## Ceiling Definition:
> 
>Suppose we have $x$
>- The ceiling of $x$ is denoted as follow : $\lceil x \rceil$
>
>Suppose $n = \lceil x \rceil$ then for all $x \in \Bbb R, n \in \Bbb Z$
>- $n = \lceil x \rceil \leftrightarrow n - 1 < x \leq n$
>
>Taking the ceiling of a number means round up so:
>- $\lceil 6.3 \rceil = 7$
>- $\lceil 5 \rceil = 5$


# Proof Example: 

#### 1. Claim: For any real number $x$: If $x$ is not an integer then $\lfloor x \rfloor + \lfloor -x \rfloor = -1$

>[!tip]
> <details>
> <summary>Proof</summary>
> 
>Let $x \in \Bbb R$, selected arbitrarily<br>
>Assume $x$ is not an integer, it suffices to show $\lfloor x \rfloor + \lfloor -x \rfloor = -1$
>1. Since $x$ is not an integer, $x$ cannot equal to its floor so $\lfloor x \rfloor < x < \lfloor x \rfloor + 1$
>4. Multiply the inequality by -1 yields 
>5. $- \lfloor x \rfloor > -x > - \lfloor x \rfloor - 1$
>7. Observe that $-x$ is not an integer since $x$ is not an integer therefore by the definition of floor
>8. $\lfloor -x \rfloor = - \lfloor x \rfloor - 1$ (remember the floor means round down)
>9. $\lfloor x \rfloor + \lfloor -x \rfloor = \lfloor x \rfloor + ( - \lfloor x \rfloor - 1) = -1$, as desired $\blacksquare$
> </details>
