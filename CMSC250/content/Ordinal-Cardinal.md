# Ordinal and Cardinal


# Ordinal
Consider the set $\{0, 1, 2\}$
- If that was the set of "natural number" what is the "first" (next) natural number that follows it?
	- It would be 3

This is the same idea with ordinal (which is based on natural number) where a structure has an "ordered structure" to it like first, second, third, etc. Basically, in layman's term, to represent the position of an element in a set or sequence.
- This is a generalization of ordinal numeral (first, second, third, etc. where each corresponds to a natural number, zeroth would corresponds to 0). 
- It is commonly used to represent infinity thus extending to infinite set. 

> Yes, there are different sizes of infinity. 


**Definition**:

Ordinal are numbers used to describe the "shape" of a well-ordering relation
- Every well-ordering is isomorphic to an ordinal 
  - In math, isomorphic means two structures have the same structure even though they appear different on the surface. For example, {1, 2, 3} is essentially the same as {first, second, third}. The only difference lies in their naming of the elements but each element has a one to one correspondence of the other element of the other set. So, "1" would be map to "first" and so on therefore taking the inverse of {1, 2, 3} would give {first, second, third} and vice versa.
	- Basically, if you map two structures of the same type together and preserve their structure, you can reverse one structure to get the other structure through inverse mapping.
  - In the context of ordinal, isomorphic means that two well-order sets have the same "order structure" even if the elements are different so as long as the two sets are identical in their ordering. 
	- So, every well ordered set is isomorphic to an unique ordinal number just mean that we can assign an ordinal number to a well ordered set that preserve its order structure or order relation between its element.

> In simple term, isomorphic just means they have the same structure. 


## Omega

Denoted as $\omega$
- It is the limit ordinal or the ordinal number that represent the natural ordering of natural numbers (basically, omega represent the set of natural number in simple terms). However, this is oversimplification since omega does not only apply to natural ordering of natural numbers. 
- Natural ordering just means $1< 2 < 3 <...$ 
  - Which means in ordinal number instead of using natural ordering I can write something like $2 < 1 <...$ under ordinal number I can do that. This is because I ordered 2 as first and 1 as second. 


> [!tip]
> The idea is to not think ordinal number as actual numbers but rather the way how elements are ordered in their position.


To oversimplify for the sake of this being an introductory course. 
1. $\omega$ represents the natural ordering of natural number which is the limit ordinal of natural number
	1. It is the first infinite ordinal after all natural numbers therefore it is the least element that is bigger than every natural number. 
		1. Think of it like the "infinity" of natural numbers, the smallest infinity. 
	2. It is the set of all finite ordinals (natural numbers).
		1. Basically, take any smaller ordinal, in this case natural number, there is always a natural number larger than it but smaller than $\omega$. 
	3. It is the first countable element after all natural numbers that represent infinity, so the "first countable infinity".
2. Any ordinal is the set of all its preceding ordinals.
	1. Suppose, we have the set $\{0, 1, 2, 3,....\}$
		1. 3 is the ordinal number that represents $\{0, 1, 2\}$ so $3 = \{0, 1, 2\}$ 
		2. 3 is the first natural number that comes after ordinal 2. 
	2. Since $\omega$ is the first infinite ordinal that comes after all the natural numbers which are all finite ordinal numbers (based on its natural ordering) hence all natural numbers precedes $\omega$. 
		1. So, $\omega = \Bbb N$
		2. $\omega = \{1, 2, 3, 4, ...\}$


## Expressing Limit Ordinal

Lets express the limit ordinals. Starting with the natural ordering of natural numbers. I will express the limit with a vertical bar "|"
1. $0, 1, 2, 3, 4, 5, 6,....... |$ 
	1. As we know the limit ordinal that represent the bar is $\omega$, so continuing the trend.
2. $\omega, \omega + 1, \omega + 2, \omega + 3, ......|$
	1. The limit ordinal of this is $2\omega$ because as you continue to do $\omega + 3, \omega + 4......$ it will eventually reach $\omega + \omega$ which is just $2\omega$
		1. This is technically not right it is actually $\omega * 2$ because multiplication is not commutative for ordinals but for simplicity and simplification for this course we will just call it $2\omega$ 
	2. Basically, it is $\omega$ follow by another $\omega$ or the set of natural number follow by another set of natural number with a different naming scheme. So, it looks like $0, 1, 2, 3, 4, ....., 0', 1', 2', 3', 4'.....$ or $0, 1, 2, 3, 4, 5, 6,......., \omega, \omega + 1, \omega + 2, \omega + 3, ......$ 
