# Divide and Conquer

Divide and Conquer is a fundamental algorithm design paradigm. 
It works by recursively breaking down a problem into two or more subproblems of the same or related type, until these become simple enough to be solved directly. 
The solutions to the subproblems are then combined to give a solution to the original problem.  
  
## The Three-Step Process
A divide-and-conquer algorithm has three distinct parts:
  1. **Divide**: The main problem is split into smaller, independent subproblems. These subproblems are smaller instances of the original problem.
  2. **Conquer**: The subproblems are solved. This is often done recursively, meaning the algorithm applies the same "divide and conquer" strategy to each subproblem. If a subproblem is small enough (a "base case"), it is solved directly without further division.
  3. **Combine**: The solutions to the subproblems are combined or merged to create a solution to the original, larger problem.
