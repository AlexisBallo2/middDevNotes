Refer to [[Cracking the Coding Interview.pdf#page=73]]


# Overview
## Listen
- Note *unique* information in a problem
## Example
- Draw an example
## Brute Force
- State the obvious solution
## Optimize
- Optimize the brute force solution
## Walk through
- Walk through algorithm and get a sense for how it behaves on an example
## Implement
- Actually code it 


# Example

> Print all positive integer solutions to $a^3 + b^3 = c^3 + d^3$ where a,b,c,d are all integers between 1 and 1000

## Listen
- all integers 
- between 1 and 1000
## Example
- a = 1, b = 1, c = 1, d = 1
- a = 2, b = 1, c = 2, d = 1

## Brute force
```pseudo
 n = 1000
 for a from 1 to n
	 for b from 1 to n
		 for c from 1 to n 
			 for d from 1 to n
				 if a^3 + b^3 == c^3 +d^3
					 print a, b, c, d
```
## Optimize
currently $O(n^4)$

is there excess work done? 
- after we find a d, we wont find another for the current values of a, b, c, d

```pseudo
 n = 1000
 for a from 1 to n
	 for b from 1 to n
		 for c from 1 to n 
			 for d from 1 to n
				 if a^3 + b^3 == c^3 +d^3
					 print a, b, c, d
```
still $O(n^4)$

is there excess work done? 
- for a, b, c there is only one value of d. so lets solve for it
$d = \sqrt[3]{a^3 + b^3 - c^3}$

```pseudo
 n = 1000
 for a from 1 to n
	 for b from 1 to n
		 for c from 1 to n 
			 d = pow(a^3 + b^3 - c^3, 3)
			 print a, b, c, d
```

now $O(n^3)$

do we have any duplicated work? 
- current alg looks at all (a,b) pairs then all (c,d) pairs that match
	- for each of the (a,b) pairs, lets save what $a^3 + b^3$ equals, and then use that value for the $c^3 + d^3$ 







