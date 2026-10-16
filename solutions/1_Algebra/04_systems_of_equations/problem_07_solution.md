# Problem 7: Choosing a Method Deliberately

## Problem Statement
Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix
   $$\begin{cases}2x-y=3,\\4y=8;\end{cases}$$
2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

## Theoretical Background and Concepts
Different linear systems call for different optimal methods depending on matrix structure and the number of right-hand sides:
- Triangular systems need no elimination; direct back substitution finds solutions immediately.
- Multiple systems with a known inverse benefit from reusing the precomputed matrix: $x_i = A^{-1}b_i$ requires only matrix-vector multiplication.
- A single system without a precomputed inverse is most appropriately approached by Gaussian elimination: row reduction reveals whether the system is consistent, unique (when every variable column has a pivot), or has free variables, while avoiding the unnecessary work of computing a full inverse for a single right-hand side.

## Detailed Step-by-Step Solution
1. **Case 1: System with triangular coefficient matrix:**
   $$\begin{cases}2x-y=3\\4y=8\end{cases}$$
   - **Chosen Method:** **Direct Back Substitution**.
   - **Justification:** The coefficient matrix $\begin{pmatrix}2&-1\\0&4\end{pmatrix}$ is already upper triangular. Performing row operations or computing an inverse would be completely redundant.
   - **Full Execution:**
     - From equation 2: $4y = 8 \implies y = 2$.
     - From equation 1: $2x - (2) = 3 \implies 2x = 5 \implies x = \frac{5}{2}$.
   - **Solution:** $(x, y) = \left(\frac{5}{2}, 2\right)$.

2. **Case 2: Three systems $Ax = b_i$ with the same invertible matrix $A$ and known $A^{-1}$:**
   - **Chosen Method:** **Matrix-Vector Multiplication ($x_i = A^{-1}b_i$)**.
   - **Plan and Reusability:**
     Since $A^{-1}$ is already computed, each solution vector $x_i$ is found by computing the single product $A^{-1}b_i$.
     The precomputed matrix $A^{-1}$ is reused three times. Setting up and running elimination three separate times would be redundant and waste computational effort.

3. **Case 3: One $3\times3$ system, inverse not given, single solution vector needed:**
   - **Chosen Method:** **Gaussian Elimination (Row Reduction)**.
   - **Plan and Diagnosis:**
     Form the augmented matrix $[A \mid b]$ and perform forward row reduction to row-echelon form. Because the problem statement does not assume that $A$ is invertible, elimination directly reveals the structure and solvability of the system:
     - If a contradiction row $[0\; 0\; 0 \mid d]$ with $d \neq 0$ appears, the system is inconsistent (no solution).
     - If there are fewer than three pivot columns and no contradiction, the system has free variables (infinitely many solutions).
     - A unique solution is guaranteed only when all three variable columns have pivots (full rank). In that case, back substitution computes the unique solution vector $x$.
   - *Unnecessary computation avoided:* Computing the entire inverse matrix $A^{-1}$ (which requires reducing $[A \mid I_3]$) performs substantial unnecessary work across all three columns of $I_3$ to obtain full matrix entries that are never needed, and it would fail altogether if $A$ is not invertible. Elimination solves directly for the single right-hand side vector $b$ while determining solvability.

## Verification and Consistency Checks
For Case 1, substitute $(x, y) = (5/2, 2)$:
- $2(5/2) - 2 = 5 - 2 = 3$ $\checkmark$
- $4(2) = 8$ $\checkmark$
Both equations are verified.
