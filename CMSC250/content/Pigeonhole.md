# Pigeonhole Principle


# Basic Definition

If you have a pigeon house with three holes and there are four pigeons, then one of those pigeon will not have a hole. 
- How does this apply to function? 
	- A function whose domain set (finite) is larger than the codomain set (finite) and every element of the domain set is mapped to an element of the codomain then at least two elements of the domain have the same image in the codomain. Meaning at least two elements of the domain shared an element of the codomain. 

Examples: Ignoring leap year there are 365 days in a year
- The minimum number of people needed to guarantee that at least two people shares the same birthday is 366.


# General Definition

Suppose you have 13 candy bars and you have 3 friends. One of the friends will get at least $x$ candy bars. The largest $x$ is 5. 
- If there are 12 candy bars then each friend gets at least 4 since $\dfrac {12}{3} = 4$, therefore if there 13 then one of the friends will get at least 5.
- Applying to function, if the domain set (finite) is larger than the codomain set (finite) and every element of the domain set is mapped to an element of the codomain then one of the element of the codomain will get mapped by at least $x$ elements of the domain. 

Suppose $A$ is the domain and $B$ is the codomain where $|A| > |B|$ and every element in the domain is mapped then easiest way to compute at least $x$ elements of the domain mapping to an element of the codomain is to do $\bigg \lceil \dfrac {|A|}{|B|} \bigg \rceil$. <br>
Using the candy bars (domain) and friends (codomain) as an example, $\lceil 13/3 \rceil = \lceil 4.333 \rceil = 5$. 