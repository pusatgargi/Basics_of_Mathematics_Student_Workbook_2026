# Problem 5: A 3x3 Matrix

## Problem Statement
Use Gauss–Jordan elimination to find the inverse of

$$A=\begin{pmatrix}1&1&0\\0&1&1\\1&0&1\end{pmatrix}.$$

Check the result by multiplication.

## Theoretical Background and Concepts
To invert a $3\times3$ matrix using Gauss–Jordan elimination, we form the augmented matrix $[A \mid I_3]$.
We systematically apply elementary row operations to transform the left block into the identity matrix $I_3$:
1. Use pivots to eliminate entries below the main diagonal (forward elimination).
2. Scale each pivot row so the diagonal entries become $1$.
3. Use pivots to eliminate entries above the main diagonal (backward elimination).

Because every row operation corresponds to multiplying on the left by an invertible operation, the cumulative transformation $E$ that reduces $A$ to $I_3$ ($EA = I_3$) simultaneously transforms the right block $I_3$ into $E I_3 = E = A^{-1}$.

## Detailed Step-by-Step Solution
1. **Initial augmented matrix $[A \mid I_3]$:**
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 1 & 0 & 1 & 0 & 0 & 1 \end{array}\right]$$

2. **Step 1: Clear below the first pivot in Column 1:**
   Entry $a_{21}$ is already $0$. To eliminate $a_{31} = 1$, apply $R_3 \leftarrow R_3 - R_1$:
   - Left: $(1-1,\; 0-1,\; 1-0) = (0, -1, 1)$
   - Right: $(0-1,\; 0-0,\; 1-0) = (-1, 0, 1)$

   Matrix after Step 1:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & -1 & 1 & -1 & 0 & 1 \end{array}\right]$$

3. **Step 2: Clear below the second pivot in Column 2:**
   To eliminate $a_{32} = -1$, apply $R_3 \leftarrow R_3 + R_2$:
   - Left: $(0+0,\; -1+1,\; 1+1) = (0, 0, 2)$
   - Right: $(-1+0,\; 0+1,\; 1+0) = (-1, 1, 1)$

   Matrix after Step 2:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 2 & -1 & 1 & 1 \end{array}\right]$$

4. **Step 3: Normalize the third pivot to $1$:**
   Apply $R_3 \leftarrow \frac{1}{2}R_3$:
   - Left: $(0, 0, 1)$
   - Right: $\left(-\frac{1}{2},\; \frac{1}{2},\; \frac{1}{2}\right)$

   Matrix after Step 3:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 1 & 0 & 1 & 0 \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

5. **Step 4: Clear above the third pivot in Column 3:**
   To eliminate $a_{23} = 1$, apply $R_2 \leftarrow R_2 - R_3$:
   - Left: $(0, 1, 1-1) = (0, 1, 0)$
   - Right: $\left(0 - \left(-\frac{1}{2}\right),\; 1 - \frac{1}{2},\; 0 - \frac{1}{2}\right) = \left(\frac{1}{2},\; \frac{1}{2},\; -\frac{1}{2}\right)$

   Matrix after Step 4:
   $$\left[\begin{array}{ccc|ccc} 1 & 1 & 0 & 1 & 0 & 0 \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

6. **Step 5: Clear above the second pivot in Column 2:**
   To eliminate $a_{12} = 1$, apply $R_1 \leftarrow R_1 - R_2$:
   - Left: $(1, 1-1, 0) = (1, 0, 0)$
   - Right: $\left(1 - \frac{1}{2},\; 0 - \frac{1}{2},\; 0 - \left(-\frac{1}{2}\right)\right) = \left(\frac{1}{2},\; -\frac{1}{2},\; \frac{1}{2}\right)$

   Final matrix $[I_3 \mid A^{-1}]$:
   $$\left[\begin{array}{ccc|ccc} 1 & 0 & 0 & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ 0 & 1 & 0 & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ 0 & 0 & 1 & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \end{array}\right]$$

   Thus,
   $$A^{-1} = \begin{pmatrix}\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\ -\frac{1}{2} & \frac{1}{2} & \frac{1}{2}\end{pmatrix} = \frac{1}{2}\begin{pmatrix}1 & -1 & 1 \\ 1 & 1 & -1 \\ -1 & 1 & 1\end{pmatrix}.$$

## Verification and Consistency Checks
Compute $A A^{-1}$ by calculating representative diagonal and off-diagonal entries:
- Diagonal entry $(1,1)$: $\frac{1}{2}[1(1) + 1(1) + 0(-1)] = \frac{1}{2}(2) = 1$.
- Diagonal entry $(2,2)$: $\frac{1}{2}[0(-1) + 1(1) + 1(1)] = \frac{1}{2}(2) = 1$.
- Off-diagonal entry $(1,2)$: $\frac{1}{2}[1(-1) + 1(1) + 0(1)] = \frac{1}{2}(0) = 0$.
- Off-diagonal entry $(2,1)$: $\frac{1}{2}[0(1) + 1(1) + 1(-1)] = \frac{1}{2}(0) = 0$.
- Off-diagonal entry $(3,1)$: $\frac{1}{2}[1(1) + 0(1) + 1(-1)] = \frac{1}{2}(0) = 0$.
All diagonal entries evaluate to $1$ and all off-diagonal entries evaluate to $0$, confirming $AA^{-1} = I_3$.
