# Problem 15: Two Methods for Solving the Same System

## Problem Statement
For

$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}7\\8\end{pmatrix}$$

solve $Ax=b$ in two ways:

1. using $A^{-1}b$,
2. using Gaussian elimination.

Compare both solutions, the number of essential steps, and state which method was simpler in this example.

## Theoretical Background and Concepts
A system of linear equations $Ax = b$ with a non-singular square matrix $A$ can be solved by:
1. **Matrix Inversion:** First compute $A^{-1}$, then perform matrix-vector multiplication $x = A^{-1}b$.
2. **Gaussian Elimination:** Row reduce the augmented matrix $[A \mid b]$ to row echelon form, followed by back substitution.

While both yield the identical unique solution, Gaussian elimination requires fewer computational operations ($O(n^3/3)$ operations) compared to computing the full inverse and then multiplying ($O(n^3) + O(n^2)$ operations). For small $2\times2$ systems, explicit inversion formulas are very quick, but Gaussian elimination remains the more efficient and numerically stable general method.

## Detailed Step-by-Step Solution
Given:
$$A=\begin{pmatrix}2&1\\1&3\end{pmatrix},\qquad b=\begin{pmatrix}7\\8\end{pmatrix}.$$

1. **Method 1: Using $A^{-1}b$:**
   - Step 1: Compute determinant:
     $$\det A = (2)(3) - (1)(1) = 6 - 1 = 5.$$
   - Step 2: Form inverse matrix:
     $$A^{-1} = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}.$$
   - Step 3: Multiply $x = A^{-1}b$:
     $$x = \frac{1}{5}\begin{pmatrix}3 & -1 \\ -1 & 2\end{pmatrix}\begin{pmatrix}7\\8\end{pmatrix} = \frac{1}{5}\begin{pmatrix}3(7) + (-1)(8) \\ (-1)(7) + 2(8)\end{pmatrix} = \frac{1}{5}\begin{pmatrix}21 - 8 \\ -7 + 16\end{pmatrix} = \frac{1}{5}\begin{pmatrix}13\\9\end{pmatrix} = \begin{pmatrix}\frac{13}{5} \\ \frac{9}{5}\end{pmatrix}.$$

2. **Method 2: Using Gaussian Elimination:**
   - Step 1: Set up augmented matrix $[A \mid b]$:
     $$\left[\begin{array}{cc|c} 2 & 1 & 7 \\ 1 & 3 & 8 \end{array}\right]$$
   - Step 2: Swap rows ($R_1 \leftrightarrow R_2$) for an easy leading 1:
     $$\left[\begin{array}{cc|c} 1 & 3 & 8 \\ 2 & 1 & 7 \end{array}\right]$$
   - Step 3: Eliminate below pivot ($R_2 \leftarrow R_2 - 2R_1$):
     $$\left[\begin{array}{cc|c} 1 & 3 & 8 \\ 0 & -5 & -9 \end{array}\right]$$
   - Step 4: Back substitution:
     From row 2: $-5x_2 = -9 \implies x_2 = \frac{9}{5}$.
     From row 1: $x_1 + 3\left(\frac{9}{5}\right) = 8 \implies x_1 = 8 - \frac{27}{5} = \frac{40 - 27}{5} = \frac{13}{5}$.
     Thus:
     $$x = \begin{pmatrix}\frac{13}{5} \\ \frac{9}{5}\end{pmatrix}.$$

3. **Comparison of Methods:**
   - Both methods produce the exact same solution: $x_1 = \frac{13}{5} = 2.6,\; x_2 = \frac{9}{5} = 1.8$.
   - **Number of essential steps:** Method 1 required 3 distinct calculations (determinant, adjugate matrix, and matrix-vector product). Method 2 required 1 row operation and back-substitution.
   - **Which method was simpler:** For this specific $2\times2$ problem, both methods are comparable in simplicity, but Method 1 (formula $A^{-1}b$) is very direct because the $2\times2$ inverse formula requires no elimination steps. For larger systems ($n \ge 3$), Gaussian elimination is noticeably simpler and avoids computing unnecessary intermediate entries.

## Verification and Consistency Checks
Substitute $x_1 = \frac{13}{5}, x_2 = \frac{9}{5}$ back into the original system:
- Equation 1: $2x_1 + x_2 = 2\left(\frac{13}{5}\right) + \frac{9}{5} = \frac{26 + 9}{5} = \frac{35}{5} = 7$.
- Equation 2: $x_1 + 3x_2 = \frac{13}{5} + 3\left(\frac{9}{5}\right) = \frac{13 + 27}{5} = \frac{40}{5} = 8$.
Both equations are satisfied exactly.
