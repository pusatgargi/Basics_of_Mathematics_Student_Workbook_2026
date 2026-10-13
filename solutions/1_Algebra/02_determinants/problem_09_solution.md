# Problem 9: Area and the Determinant

## Problem Statement
The vectors

$$u=\begin{pmatrix}3\\1\end{pmatrix},\qquad v=\begin{pmatrix}1\\4\end{pmatrix}$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

## Theoretical Background and Concepts
The area of a parallelogram spanned by two vectors $u, v \in \mathbb{R}^2$ is given by the absolute value of the determinant of the matrix formed by placing the vectors as columns:

$$\text{Area} = |\det(u, v)|.$$

The determinant itself represents signed area. Reversing the order of the vectors swaps the two columns of the matrix, which changes the sign of the determinant, while the geometric area remains the absolute value.

## Detailed Step-by-Step Solution
1. **Compute area using order $(u, v)$:**
   Form the matrix $M_1 = \begin{pmatrix}3&1\\1&4\end{pmatrix}$.
   $$\det M_1 = (3)(4) - (1)(1) = 12 - 1 = 11.$$
   The area of the parallelogram is:
   $$\text{Area} = |\det M_1| = |11| = 11.$$

2. **Reverse the order of the vectors to $(v, u)$:**
   Form the matrix $M_2 = \begin{pmatrix}1&3\\4&1\end{pmatrix}$.
   $$\det M_2 = (1)(1) - (3)(4) = 1 - 12 = -11.$$

3. **Comparison:**
   - **What changes in the determinant:** Reversing the order swaps the two columns of the matrix, which reverses the sign of the determinant from $+11$ to $-11$.
   - **What does not change in the area:** The geometric area does not change because area is non-negative and defined by the absolute value:
     $$\text{Area} = |\det M_2| = |-11| = 11.$$

## Verification and Consistency Checks
The determinant reflects the standard column-swap rule: $\det(v, u) = -\det(u, v)$. Both determinants have absolute value $11$, confirming that the geometric area is $11$ regardless of vector ordering.