3. $2\omega, 2\omega + 1, 2\omega + 2, 2\omega + 3, ......|$
	1. The limit ordinal of this is $3\omega$, eventually we will reach $4\omega, 5\omega, 6\omega, ......|$
4. So, $3\omega, 4\omega, 5\omega, 6\omega, ......|$
	1. The limit ordinal of this is $\omega^2$ because eventually it will reach $\omega * \omega = \omega^2$, as you continue the trend.
5. $\omega^2, \omega^2 + 1, \omega^2 + 2, \omega^2 + 3,......|$ 
	1. The limit ordinal of this is $\omega^2 + \omega$ 
6. $\omega^2 + \omega, \omega^2 + \omega + 1, \omega^2 + \omega + 2, \omega^2 + \omega +3,......|$
	1. limit ordinal of this is $\omega^2 + 2\omega$
7. $\omega^2 + 2\omega, \omega^2 + 2\omega + 1 ...|$
	1. limit ordinal of this is $\omega^2 + 3\omega$, eventually we will reach $\omega^2 + 3\omega, \omega^2 + 4\omega, ....$
8.  $\omega^2 + 3\omega, ..., \omega^2 + 4\omega, ... |$
	1. Limit ordinal of this is $2\omega^2$ (the process for $2\omega^2$ is essentially the same as $\omega^2$ starting at step 5 to step 8) eventually we will reach $3\omega^2, ..., 4\omega^2, ....$ 
9. $2\omega^2, ..., 3\omega^2, ..., 4\omega^2, ... |$
	1. Limit ordinal of this is $\omega^3$, the process repeats and we will reach $\omega^4, ... \omega^5, ...$ 
10. $\omega^3,..., \omega^4, ..., \omega^5, ...|$ 
	1. The limit ordinal of this is $\omega^\omega$, the process repeats. 
		1. So, it will be $\omega^\omega, \omega^\omega + 1, \omega^\omega + 2, \omega^\omega + 3 ... |$ This will reach $\omega^\omega + \omega$ 
	2. After this you would need to understand your exponential rule but eventually we will reach $2\omega^\omega,..., 3\omega^\omega, ...$
11. $\omega^\omega, ..., 2\omega^\omega, ..., 3\omega^\omega, ...|$
	1. The limit ordinal of this is $\omega^{\omega + 1}$, eventually reaching $2\omega^{\omega + 1},..., 3\omega^{\omega + 1}.....$ 
12. $\omega^{\omega + 1}, ..., 2\omega^{\omega + 1}, ..., 3\omega^{\omega + 1}...|$
	1. Limit ordinal is $\omega^{\omega + 2}$, process repeats then eventually reaching $\omega^{\omega + 3}, ..., \omega^{\omega + 4}, ...$ which is represent by the limit ordinal $\omega^{2\omega}$
13. $\omega^{2\omega},..., \omega^{3\omega}, ...|$
	1. Limit ordinal is $\omega^{\omega^2}$, process repeats.
14. $\omega^{\omega^2}, ..., \omega^{\omega^3}...$
	1. Limit ordinal is $\omega^{\omega ^ \omega}$, eventually reaching $\omega^{\omega ^ {\omega^\omega}},...,\omega^{\omega ^ {\omega^{\omega ^\omega}}}, ...$
	2. So, how do we represent this limit? Well mathematicians cheated and just say it is $\epsilon_0$ (Epsilon 0) and the process repeats. 
	3. The limit ordinal of $\epsilon_{0}^{\epsilon_{0}^{\epsilon_0}},..., \epsilon_{0}^{\epsilon_{0} ^ {\epsilon_{0}^{\epsilon_0}}}, ...$ is $\epsilon_1$ and the process repeats.



