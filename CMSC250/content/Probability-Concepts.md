# Probability Concepts

# Multiplication Rule for Independent Event

- The probability of event $E$ is denoted as $P(E)$

If $E_1, E_2, E_3, ...., E_k$ are all mutually independent. Then: 
- $P (E_1\cap E_2 \cap E_3 \cap .... \cap E_k) =P(E_1)P(E_2)P(E_3).....P(E_k)$


>[!tip]
> <details> 
> <summary>Example: What is the probability of flipping all tails if you flip a coin 5 times? </summary>
>
> Answer = $(\dfrac {1}{2})^5$
> 
>The probability of getting a tail 0.5 and each flip is independent of each other so the probability of flipping a tail on the first flip is 0.5, the second flip is 0.5, etc. 
> </details>

> Think "and": "Event 1 and event 2 and event 3 and .... and event k"

# Probability with Complement

The complement of event $E$ is denoted as $E^c$, which reads "event $E$ does not happen".
- The probability of $E^c$ is the 1 minus the probability of $E$ (The probability in which $E$ does happen). 
	- So, if the probability of some event happening is 0.32 then the probability of it not happening is 0.68. 
- Formula: $P(E^c) = 1 - P(E)$



>[!Tip] 
>1. What is the probability that at least one digit in a randomly selected 4-digit PINS is repeated? 
>2. If you have 8 blue balls and 5 red balls in a bag what is the probability that you draw at least one red ball in 4 draws (ball is put back into the bag after each draw)? 
>
> <details>
> <summary>Solution</summary>
>
> 1. $P(\text {at least one digit repeated}) = 1 - P(\text {no digit repeated})$
>       - $P(\text {no digit repeated}) = \dfrac {10 * 9 * 8 * 7}{10000}$, the numerator is the amount of 4-digit pins with no repeated digit and 10000 is the amount of 4-digit pins there is. 
>       - $P(\text {at least one digit repeat}) = 1 - \dfrac {10 * 9 * 8 * 7}{10000}$
> 2. $P(\text {at least one red ball in 4 draws}) = 1 - P(\text {only blue balls drawn})$
>       -  $P(\text {only blue balls drawn}) = (\dfrac 8 {13})^4$, there are 13 balls  8 of them are blue balls. A ball is drawn 4 times with replacement. 
>       - $P(\text {at least one red ball in 4 draws}) = 1 - (\dfrac 8 {13})^4$
> </details>



# Addition Rule for Mutually Exclusive Event

If $E_1, E_2, E_3, ...., E_k$ are all mutually exclusive. Then: 
-  $P (E_1\cup E_2 \cup E_3 \cup .... \cup E_k) = P(E_1) + P(E_2)+ P(E_3)+ .....+P(E_k)$

>Think "or": "Event 1 or event 2 or event 3 or .... or event k". Basically each event is a partition of the sample space. 


>[!tip] 
> Example: Five students and Five Chairs
>
>Suppose is five chairs in a row (not a circle)
>
>1. How many ways can you seat those five students? 
>2. If James and Nancy are both students of the group. What is the probability they are seated next to each other? (There are two ways to do this)
>
> <details>
> <summary>Solution</summary>
> 
> 1. $5! = 120$
> 2. There are five chairs we know that James and Nancy has sit next to each other. 
>       - First way use partition: Lets denote James as J and Nancy as N. All the possible cases that James and Nancy can sit next to each other are:
>		    1. J N __ __ __
>		    2. __ J N __ __
>		    3. __ __ J N __
>		    4. __ __ __ J N
>		    5. N J __ __ __
>		    6. __ N J __ __
>		    7. __ __ N J __
>		    8. __ __ __ N J
>       - There are eight cases in total and in every cases we have three other students that we haven't seated yet and the number of ways to seat the other three student is $3! = 6$. Since there are eight cases we can just multiply $6 * 8 = 48$ possible ways where James and Nancy can sit next to each other. Therefore, the probability of James and Nancy sitting next to each other is $\dfrac {48}{120}$. This uses the addition rule because each cases is a partition of the sample space so it is basically adding up all the partitions divided by the sample space: $\dfrac {6}{120} + \dfrac {6}{120} + ....$ (8 times).
>       -  The second way is to use the multiplication rule for counting or the steps in a process. So, there are 4 areas where James and Nancy can sit next to each other. Either the first and second seats or the second and third seats or the third and fourth seats or the fourth and fifth seats. There are 2 ways to order them either JN or NJ. There 3 other students we have to seats and the number of way to seat them is $3! = 6$. Multiply them up you get $4 * 2 * 6 = 48$ and the probability is $\dfrac {48}{120}$.



