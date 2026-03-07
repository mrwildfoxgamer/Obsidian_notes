## Introduction
An algorithm is a finite set of steps used to solve a problem

Characteristics of an Algorithm
+ Input -Algorithm takes input values
+ Output - Produces result
+ Definiteness - Each step is clearly defined
+ Fineness - Algorithm must stop after a finite number of steps
+ Effectiveness - Steps must be simple and executable

## Analysis of algorithm
Analysis of algorithm means how efficient an algorithm is 
it measures Time complexity and space complexity

## Types of Analysis

1. Priori Analysis 
	+ Done before Executing the algorithm
	+ independent of hardware
	+ gives approximate result
2. Posteriori Analysis
	+ Done after running the algorithm
	+ Depends on hardware and programming language
	+ Give exact result
## Cases in Algorithm Analysis

1. Best case
	 + minimum time taken by the algorithm
2. Worst case
	+ Maximum time taken by algorithm
3. Average  case 
	+ Average time taken

## Frequency count Method

This method calculates how many time each statement executes
`f(n)`

```
S=0
for i=0 to n
s=s+a[i]
```
frequency function
`f(n)=2n+3`
Time complexity:
`O(n)`
Space Complexity
`O(n)`

# 7. Types of Time Complexity

| Notation | Meaning     |
| -------- | ----------- |
| O(1)     | Constant    |
| O(log n) | Logarithmic |
| O(n)     | Linear      |
| O(n²)    | Quadratic   |
| O(n³)    | Cubic       |
| O(2ⁿ)    | Exponential |
```
1 < log n < √n < n < n log n < n² < n³ < 2ⁿ
```

## Asymptotic Notations

Asymptotic notation describes how the running time of an algorithm grows with input size

Three main notations are:
1. **Big O (O)**
2. **Omega (Ω)**
3. **Theta (Θ)**

#### Big O notation
Big - o notation represents the upper bound (worst case) of an algorithm time complexity
#### Omega notation (Ω)
Omega represents the lower bound(  best case ) time complexity
#### Theta Notation (Θ)
Theta represents the exact bound (both upper and lower bounds)