>[!warning]
> <details>
> <summary>Warning! Contains Extra Information on ordinals. Read at your own risk</summary>
>
> If I have the set $\{1, 2, 3, 4,....\}$, this is the same thing as saying, in ordinal, $1 < 2< 3< 4< .....$ (based on their ordering). Suppose I take another set $\{10, 11, 12, 13,.....\}$ which is $10 < 11< 12< 13<.....$ 
>- The set $\{1, 2, 3, 4, ....\}$ has the same ordered structure as $\{10, 11, 12, 13, .....\}$, just with different element name therefore they are essentially the same thing if I just rename everything. They also have a one to one correspondence where $1 \to 10, 2 \to 11, 4 \to 12, 4 \to 13$. Taking the inverse will just reverse the arrow.
>
>Now suppose we have $\{2, 3, 4, ..., 1\}$, this the same as saying $2 < 3 < 4 <.....< 1$ but this does not have the same ordered structure as $\{10, 11, 12, 13,.....\}$ because there is an extra element in the set $\{2, 3, 4, ..., 1\}$ which is ordinal 1 (everything else got renamed so 2 is now "first" instead of 1) and we called that $\omega + 1$. We can still map them it just that the extra element 1 will not have a corresponding element mapped to it from the other set. Hence, we can denote each set as follow: 
>- $\{1, 2, 3, 4,....\} = \omega$
>- $\{10, 11, 12, 13,.....\} = \omega$
>- $\{2, 3, 4, ..., 1 \} = \omega + 1$
>	- However, this is bit confusing since we moved the number 1 to the front of the set after all the other numbers but the amount of numbers before 1 did not changed. So, this is the same as saying $\{1, 2, 3,..., 1'\}$ or $1 < 2 < 3<...< 1'$ if this makes more sense. We can also write it as $\{1, 2, 3,..., \omega \}$ instead or $1 < 2 < 3 < ... < \omega$ because remember ordinal is based on the ordering of the element position not their face value.
>
>
>
> Do note operation with $\omega$ is not commutative so $1 + \omega \neq \omega + 1$ 
> - Reason for this is 1 is a ordinal number that represent the order of type 1 so if this is the set  $\{1, 2, 3, 4,...\}$ then 1 actually just mean $\{1\}$ or $1$. Similarly, 2 just means $\{1, 2\}$ or $1 < 2$ and everything else after is just $\omega$ therefore $1 + \omega = \omega$ 
>	- Basically, you take the ordinal 1 or 2 which are finite ordinals (they have a finite amount of elements) then add $\omega$ (infinite ordinal) after it and rename the elements which is basically just $\omega$. 
> - While $\omega + 1$ means take the set of all finite ordinals and add an extra element after it that represent ordinal 1.
>	- So, if $\omega$ is the infinite ordinal that represent the set of all the finite ordinals denoted as $\{1, 2, 3, .....\}$ or $1 < 2 < 3 <.....$ and ordinal 1 just represent $\{1\}$ or $1$ then we take $\omega$ then add ordinal 1 after $\omega$ and rename the element of ordinal 1. $\{1, 2, 3,..., 1'\}$ or $1 < 2 < 3<...< 1'$ 
> - $2 * \omega = \omega$ since it is just a bunch of copies of ordinal 2 then replacing each element of $\omega$ with copies of ordinal 2 and renaming the elements. So it would be something like $\{0, 1, 0, 1, 0, 1, 0, 1, ....\}$ (although it looks like a set that contains duplicates it really doesn't since ordinal is based on the position of the element not their face value) and renaming the elements to $\{0, 0', 1, 1', 2, 2', 3, 3', ....\}$  which is really just $\omega$
>	- You can called this the "omega copies of ordinal 2" or "copies of ordinal 2 omega times". 
> - $\omega * 2$  is actually taking a copy of ordering type $\omega$ and duplicate it so we have two $\omega$ so something like $\{0, 1, 2, 3, ....., 0', 1', 2', 3', .....\}$
>
>
>For more information: [Ordinal Number](https://homepages.math.uic.edu/~kauffman/ConwayOrdinals.pdf)



# Cardinal

Consider the set $\{1, 2, 3\}$
- What is the size of this set? 
	- The size is 3

This is the idea of cardinal number, it used to denote the quantity or size of something that is countable. 

- It is really just counting things like "one, two, three, etc." as oppose to ordinal which is ordering things "first, second, third, etc.". 
	- For example, in algebra we say "$2x$" because there are two x's. 
		- We say "three" because there are 3 things 
- For finite cardinal number it is the same as if you would do normal math. 

**Bijection Function**
- Suppose we have the function, $f$, defined as $f : A \to B$, if the function is bijective. 
	- Then we can say the size of set $A$ and the size of set $B$ are the same therefore they have the same cardinality.
		- $|A| = |B|$
The idea is identical when counting items, suppose we don't use a function and lets say we have two boxes of candies and we want to determine which box has more candies. The original idea is to just count the candies in each box but suppose the counting system is not invented yet so how would we do this?
- We match each candy in one box to another candy of the other box like a function. So, each candy in one box has a one to one correspond with another candy of the other box.
	- Whichever box that has leftover candies that do not have a match has more candies. 
	- Or, if every candies has a match then they have the same amount of candies. 


## Infinite Cardinal

The size of a set or collection that has a infinite amount of things is denoted as $\aleph_0$, "Aleph-nought" or "Aleph null". 
- In some math book they might denoted as $\omega$ instead but this confusing since ordinal uses it as well.
- Commonly used to denote the cardinality of the natural number, $\Bbb N$. So, $|\Bbb N| = \aleph_0$ 
	- An infinite set is "countable" or enumerable if it has the same size as $\Bbb N$ it is uncountable if it larger than $\Bbb N$

### Arithmetic with "Aleph-nought"

Consider the infinite set denoted as $A$, and suppose $|A| = |\Bbb N|$, therefore $|A| = \aleph_0$. 


Suppose we add an extra element to $A$
- So, $A \cup \{0\}$
	- What is the cardinality now? 
		- It is still $\aleph_0$.
	- The size of the set did not change because there are still an infinite number of elements. Adding an extra element to the set does not change its size.
	- Therefore, $|A \cup \{0_2\}| = \aleph_0 = |A|$
	- You can think of this in the context of calculus where $\infty + 1 = \infty$ 
		- But, in calculus the concept of infinity isn't really defined. In infinite cardinal we defined the size of a infinite set as $\aleph_0$ which is considered a "number". In other word, we defined infinity as a "number" that can be counted. 
- Generalizing this, add any finite number, $n$, to $\aleph_0$ the result is still $\aleph_0$
	- $\aleph_0 + n = \aleph_0$

Suppose we multiply the size of $A$ by 2.
- Again, the same idea, doubling the size of a infinite set does not make it any bigger therefore $\aleph_0 * 2 = \aleph_0$
	- In calculus, $2 * \infty = \infty$ 
- Generalizing this, multiply any finite number, $n$, to $\aleph_0$ the result is still $\aleph_0$
	- $\aleph_0 * n = \aleph_0$

Suppose we join set $A$ with another infinite set $B$
- So, we have $A \cup B$,
	- The cardinality, $|A \cup B| = \aleph_0 + \aleph_0 = \aleph_0$
		- Thus, joining one infinite set to another infinite set does not make the size of the set any bigger
			- In calculus, $\infty + \infty = \infty$ 
- Generalizing this, adding any amount of $\aleph_0$ together, the result is still $\aleph_0$
	- $\aleph_0 + \aleph_0 + \aleph_0 + \aleph_0 + ....= \aleph_0$
	- Or, $\aleph_0 * n = \aleph_0$ for any finite number $n$.

Suppose we have an infinite amount of infinite set indexed by each natural number, so $\forall i \in \Bbb N$, $|B_i| = \aleph_0$, and we union them together.
- So, we get $B_0 \cup B_1 \cup B_2 \cup...$
	- The cardinality, $|B_0 \cup B_1 \cup B_2 \cup...| = \aleph_0$
		- Thus, joining infinite amount of infinite set does not make the size any bigger. It is still countable. 
			- A way to look at this is with a matrix, there is an infinite amount of rows and infinite amount of columns, indexed by natural numbers.
			- In calculus $\infty *\infty = \infty$
- Generalizing this, multiplying any amount of $\aleph_0$ together, the result is still $\aleph_0$
	- $\aleph_0 *  \aleph_0 * \aleph_0 * \aleph_0 * ....= \aleph_0$


The ideas above can be explained using the "Infinite Hotel Paradox".<br>
Suppose I have a hotel with infinite number of rooms, numbered starting at 0 then 1, 2, 3, 4, ...., and the hotel is "full", there is an infinite number of guests.
- Suppose a new guest came up and ask for a room. How do we fit the guest into the hotel? 
	- I can't add him to the end of the hotel since there are no "end", the hotel is infinite.
	- So, I add him to the first room. I tell all the current guests in the hotel to move one room over to their right, so the current guest in room 0 will move to room 1, the current guest in room 1 move to room 2, and so on. There is an infinite number of rooms so all the current guests will still fit in the hotel. Now I have an empty room in room 0, so I can fit that extra guest to room 0. 
		- If the new guest wants room 100, I can just tell all the guests from room 100 and up to move one over to their right instead.
- Suppose I have 12 new guests.
	- I tell all the current guests in my hotel to take their number and add 12 to it and that will be their new room. Now, I have freed up the first 12 rooms for the 12 new guests. 
- Suppose a bus came and the bus is also infinite it has an infinite number of guests and each guest is seated numbered 0, 1, 2, 3,.....
	- So, how can I fit them? I can't just tell the current guests in my hotel to move to the right infinite amount of times, they will just keep moving down and none of the current guests will have room.
	- But there is an infinite amount of even and odd numbers. So, I tell the current guests in my hotel to multiply their current room number by 2 and that will be their new room. 
		- All the current guests will now be stationed in even numbered rooms 
	- So, now all the odd numbered rooms are opened up and I can now fit the infinite number of guests on the infinite bus to odd numbered room, they will take their seat number multiply it by 2 and add 1. So, the guest seated in seat number 0 will move to room 1. 
- Suppose my hotel is now empty and an infinite number of buses came and each bus is also infinite with infinite number of guests. Each bus is numbered 0, 1, 2, 3,.... Each guest on each bus is also seated 0, 1, 2, 3, ...... 
	- This can be represent using a matrix (think 2d array in Computer Science). Let the row represents the bus number and the column represent the seat number. So, the guest in row 0 column 0 will be in bus 0 seated in seat number 0, the guest in row 1 column 0 will be in bus 1 seated in seat number 0. 
	- Now, move along the diagonal of the matrix and assign a room to each guest. So, the guest in row 0 column 0 (bus 0 seat number 0) will move to room 0, the guest in row 0 column 1 (bus 0 seat number 1) will move to room 1, the guest in row 1 column 0 (bus 1 seat number 0) will move to room 2, etc...
		- Basically a path that goes from row 0 column 0 to row 0 column 1 to row 1 column 0 to row 2 column 0 to row 1 column 1 to row 0  column 2 to etc...
		- Drawing the matrix and the path looks something like this. If each of those star represents a guest. 
![[Hotel.png]]
	- But what if my hotel is full? How would I do fit all the guest into my hotel? 
		- This would have something to do with infinite prime numbers which is hard to explain so I just linked a video explaining this one. [Infinite Hotel Paradox](https://www.youtube.com/watch?v=Uj3_KqkI9Zo)

> Do notes: this only works with natural numbers or any sets of numbers that has the same cardinality of the set of natural numbers. 
> - The cardinality of the set of real numbers has a different cardinality to the set of natural numbers, real numbers has an higher order of infinity than naturals which is denoted as $2^{\aleph_0}$
### Cardinality with Different Known Sets


What is the cardinality of $\Bbb Z$? 
- Believe it or not it is $\aleph_0$ which is the same cardinality of $\Bbb N$ 
	- Therefore, $|\Bbb Z| = |\Bbb N|$ even though $\Bbb N \subset \Bbb Z$ (Natural numbers is a proper subset of Integers). 
	- All integers can be mapped to to exactly one natural numbers (one to one correspondence). Even though the size of the set of integers should theoretically be bigger, no? 
		- Well, infinite cardinal is very different than finite cardinal where if a infinite set is "countable" then it has the same cardinality as the natural numbers which is $\aleph_0$
	- We know that there is an infinite amount even and odd numbers. So, all the even natural numbers can be mapped to all the non-negative integers number (saying "non-negative" here because we are including 0). So, $0 \to 0, 2 \to 1, 4 \to 2, etc...$ then we map all the odd natural numbers to all the negative integers, so $1 \to -1, 3 \to -2, 5 \to -3, etc ...$ 
		- We can create a bijection function here by breaking the function into two parts like a piecewise function: One for non-negative integers and one for negative integers. 
	- Now, we can see they have the same cardinality.


Does $\Bbb R$ has the same cardinality as $\Bbb N$?
- No, I already answered this. But why?
	- $\Bbb R$ is not countable 
		- Take the interval $(0, 1)$ isn't there an infinite amount of numbers between 0 and 1, now if we mapped all the natural numbers to all the real number between 0 and 1, which is not possible you can always find a number between 0 and 1 that does not have a corresponding natural number mapped to it. See [[#Cantor's Diagonalization Proof for Reals]]. 


>[!note]
>
>Any intervals of the real number has the same size as the real number. 
>- $|\Bbb R| = |(0, 2)| = |[0, 1000)| = |(-10, 10)| = 2^{\aleph_0}$
>	- Example, the tangent function has a domain of $(-\frac \pi 2, \frac \pi 2)$ and is mapped to all the real number, $\Bbb R$, so the function defined for tangent is $f : (-\frac \pi 2, \frac \pi 2) \to \Bbb R$. This is a one to one correspondence, co-tangent is just $f : \Bbb R \to (-\frac \pi 2, \frac \pi 2)$ therefore $(-\frac \pi 2, \frac \pi 2)$ and $\Bbb R$ are the same size.

What about rational numbers $\Bbb Q$? 
- There is an infinite number of rational numbers between 0 and 1 but this has the same cardinality as $\Bbb N$. How? It is the matrix thingy again.
	- Rational numbers is really an integer over an integer where the denominator cannot be zero. Let use a matrix where the row represent the numerator and the column represent the denominator (You can do it the other way as well). So, row 1 column 4 will be $\frac 14$.
		- We will ignore column 0 since the denominator is 0 in that column, we will also ignore all equivalent rational number that has already been listed, so for example, $\frac 12 = \frac 24$ where $\frac 12$ is listed before $\frac 24$ so we ignore $\frac 24$.
		- Using the same idea with the hotel take the diagonal path, and we will map all the even natural numbers to all non-negative rational number and the all the odd natural numbers to all the negative rational number. This creates a one-to-one correspondence.
	- This has the same cardinality as $\Bbb N$ because it is really just an integer number over an integer number where the denominator cannot be 0 and multiple rational numbers have the same value so we can exclude those duplicated value (if we don't exclude those we cannot make an one-to-one correspondence). By these two features of the rational number this allows us to create an one-to-one correspondence between $\Bbb N$ and $\Bbb Q$.
		- Which makes $\Bbb Q$ a "countable" infinite set. 
		- The matrix looks something like this but this shows the mapping for positive rational numbers only (the same idea for the hotel is used here). The boxes that are in red either have a denominator of 0 or have a equivalent rational number that has already been listed, so we ignore those numbers. 
![[Rational Cardinality.png]]

> Note: one-to-one correspondence means bijective not just injective (which means one-to-one without the word "correspondence").


## Cantor's Diagonalization Proof for Reals

This proof applies to any interval of all reals but for simplicity we will consider the interval from $(0, 1)$<br>
Lets denote the interval as $A$ so set $A$ will contain all the real numbers from $(0, 1)$ which is an infinite set. If a set is countable then it must have the same cardinality as $\Bbb N$. So, we will attempt to map a one to one correspondence of the natural numbers to all the real numbers contains in $A$.<br>
Claim: $A$ is not countable
- Proof: 
	- Suppose BWOC $A$ is countable, map each natural number to a unique random number in $A$ 
		- $0 \to 0.11234$
		- $1 \to 0.23550$
		- $2 \to 0.48390$
		- $3 \to 0.2839249$
		- $4 \to 0.34349344$
		- $5 \to 0.3475$ 
		- $...$
	- Now, suppose the digit in the tenth place corresponds to the $0^{th}$ position (we will call it the $0^{th}$ digit), the hundredth place corresponds to the $1^{st}$ position (again, the $1^{st}$digit), etc.. We starts at 0 since the natural number I chose starts at 0, also because this is a math course tailored towards computer science. 
	- Next, define a variable, suppose $k$, which will be a real number that is part of the set $A$. It will be constructed by choosing a number that is different from the $0^{th}$ digit of the number that 0 maps to (which will represent the tenth place for $k$), a number that is different from the $1^{st}$ digit of the number that 1 maps to (which will represent the hundredth place for $k$), etc.. So, basically for every natural number $n$, choose a number that is different from the $n^{th}$ digit of the number that $n$ maps to construct the number that $k$ will represent that is part of the set $A$ (it is hard to explain in words so I will underline all the digits below).
		- $0 \to 0.\underline11234$
		- $1 \to 0.2\underline3550$
		- $2 \to 0.48\underline390$
		- $3 \to 0.283\underline9249$
		- $4 \to 0.3434\underline9344$
		- $5 \to 0.34750\underline000$ 
		- $...$
	- The digit underlined of the real number that each natural number maps to is the number that we will change when constructing $k$. It is a diagonal line that goes downward. 
	- The $0^{th}$ digit of 0.11234 is 1, the $1^{st}$ digit of 0.23550 is 3, the $2^{nd}$ digit of 0.48390 is also 3, etc.. Therefore, when constructing $k$ for each $n^{th}$ digit choose a different number, so for the tenth place choose a different number from 1, hundredth place choose a different number from 3, thousandth place choose a different number from 3, etc.. 
		- Some numbers that $k$ can represent are: 
			- $0.245038...$
			- $0.598467...$ 
			- $0.421839...$
		- Any of the number above can be $k$
		- Suppose $k = 0.245038...$ , this number is part of the set $A$ but there is no natural number that is mapped to this number. Each natural number is mapped to a real number that is different from $k$ because their $n^{th}$ digit is different. 
			- So, for example, the real number contained in $A$ that the natural number $6$ maps to has a different digit in its $6^{th}$ position than the $6^{th}$ digit of the real number that $k$ represent; $5$ is mapped to $0.347500$ but the digit in its $5^{th}$ position is 0 which is different from the $5^{th}$ digit of the real number that $k$ represent which is 8. This applies to all the natural number where each one is mapped to a real number in $A$. 

## Continuum Hypothesis

We know that $\aleph_0 < 2^{\aleph_0}$, so the question is: Is there a $x$ in between?
- This is the continuum hypothesis which states "there is no such $x$".

The continuum hypothesis is actually both true and false, it is a hypothesis that is independent of all established mathematics. 
- Therefore, it depends on how one defines math. 
	- It is completely fine to say the hypothesis is false "where there does exist some $x$ or multiple $x's$ such that $\aleph_0 < x < 2^{\aleph_0}$". 
	- Or the hypothesis is true "there does not exist an $x$ such that $\aleph_0 < x < 2^{\aleph_0}$".
- It is up to one's interpretation of the hypothesis

### Aleph-numbers

The cardinality of $\Bbb N$ is defined as $\aleph_0$ as we know this is the "smallest" infinite cardinal. We then defined the next biggest infinite cardinal as $\aleph_1$, and so forth. 
- Aleph-numbers are indexed by the ordinal.
	- $\aleph_0, \aleph_1, \aleph_2, \aleph_3, ......\aleph_{\omega}$

Like continuum hypothesis, there not much mathematician can prove about aleph-number. Most things about aleph-number is considered "independent" of all established mathematics.<br>

Lets use the continuum hypothesis with aleph-number
- If you say the continuum hypothesis is true; there is no $x$ in between. Then, $2^{\aleph_0}$ would be the next biggest infinite cardinal after $\aleph_0$ so $2^{\aleph_0} = \aleph_1$
	- $\aleph_0 < 2^{\aleph_0}$
	- $\aleph_0 < \aleph_1$
- Otherwise, if you say the continuum hypothesis is false; there does exist an $x$ or multiple $x's$ in between. Then, each $x$ will be denoted as an aleph-number. So, let's say there are 3 $x's$ in between.
	- $\aleph_0 < x_0 < x_1 < x_2 < 2^{\aleph_0}$
	- Denoting each $x$ as aleph-number as well as $2^{\aleph_0}$
		- $x_0 = \aleph_1, x_1 = \aleph_2, x_2 = \aleph_3$, and $2^{\aleph_0} = \aleph_4$
	- $\aleph_0 < \aleph_1 < \aleph_2 < \aleph_3 < \aleph_4$



> Another paradox that may be "fun" to research is Berry Paradox