## The Inclusion/Exclusion Rule

The addition rule only works if the events are mutually exclusive but what if the events overlapped. The area where they overlap is the intersection (use a Venn Diagram to see). <br>
![[venn diagram.png]]

For any two sets $A, B$ not mutually exclusive, the formula to calculate the probability of A or B is: 
- $P(A \cup B) = P(A) + P(B) - P(A \cap B)$ assuming A and B are independent otherwise you cannot do $P(A \cap B)$.
	- Basically, the idea is to add up the probability of A and the probability of B then subtract the intersection. Subtracting the intersection is necessary because we double counted the intersection when doing $P(A) + P(B)$. 
		- Example:
			- Suppose A is 0.5 and B is 0.3, if they are **mutually exclusive** then we can just add them up so the probability of A or B will be 0.8. 
			- Suppose they are **NOT** mutually exclusive then we need to subtract the intersection once since $0.5 + 0.3 = 0.8$ is double counting the intersection. So the calculation would instead be do $0.5 + 0.3 - (0.5 * 0.8) = 0.65$ to get the actual probability of A or B if they are not mutually exclusive. 
- Similarly, the size of A or B is: 
	- $|A \cup B| = |A| + |B| - |A \cap B|$

> Remember, the formula above only works for 2 sets. Anything with more than 2 sets are a bit more complicated and it just better to use the complement rule for probability instead. Sometimes it may be easier with the complement rule. So basically $P(A \cup B) = 1 - P(A^c \cap B^c)$. You take the complement $(A \cup B)$ to get $(A^c \cap B^c)$. This is easier to do since we are just using the multiplication rule assuming $A^c$ and $B^c$ are independent from each other. So, suppose A is 0.5 and B is 0.3 then not A is 0.5 and not B is 0.7. Multiplying them yields $0.5*0.7 = 0.35$ and $1 - 0.35 = 0.65$ which is the same as the example above.

### Examples 


#### 1.
Stephen King has written 57 books that can be classified as horror. 40 of the books he has written were before 2000 and 35 of the horror books were written before 2000.
1. How many books are either horror or were written before 2000? 

Venn Diagram:
![venn_example.png](../assets/venn_example.png)

Breakdown: 
1. 57 books written are horror but 35 of those were written before 2000 so $57-35 = 22$ for the amount of horror books written but are not written before 2000.
2. 40 of his books were written before 2000 but 35 of those are horror so $40 - 35 = 5$ books written before 2000 but are not horror.

Answer to the question is: $22 + 35 + 5 = 62$ books are horror or written before 2000.<br>
#### 2. What is the probability of getting an king (K) or an diamond (D) in a deck of cards.

1. There are 4 kings in a deck of cards so the probability of getting a king is $\dfrac {4}{52}$
2. There are 13 cards with diamond so the probability of getting a diamond is $\dfrac {13}{52}$
3. There is 1 king with a diamond so the probability of getting a king with a diamond is $\dfrac 1{52}$
5. $P(K \cup D) = P(K) + P(D) - P(K \cap D)$
	1. $= \dfrac {4}{52} + \dfrac {13}{52} - \dfrac {1}{52} = \dfrac {16}{52}$