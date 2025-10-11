# Examples with Combinatorics and Probability

# Set Examples
1. How many ways are there to rearrange the letters in alabama? (common question)
	1. ${7 \choose 4}(3)(2)(1) = (7)(6)(5){4 \choose 4} = (7)(6)(5)$
		1. There are 7 letters in Alabama, There are 5 distinct letters {a, l, b, m}
		2. There are 4 a's so choose 4 spot for the a's so that is (7 choose 4)
		3. There are 3 spots left and each of the other letters only appears once so we can just do 3! for l, b, and m
		4. Alternatively, we can do l, b, m first where we chose one spot for each l, b, and m. ${7 \choose 1}{6 \choose 1}{5 \choose 1} = (7)(6)(5)$, then you have 4 spots left for the 4 a's so ${4 \choose 4} = 1$
	2. Order doesn't matter here since all a's are not unique to each other; we can swap the position of the a's with each other and it still going to be the same ordering. However, we can still use permutation to solve this. 
		1. Suppose all the letters are distinct (lets say we assigned a unique color to each of the 4 a's since that is the only letter that repeats), then the amount of permutation is $7!$ but the a's are still the same a's (they are still indistinguishable with each other) so we divide by the amount of permutations of a's. All the letters that appears once are just $1!$, a's appears 4 times so the permutation for letter a is $4!$ since there $4!$ to order the a's if they are all distinct. 
		2. $\dfrac {7!}{4!} = (7)(6)(5)$
2. How about mississippi?
	1. $11{10 \choose 4}{6 \choose 4}{2 \choose 2}$
		1. The letters are {m, i, s, p} and there 11 letters in total. 
		2. There is 1 m, 4 i's, 4 s's, and 2 p's. Choose 1 spot for the m, 4 spots for the i, 4 spots for the s, and 2 spots for the p.
	2. Using permutations
		1. $\dfrac {11!}{4! * 4! * 2!}$
		2. Letter i repeats 4 times, s repeats 4 times, and p repeats 2 times. 

Suppose you have 5 red crayons, 7 blue crayons, 10 yellow crayons. How many ways are there to arrange them in a row? 
- ${22 \choose 5}{17 \choose 7}{10 \choose 10}$
	- There is 22 crayons in total, choose 5 positions for the red ones, 7 positions for the  blue ones and 10 positions for the yellow ones. 


# Multiset Example
Your bag of M&Ms contains:
- 10 red
- 5 yellow
- 7 green
- 6 brown
- 4 orange
How many ways are there to reach in and grab 4 M&Ms?
- ${5 + 4 -1 \choose 4} = {8 \choose 4}$
	- There are four M&Ms to choose from and we are grabbing 4 M&Ms.
1. What is the probability that you get four brown?

>[!note]
> 
>Probability does not work well with multiset where all the items are not equally likely to be chosen. Recall that a probability can only be done on a sample size where all the events are equally likely. In this case it is more likely to choose grab 4 brown M&Ms than orange since there is only one way to choose 4 orange M&Ms but like 15 ways to choose 4 brown M&Ms since ${6 \choose 4} = 15$. Therefore, we convert it into a set instead where we assume each M&Ms is unique (lets say we assign a number to each one), this would create a sample space of equally likely event. 
	
-  Event size of choose 4 brown M&Ms is ${6 \choose 4}$
- Size of the sample space is ${32 \choose 4}$ since we convert it to a set instead. 
- The probability of choose 4 brown is $\dfrac {6 \choose 4} {32 \choose 4}$
1. What is the probability that you get two red, a yellow, and a green?
	- $\dfrac {{10 \choose 2}{5 \choose 1}{7 \choose 1}}{32 \choose 4}$


# Poker Example
Really good practice. 

Denote ace as A, jack as J, queen as Q, king as K, clubs as C, diamond as D, spade as S, and heart as H. 

1. How many 5 cards hand are possible? (sample size)

Find the event size of the following (The probability for each one can be found by dividing the event size by the sample size): 

2. Straight flush
3. Four of a kind 
4. Full House
5. Flush (not Straight Flush)
6. Straight (not Straight Flush)
7. Three of a kind
8. Two Pairs
9. Pair

> [!important]
> <details>
> <summary>Solution</summary>
>
>1. Order doesn't matter because if you draw 5 cards it does not matter how you order them it still going to be the same hand therefore ${52 \choose 5}$
>2. $40 = (4)(10) = {4 \choose 1}{10 \choose 1}$
>		1. There are 10 cards you can start from $\{A, 2, 3, 4, 5, 6, 7, 8, 9, 10\}$, so we choose one card
>		2. 4 suits to choose from $\{C, D, S, H\}$, so we choose 1 suit
>		3. Every cards after the starting point has to be the same suit since it is a flush so there is only one choice for the other cards.
>3. $(13)(48) = {13 \choose 1}{4 \choose 4}{12 \choose 1}{4 \choose 1}$
>		1. Choose 1 out of the 13 ranks to be the cards that will be repeated 4 times. There are 48 cards left since we chose a rank to be repeated 4 times, choose another card out of the 48 to be last card. 
>		2. Alternatively, after choosing the rank to be repeated 4 times (which is choose 4 suits out of the 4 for that rank), there is 12 ranks left to choose from, choose 1 rank from the 12 ranks and choose a suit out of the 4 suits for that rank. 
>4. ${13 \choose 1}{4 \choose 3}{12 \choose 1}{4 \choose 2}$
>		1. There are 13 ranks to choose from choose 1 to be repeated 3 times, choose another rank (which there are now 12 left) to be repeated 2 times. For each rank choose 3 suits out of the 4 and 2 suits out of the 4 respectively. 
>5. ${13 \choose 5}{4 \choose 1} - 40$
>		1. All the suits must be the same so choose 1 suit out of the 4. It doesn't matter which of the 5 ranks we choose, we just have to choose 5 ranks so choose 5 out of the 13 ranks and minus 40 which are the straight flush since we just want flush that are not straight. 
>6. $(10)(4)^5 - 40= {10 \choose 1}{4 \choose 1}{4 \choose 1}{4 \choose 1}{4 \choose 1}{4 \choose 1} - 40$
>		1. There are 10 cards to start from 
>		2. Each of the five cards can be any suits since we do not care if it is a flush so choose 1 suit for each of the cards
>		3. We only wants straight that are not flush so minus 40 which are straight flush.
>7. ${13 \choose 1}{4 \choose 3}{12 \choose 2}(4^2)={13 \choose 1}{4 \choose 3}{12 \choose 2}{4 \choose 1}{4 \choose 1}$
>		1. Choose 1 out of the 13 ranks to be repeated 3 times, choose 2 more other ranks (doesn't matter which) and choose 1 suit for each of the 2. 
>		2. The reason we do ${12 \choose 2}$ instead of ${12 \choose 1}{11 \choose 1}$ is because we do not want to double count if you do it the other way divide by $2!$.
>8. ${13 \choose 2}{4 \choose 2}{4 \choose 2}(44) = {13 \choose 2}{4 \choose 2}{4 \choose 2}{11 \choose 1}{4 \choose 1}$
>		1. Choose 2 ranks out of the 13 to duplicate. Choose 2 suits for the first card and choose 2 suits for the second card to get two pairs. 
>		2. There are 44 other cards to choose from we cannot choose the cards we have duplicated or else we will get a full house so we exclude them from the remaining cards. Or choose 1 rank from the remaining 11 ranks and 1 suit for that rank.
>9. ${13 \choose 1}{4 \choose 2}{12 \choose 3}(4)^3 = {13 \choose 1}{4 \choose 2}{12 \choose 3}{4 \choose 1}{4 \choose 1}{4 \choose 1}$
>		1. Choose 1 rank out of the 13 to duplicate. Choose 2 suits for that rank. 
>		2. Choose 3 more ranks out of the 12 leftovers then choose 1 suit for each of the 3 ranks. 
>		3. The reason why we don't multiply by 48 which is remaining cards after we choose the card to duplicate is because we might end up with two pairs or a full house.
>
>
> Note: If $r = 1 \text { or } r = n - 1$ in any of the choose notation then that can be simplified to just $n$. So, ${n \choose 1} = {n \choose n - 1} = n$.
> </details>
