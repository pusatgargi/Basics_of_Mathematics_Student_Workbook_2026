# Problem 7: Choosing a Method Deliberately

## Problem Statement
Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix
   $$\begin{cases}2x-y=3,\\4y=8;\end{cases}$$
2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

## Theoretical Background and Concepts
Different computational methods for linear systems are optimal under different conditions:
- **Back substitution:** When the coefficient matrix is already triangular (or in echelon form), elimination is entirely unnecessary; back substitution solves the system directly in $O(n^2/2)$ operations.
- **Matrix-vector multiplication via $A^{-1}$:** When solving multiple systems $Ax = b_i$ ($i = 1, 2, \dots, k$) sharing the same invertible matrix $A$ whose inverse $A^{-1}$ is precomputed, computing each solution costs only one matrix-vector multiplication $O(n^2)$. Re-solving via elimination each time would cost $k \times O(n^3/3)$.
- **Gaussian elimination with LU/back substitution:** When solving a single system once and $A^{-1}$ is not known, Gaussian elimination is by far the most efficient method ($O(n^3/3)$ operations). Computing $A^{-1}$ requires $O(n^3)$ operations—roughly three times more work—and produces unnecessary intermediate entries.

## Detailed Step-by-Step Solution
1. **Case 1: System with triangular coefficient matrix:**
   $$\begin{cases}2x - y = 3 \\ 4y = 8\end{cases}$$
   - **Chosen Method:** **Direct Back Substitution**.
   - **Justification:** The coefficient matrix $\begin{pmatrix}2&-1\\0&4\end{pmatrix}$ is already upper triangular. No row reduction or matrix inversion is needed.
   - **Execution:**
     - From equation 2: $4y = 8 \implies y = \frac{8}{4} = 2$.
     - From equation 1: $2x - (2) = 3 \implies 2x = 5 \implies x = \frac{5}{2}$.
   - **Result:** $(x, y) = \left(\frac{5}{2}, 2\right)$.

2. **Case 2: Three systems $Ax = b_i$ with the same invertible $A$ and known $A^{-1}$:**
   - **Chosen Method:** **Matrix-Vector Multiplication: $x_i = A^{-1} b_i$ for each $i \in \{1, 2, 3\}$**.
   - **Plan and Reusability:**
     Since $A^{-1}$ is already available, computing the solution for each right-hand side requires only one matrix-vector product $A^{-1}b_i$.
     The precomputed matrix $A^{-1}$ is completely reusable across all three systems.
     Setting up and running elimination three separate times would be redundant and waste computational effort.

3. **Case 3: Single $3\times3$ system, inverse not given, single solution vector needed:**
   - **Chosen Method:** **Gaussian Elimination with Back Substitution**.
   - **Plan and Efficiency:**
     Form the augmented matrix $[A \mid b]$ and apply Gaussian elimination to reduce it to upper triangular form, followed by back substitution.
     - **Unnecessary work avoided:** Finding $A^{-1}$ would require reducing $[A \mid I_3]$ (solving 3 separate columns simultaneously), which takes roughly 3 times as many operations. Since we only need the solution for a single vector $b$, calculating the other entries of $A^{-1}$ is entirely unnecessary.

## Verification and Consistency Checks
- For Case 1: Check substitution: $2(5/2) - 2 = 5 - 2 = 3$ $\checkmark$ and $4(2) = 8$ $\checkmark$.
- The operation counts ($O(n^2)$ for back substitution, $O(n^2)$ per RHS with known inverse, $O(n^3/3)$ for Gaussian elimination vs $O(n^3)$ for full inversion) confirm that each choice minimizes computational complexity.
