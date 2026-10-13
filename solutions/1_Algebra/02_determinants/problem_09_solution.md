# Problem 9: Area and the Determinant

## Problem Statement
The vectors

$$u=\begin{pmatrix}3\\1\end{pmatrix},\qquad v=\begin{pmatrix}1\\4\end{pmatrix}$$

span a parallelogram. Compute its area using a determinant. Then reverse the order of the vectors and explain what changes in the determinant and what does not change in the area.

## Theoretical Background and Concepts
The area of a parallelogram spanned by two column vectors $u, v \in \mathbb{R}^2$ is given by the absolute value of the determinant of the matrix formed by placing the vectors as columns (or rows):

$$\text{Area} = |\det(u, v)|.$$

The determinant itself represents the **signed (oriented) area**:
- $\det(u, v) > 0$ means the ordered pair $(u, v)$ has a counterclockwise (positive/right-handed) orientation.
- $\det(u, v) < 0$ means the ordered pair has a clockwise (negative/left-handed) orientation.

Swapping two columns in a matrix changes the sign of the determinant, reflecting the reversal of orientation, but leaves the absolute value (the geometric area) unchanged.

## Detailed Step-by-Step Solution
1. **Compute area using order $(u, v)$:**
   Form matrix $M_1 = \begin{pmatrix}3&1\\1&4\end{pmatrix}$.
   $$\det M_1 = (3)(4) - (1)(1) = 12 - 1 = 11.$$
   The area of the parallelogram is:
   $$\text{Area} = |\det M_1| = |11| = 11.$$

2. **Reverse the vector order $(v, u)$:**
   Form matrix $M_2 = \begin{pmatrix}1&3\\4&1\end{pmatrix}$.
   $$\det M_2 = (1)(1) - (3)(4) = 1 - 12 = -11.$$

3. **Comparison and Explanation:**
   - **What changes:** The determinant changes sign from $11$ to $-11$. This sign reflects the reversal of orientation: turning from $u$ to $v$ is counterclockwise, whereas turning from $v$ to $u$ is clockwise.
   - **What does not change:** The geometric area remains unchanged because area is non-negative and defined as the absolute value: $|-11| = 11$.

## Verification and Consistency Checks
- Using the cross product in $\mathbb{R}^3$:
  $$\tilde{u} = (3, 1, 0)^T,\quad \tilde{v} = (1, 4, 0)^T.$$
  $$\tilde{u} \times \tilde{v} = (0, 0, 3 \cdot 4 - 1 \cdot 1)^T = (0, 0, 11)^T.$$
  $$\|\tilde{u} \times \tilde{v}\| = 11.$$
  The geometric area is confirmed to be exactly $11$.
