
# Combinatorics and Probability

- Combinatorics is the idea of "counting" in a finite or discrete structure.
- Probability is the idea of how likely a certain event is going to happen. 


# Probability Definition

- The sample space, denoted as $S$, is a set that contains all possible outcomes. 
- The event, denoted as $E$, is any subset of the sample space. 

## Probability Formula

In order to calculate the probability of an event happening, every elements in the sample space must be equally likely. If so, the probability of an event is the size of the event divided by the size of the sample space.

$$ P(E) = \dfrac {|E|}{|S|}$$

>[!tip]
>1. Suppose we flip 2 coins consecutively, then the possible outcomes in the space space are: $S = \{HH, HT, TH, TT\}$, where H is head and T is tail
>	2. The event of one head and one tail is $\{HT, TH\}$, the probability of that happening is the size of the event divide by the size of the sample space which is $\dfrac {2}{4} = 0.5$ or 50%. 



# Multiplication Rule for Counting (Steps in a Process)

Rather than trying to draw out the sample space every time (which doesn't work very well when you have a large sample) instead we use the multiplication rule for counting. People do this all the time intuitively. <br>
For example, suppose you have 5 different color shirts (blue, red, white, black, and green) and 4 different pairs of pants (shorts, slacks, jeans, and khakis). How many different outfit combination can you make with one shirt and one pair of pants? 
- It is $4 * 3 = 12$, by intuition you would do this without thinking too hard
	- Basically, the steps are: choose a shirt you have 4 choices and choose a pair of pants you have 3 choices and you multiply them together and you get 12. 
		- You can also draw a 3 by 4 matrix and write out the pairs. 

>[!Important] 
> 
> Multiplication Rule Formula 
>
>Given a task with $k$ number of steps and each step has a number of choices we can choose from, lets called it $n$, then the amount of ways to perform the task is:
>- $n_1 * n_2 * n_3 * .... * n_k$ where $n_i$ is the number of choices to choose at step $i$. 


>[!Tip] 
>1. How many 3-digit PINS are possible?
>	1. Intuitively, we say 1000 PINS because 0-999, where 000 counts as one combination of a 3 digit PIN.
>	2. But suppose we use the multiplication rule instead. There are 3 digits in total, we have ten choices for the first digit 0-9, ten choices for the second digit 0-9, and ten choices for the third digit 0-9. So, the amount of 3-digit PINS possible is: $10 * 10 * 10 = 1000$
>2. Lets assume we assigned a PIN by random. 
>	1. How many 3-digit PINS are there where all the digits are even? 
>		1. Answer: 125. There are 5 even numbers from 0-9 which are 0, 2, 4, 6, 8.
>			1. The first digit we can choose any of the 5 even number. Same thing goes for the second and third digit. Therefore, the amount of 3-digit PINS where all digits are even is $5*5*5 = 125$
>	2. What is the probability of getting a PINS where all the digits are even? 
>		1. Answer $\dfrac {125}{1000}$, the sample size is 1000 3-digit PINS, the amount of PINS with all even digits is 125. 
>	3. What is the probability of getting a 3- digit PINS where all the digits are unique? 
>		1. The amount of 3-digit PINS where all digits are unique is $10 * 9 * 8$ 
>			1. The first digit we can choose from any number 0-9, the second digit we only have 9 choices left because the second digit cannot be the same number as the first digit and the third digit cannot be the same number as the first or second digit so there are 8 choices for the third digit.
>		2. Answer: $\dfrac {10 * 9 * 8}{1000}$
>	4. What is the probability of getting a 3- digit PINS where the same digit cannot appear two times in a row? 
>		1. The event size is $10 * 9 * 9$
>			1. There are 10 choices for the first digit, 9 choices for the second digit because it cannot be the same digit as the first digit, and 9 choices for the third digit because it cannot be the same as the second digit but it can be the same digit as the first digit. 
>		2. Answer: $\dfrac {10 * 9 * 9}{1000}$


# Independent Event

Two or more events are independent from each other if knowing one event does not affect the probability of the other events. 

Examples: 
- Consecutive coin flips are independent from each other. Flipping a head on the first flip does not influence the probability of flipping a tail or head on the next flip. (All you physicists out there shut up).
- Rolling a die

Examples non-independent events: 
- Drawing a card without replacement. 
	- If I draw an Ace the probability of my friend drawing an Ace is affected
		- The probability of drawing an Ace is $\dfrac {4}{52}$
		- If I were to draw an Ace the probability of my friend drawing another ace is $\dfrac {3}{52}$


# Mutually Exclusive Event 

Two or more events are mutually exclusive if they can't happen at the same time. Meaning if one event happens the others cannot happen at the same time as the one that happened. This is very different from independent event so do not get them mixed up. Basically, suppose you have two events that are mutually exclusive, if one event occurs, then the other cannot occurs therefore the effect of one event occurring directly influence the other event not occurring. 
- Example: 
	- A coin cannot flip head and tail at the same time. If a coin flipped head then the event of flipping tail did not occur and cannot occur because the coin already flipped head. (Note: this is different from consecutive coin flips where we are looking at the probability of flipping head or tail each flip and each flip cannot influence the other flips).
