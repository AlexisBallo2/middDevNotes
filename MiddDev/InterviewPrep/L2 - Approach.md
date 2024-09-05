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
			 ford from 1 to n
				 if a3 + b3 == c3 +d3 7 print a, b, c, d
```





