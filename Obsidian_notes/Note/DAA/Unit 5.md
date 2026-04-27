- Complexity classes group problems based on the resource required to solve them 
- Computational complexity theory studies the resource required to solve computational problems It helps us understands which problems can be solved efficiently and which are inherently difficult 

![[Pasted image 20260428024037.png]]


## Types of Complexity 

**Classes -P class**
- P in p class stands for Polynomial time It is the collection of decision problems that can be solved by a deterministic machine in polynomial time 
- Solution to p problems is easy to find 
- A problem is **tractable** if:

- It can be solved theoretically, **and**
- It can also be solved practically in real life with computers.
	So most problems in **P** are called tractable.

 •Finding a name in a sorted list
• Arranging marks in order
• Finding the shortest route on maps

 **Intractable means:**
 Some problems can technically be solved, but they take **too much time** for large inputs.
![[Pasted image 20260428025719.png]]

**Classes-NP class**
- Np class problems are those where the solution can be verified in polynomial time but we don't know how to solve them efficiently
- If you have a solution we can check if the solution is correct in a reasonable amount of time 
![[Pasted image 20260428032753.png]]

**Classes -NP Hard**
- A problem is **NP-Hard** if it is **at least as difficult as the hardest problems in NP**.
- If you can solve one NP-Hard problem quickly, you can solve all NP problems quickly.
- Many NP-Hard problems ask for the **best solution**, not just yes/no.
 
   
**Example:**

- Best route for delivery truck
- Best timetable
- Validating password/logic constraints

## Reduction

Reduction means converting one problem into another.

If Problem A can be reduced to Problem B:

- Solving B helps solve A.

So if every NP problem reduces to problem B, then B is NP-Hard.![[Pasted image 20260428034314.png]]

**Classes - NP Complete**

- A problem is **NP-Complete** if it is:

1. **In NP** → Solution can be checked quickly
2. **NP-Hard** → As hard as the hardest NP problems

So NP-Complete problems are the **hardest problems inside NP**.

If **one NP-Complete problem** is solved in polynomial time, then **all NP problems** can also be solved in polynomial time.

**Examples**
- Hamiltonian Cycle
- Satisfiability (SAT)
- Vertex Cover
![[Pasted image 20260428034847.png]]


















