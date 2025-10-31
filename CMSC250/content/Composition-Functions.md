# Composition Functions

Denoted as $g \circ f$ where $f$ is the inner function and $g$ is the outer function<br>

Suppose $f : X \to Y$ and $g : Y \to Z$ then $g \circ f$ will be denoted as: 
- $(g \circ f) : X \to Z$ where $(\forall x \in X)[(g \circ f)(x) = g(f(x))]$


![composition.png](../assets/composition.png)

1. The domain of $g \circ f$ is $X$
2. The codomain of $g \circ f$ is $Z$
3. What about the range?
   1. Recall that a range is a subset of the codomain and may or may not be the entire codomain. 
   2. The range of $f$ is a subset of the codomain $Y$ and the range of $g$ is a subset of the codomain $Z$, therefore the range of $g \circ f$ is a subset of the range of $g$ which may or may not be the entire codomain. 

Using the same diagram as above, the range:


![ComRange.png](../assets/ComRange.png)


> [!important]
> Given an input if the output of a composite function falls outside of its codomain then that composite function does not exist for that input.

Simple example of a composite function, if $g(x) = x^2$ and $f(x) = x + 1$
- Then $g(f(x)) = g(x+1) = (x + 1)^2 = (f(x))^2$
- If $x = 4$ then $g(f(4)) = g(4 + 1) = g(5) = 5^2 = (f(4))^2$