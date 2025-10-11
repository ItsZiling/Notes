
This is not a super important unit for discrete structures as it deals with hardware, however it is good to know. 

## Basic Logic Gates
The three most basic logic gates are: 
- the **or** gate
- the **and** gate
- the **not** gate

![Gates.jpg](../assests/Gates.jpg)

> If we combine a couple of these together with some inputs and outputs we get a circuit board. 

Consider this simple circuit (Stolen from my professor's slide)
- It has three input bits and two output bits
![Simple Circuit.png](../assests/Simple%20Circuit.png)

What is the output given the input 011(Top to bottom)?

<details>
    <summary>Solution</summary>
    Output: 11
</details>



## Propositional Logic into Circuit
You can turn a propositional logic statement into a circuit.
- Each variable represents one input bit and there is one output bit for the entire statement.
Consider the statement $p \wedge \neg (q \vee r) \equiv p \wedge (\neg q \wedge \neg r)$

It will look something like this

![Example_1.png](../assests/Example_1.png)

> Alternatively, you can combine the $q$ and the $r$ to an "or" gate and then negate the output of the "or" gate with a "not" gate.  FYI I drew the picture above.
> (Insert a slow clap from the editor here) 

## Truth tables into Circuits 
You can also turn any truth table into circuit

Consider the truth table below with some random outputs I have chosen: 

| row # | $p$ | $q$ | $r$ | $output$ |
| :---: | :-: | :-: | :-: | :------: |
|   1   |  1  |  1  |  1  |    0     |
|   2   |  1  |  1  |  0  |    0     |
|   3   |  1  |  0  |  1  |    0     |
|   4   |  1  |  0  |  0  |    1     |
|   5   |  0  |  1  |  1  |    0     |
|   6   |  0  |  1  |  0  |    1     |
|   7   |  0  |  0  |  1  |    1     |
|   8   |  0  |  0  |  0  |    0     |
> What propositional statement corresponds to the output column?



<details>

<summary> Solution </summary>

> [!TIP]- Solution
> $(p \wedge \neg q \wedge \neg r) \vee (\neg p \wedge q \wedge \neg r) \vee (\neg p \wedge \neg q \wedge r)$
> - The only rows you have to consider are the ones with a 1 on the output column; there are three rows on the output column with 1: row 4, 6 and 7. Then take all the variables with their corresponding truth value in that row and combine them with "and" connectivity and separate each row with "or" connectivity.
>
>>You can probably simplify the above statement with some logic rules but my lazy ass is not doing that. 

</details>



## Math with Circuit 
You can build a circuit that does math (wow!)

### Brute Force: Addition
If we are adding two 2-bit numbers together we can use a truth table to show the output
- This method simply adds 2 binary numbers of the same size via table
	- There would be 4 input bits since there are two 2-bit numbers
	- When adding two 2-bit data you would have 3 output bits
- If it was two 32-bit numbers there would be 64 input bits
	- At this point, the brute force method is so unwieldy that you would need 64 input bits and 33 output bits. That's 97 columns in the corresponding truth table.

## A Better Way to Add Binary
Instead of using a truth table we can add "normally", as they teach you in elementary school. The method uses the same idea as base 10 numbers but we instead work with base 2:
- In base 10 : $9 + 1 = 10$, where you would carry the one over to the next "column"
	- But in base 2 or binary we carry the one over when the sum is 2. So $1 + 1 = 10$ in base 2 since 2 is 10 in binary.
	- So, what if we add three 1's together in binary? 
		- $1+1+1 = 11$, 3 is 11 in binary
			- Breakdown: 
				- $1+1=10$, carry the one over
				- $10 + 1 = 11$, add straight down
### Example using a table

| Carry |  1  |     |     |     |     |
| :---: | :-: | :-: | :-: | :-: | :-: |
|       |     |  1  |  0  |  0  |  0  |
|  $+$  |     |  1  |  0  |  1  |  1  |

| ***Output*** |  1  |  0  |  0  |  1  |  1  |
| :----------: | :-: | :-: | :-: | :-: | :-: |
>Answer : 10011

| Carry |  1  |  1  |     |     |     |
| :---: | :-: | :-: | :-: | :-: | :-: |
|       |     |  1  |  1  |  0  |  0  |
|  $+$  |     |  1  |  1  |  1  |  1  |

| ***Output*** |  1  |  1  |  0  |  1  |  1  |
| :----------: | :-: | :-: | :-: | :-: | :-: |
>Answer : 11011

## Half-Adder, Full-Adder and Parallel-Adder

A half-adder is a circuit used to add two bits together. But here it is: (Note: All pictures are taken from my professor slide) 
![[Half-Adder.png]]

A full-adder uses two half-adders to add three bits together. 

![[full-adder.png]]

A parallel-adder is when you are doing operands with $k$-bits, where $k$ is the number of bits. It uses a combination of half-adder and full-adder. 

- When adding 2 $k$-bit number together, the number of inputs is always $2k$ and the number of outputs is always $k+1$. 
	- For example, consider a 3 bit operands. The number of inputs is 6 and the number of outputs is 4. Here is a picture from my professor slide.
![[parallel-adder.png]]
>[!tip]
>- The amount of half-adder for any $k$-bit operands is always 1
>- The amount of fuller-adder for any $k$-bit operands is always $k-1$
>- The amount of outputs for any $k$-bit operands is always $k+1$
>

## Converting Binary to Base 10 and Vice Versa
If you're taking this class, you should really know how to do this already, but our esteemed writer has taken mercy on you and will recap the process. You shouldn't  need to know any other base other than 2 or 10 (at least for now).
- Binary to Base 10 is simple:
	- Take a binary number multiply each bit with it corresponding place value which is $2^{n}$, where $n$ is the place value. Then add them up. Note: the first place value is 0. 
		- For other base you do the same thing but instead of a 2 it would be whatever base you are using. 

Example with table

| Convert the following to base 10 |     1      |     1     |     0     |     1     |     1     |
| :------------------------------: | :--------: | :-------: | :-------: | :-------: | :-------: |
|           Place Value            |   $2^4$    |   $2^3$   |   $2^2$   |   $2^1$   |   $2^0$   |
|             Multiply             | $1*2^4=16$ | $1*2^3=8$ | $0*2^2=0$ | $1*2^1=2$ | $1*2^0=1$ |
> Then add the result up: $16+8+2+1 =27$

> [!tip]
> You can safely ignore all the digits with 0 since 0 times anything is equal to 0. You  just need to worry about the digits with 1 in them. As a matter of fact you don't need to do any multiplication with 1 since 1 times any number $n$ is $n$ itself. 
> - So using the above example, ignoring all the 0 and just looking at the place value with 1 in them. I can just write $11011_2 = 2_{10}^4 + 2_{10}^3 + 2_{10}^1 + 2_{10}^0 = 27_{10}$
>
>> The little 2 notation just means that number is in base 2 and same thing for the little 10.

- Base 10 to Binary, there is two methods to this: Division and Subtraction
	- The Division Method: When using this method, you will be writing the 0's and 1's in reverse order (This will make more sense once the example comes around)
		- Steps:
			1. Look at the original number (base 10) and determine if it is even or odd? If odd write a 1, if even put a 0.
			2. Divide by 2 and throw the remainder out (integer division), look at the result and determine if it is even or odd? If it is odd put a 1 BEFORE the previous number, if it is even put a 0 BEFORE the previous number.
			3. Repeat step 2 until your base 10 number reaches 0 or 1.
		- Example: Consider the base 10 number 106
			- 106 is even so we put 0: 0
			- $106/2 = 53$. 53 is odd, put a 1 BEFORE 0 so: 10
			- $53/2= 26$, We throw out the remainder here, 26 is even so put a 0 BEFORE 10 so: 010
			- $26/2=13$ 13 is odd, put a 1 so: 1010
			- $13/2 = 6$, 6 is even, put a 0 so: 01010
			- $6/2=3$ 3 is odd, put a 1 so: 101010
			- $3/2 = 1$1 is odd, put a 1 so: 1101010
			- **STOP! We reached 1**, so the Answer is 1101010
	- The Subtraction way: In division we find the digits in reverse order. In subtraction we find the digits in order.
		- Steps: 
			1. Look at the original number (base 10), and find the highest power (exponent) of base 2. In other words, find the value of $2^n$ where $n$ is the greatest integer, without $2^n$'s value becoming greater than the original number (in base 10).
			2. Write a 1, then subtract the highest power of base 2 from the original number. Afterwards subtract 1 from the exponent so $2^{n}$is now $2^{n-1}$ . Is the value of $2^{n-1}$ greater than the resulting difference of the base 10 number? If so, put a 0 and subtract 1 from the exponent, if not, put a 1 and subtract $2^{n-1}$ from the resulting difference.
			3. Repeat step 2 until you reach 0. If the exponent $n$ has not reached 0 then write an additional 0 in the base 2 number for each remaining exponent.
		- Example: Consider the base 10 number 106 again
			- The highest power $n$ of base 2 without being greater than 106 is 6 since $2^7= 128$ which is greater than 106 and $2^6=64$. Let use a table for this: 

| Base 2 powers |       $2^6 = 64$        |       $2^5 = 32$       |            $2^4 = 16$            |       $2^3 = 8$       |     $2^2 = 4$     |                     $2^1 = 2$                     |       $2^0 = 1$        |
| :-----------: | :---------------------: | :--------------------: | :------------------------------: | :-------------------: | :---------------: | :-----------------------------------------------: | :--------------------: |
|   Subtract?   | Yes, since $64 \le 106$ | Yes, since $32 \le 42$ |       No, since $16 > 10$        | Yes, since $8 \le 10$ | No, since $4 > 2$ |               Yes, since $2 \le 2$                | No, since we reached 0 |
|  Subtraction  |     $106 - 64 = 42$     |      $42-32 = 10$      | Ignore the subtraction, still 10 |      $10 - 8 =2$      |  Ignore, still 2  | $2-2=0$<br>STOP, any remaining exponents put a 0. |                        |
| Binary Answer |            1            |           1            |                0                 |           1           |         0         |                         1                         |           0            |

> Observe that we still got the same answer 1101010 as in the division example for 106. Personally, I prefer the subtraction since I think it is faster and I don't have to write in a reverse order. 


>[!tip]
>
>If a base 10 number is exactly 2 to the $n$ power then the binary form is 1 plus $n$ amount of 0(s). 
>- So if the base 10 number is 64. 64 is exactly $2^6$ $\therefore$ the binary form is 1 with six 0s after so 1000000. 
>
>If a base 10 number is +1 away from 2 to the $n+1$ power, in other word if $2^{n+1}$ is greater than the base 10 number by exactly 1, then the binary form is $n$ amount of 1(s).
>- So if the base 10 number is 255. The highest $n$ power of base 2 without being greater than 255 is 7, however, 255 is exactly +1 away from $2^{7+1} = 2^8 = 256$, $\therefore$ the binary form of 255 is exactly seven 1s so 1111111. 
