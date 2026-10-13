# Problem 5: A 3x3 Matrix

## Problem Statement
Use Gauss–Jordan elimination to find the inverse of

$$A=\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix}.$$

Check the result by multiplication.

## Theoretical Background and Concepts
To find the inverse of a $3\times3$ matrix, we form the augmented matrix:

$$[A \mid I_3] = \left[\begin{array}{ccc|ccc} a_{11} & a_{12} & a_{13} & 1 & 0 & 0 \\ a_{21} & a_{22} & a_{23} & 0 & 1 & 0 \\ a_{31} & a_{32} & a_{33} & 0 & 0 & 1 \end{array}\right]$$

and apply elementary row operations until the left block becomes the $3\times3$ identity matrix $I_3$. The sequence of row operations that transforms $A$ into $I_3$ simultaneously transforms $I_3$ into $A^{-1}$.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid I]$:**
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 1 & 0 & 1 & 0 & 0 & 1 \end{array}\right]$$

2. **Step 1: Eliminate $a_{31}$ using Row 1:**
   Apply $R_3 \leftarrow R_3 - R_1$:
   - Left: $(1-1, 0-1, 1-0) = (0, -1, 1)$
   - Right: $(0-1, 0-0, 1-0) = (-1, 0, 1)$

   Matrix:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & -1 & 1 & -1 & 0 & 1 \end{array}\right]$$

3. **Step 2: Eliminate $a_{32}$ using Row 2:**
   Apply $R_3 \leftarrow R_3 + R_2$:
   - Left: $(0+0, -1+1, 1+1) = (0, 0, 2)$
   - Right: $(-1+0, 0+1, 1+0) = (-1, 1, 1)$

   Matrix:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 2 & -1 & 1 & 1 \end{array}\right]$$

4. **Step 3: Normalize Row 3 pivot:**
   Apply $R_3 \leftarrow \frac{1}{2}R_3$:
   - Left: $(0, 0, 1)$
   - Right: $\left(-\frac{1}{2}, \frac{1}{2}, \frac{1}{2}\right)$

   Matrix:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

5. **Step 4: Eliminate $a_{23}$ using Row 3:**
   Apply $R_2 \leftarrow R_2 - R_3$:
   - Left: $(0, 1, 1 - 1) = (0, 1, 0)$
   - Right: $\left(0 - \left(-\frac{1}{2}\right),\; 1 - \frac{1}{2},\; 0 - \frac{1}{2}\right) = \left(\frac{1}{2}, \frac{1}{2}, -\frac{1}{2}\right)$

   Matrix:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

6. **Step 5: Eliminate $a_{12}$ using Row 2:**
   Apply $R_1 \leftarrow R_1 - R_2$:
   - Left: $(1, 1 - 1, 0) = (1, 0, 0)$
   - Right: $\left(1 - \frac{1}{2},\; 0 - \frac{1}{2},\; 0 - \left(-\frac{1}{2}\right)\right) = \left(\frac{1}{2}, -\frac{1}{2}, \frac{1}{2}\right)$

   Matrix:
   $$\left[\begin{array}{ccc|ccc} 1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

7. **Conclusion:**
   The left block is $I_3$, so the right block is $A^{-1}$:
   $$A^{-1} = \begin{pmatrix} \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{pmatrix} = \frac{1}{2} \begin{pmatrix} 1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1 \end{pmatrix}.$$

## Verification and Consistency Checks
Compute $A A^{-1}$:
$$A A^{-1} = \begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix} \cdot \frac{1}{2}\begin{pmatrix}1&-1&1\\1&1&-1\\-1&1&1\end{pmatrix}$$
- Row 1: $\frac{1}{2}(1\cdot1 + 1\cdot1 + 0, \; 1(-1) + 1\cdot1 + 0, \; 1\cdot1 + 1(-1) + 0) = \frac{1}{2}(2, 0, 0) = (1, 0, 0)$
- Row 2: $\frac{1}{2}(0 + 1\cdot1 + 1(-1), \; 0 + 1\cdot1 + 1\cdot1, \; 0 + 1(-1) + 1\cdot1) = \frac{1}{2}(0, 2, 0) = (0, 1, 0)$
- Row 3: $\frac{1}{2}(1\cdot1 + 0 + 1(-1), \; 1(-1) + 0 + 1\cdot1, \; 1\cdot1 + 0 + 1\cdot1) = \frac{1}{2}(0, 0, 2) = (0, 0, 1)$

$$A A^{-1} = \begin{pmatrix}1&0&0\\0&1&0\\0&0&1\end{pmatrix} = I_3.$$
The inverse is confirmed.
