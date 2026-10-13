# Problem 4: Gauss–Jordan

## Problem Statement
Find $A^{-1}$ using the Gauss–Jordan method for

$$A=\begin{pmatrix}1&2\\3&5\end{pmatrix}.$$

Show the augmented matrix $[A\mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

## Theoretical Background and Concepts
The Gauss–Jordan method computes the matrix inverse by setting up the augmented block matrix:

$$[A \mid I].$$

Elementary row operations are applied to transform the left block into the identity matrix $I$.
Each elementary row operation corresponds to multiplying on the left by an elementary matrix $E_k$.
When the sequence of operations $E_k \cdots E_2 E_1$ transforms $A$ into $I$:

$$(E_k \cdots E_2 E_1) A = I \implies (E_k \cdots E_2 E_1) = A^{-1}.$$

Applying the exact same sequence of row operations to the right block $I$ simultaneously produces:

$$(E_k \cdots E_2 E_1) I = A^{-1}.$$

Thus, when $[A \mid I] \xrightarrow{\text{row ops}} [I \mid B]$, the resulting matrix $B$ is necessarily $A^{-1}$.

## Detailed Step-by-Step Solution
1. **Set up the augmented matrix $[A \mid I]$:**
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array}\right]$$

2. **Step 1: Eliminate the entry below the pivot $a_{11}$:**
   Apply $R_2 \leftarrow R_2 - 3R_1$:
   - Left side: $R_2 = (3 - 3(1),\; 5 - 3(2)) = (0, -1)$
   - Right side: $R_2 = (0 - 3(1),\; 1 - 3(0)) = (-3, 1)$

   Augmented matrix after Step 1:
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array}\right]$$

3. **Step 2: Normalize the pivot in the second row:**
   Apply $R_2 \leftarrow -R_2$:
   - Left side: $R_2 = (0, 1)$
   - Right side: $R_2 = (3, -1)$

   Augmented matrix after Step 2:
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array}\right]$$

4. **Step 3: Eliminate the entry above the pivot $a_{22}$:**
   Apply $R_1 \leftarrow R_1 - 2R_2$:
   - Left side: $R_1 = (1 - 2(0),\; 2 - 2(1)) = (1, 0)$
   - Right side: $R_1 = (1 - 2(3),\; 0 - 2(-1)) = (1 - 6,\; 0 + 2) = (-5, 2)$

   Augmented matrix after Step 3:
   $$\left[\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array}\right]$$

5. **Read off the inverse matrix:**
   Since the left block is now the identity matrix $I$, the right block is $A^{-1}$:
   $$A^{-1} = \begin{pmatrix}-5 & 2 \\ 3 & -1\end{pmatrix}.$$

## Verification and Consistency Checks
- Multiply $A$ and $A^{-1}$:
  $$AA^{-1} = \begin{pmatrix}1&2\\3&5\end{pmatrix}\begin{pmatrix}-5&2\\3&-1\end{pmatrix} = \begin{pmatrix}1(-5)+2(3) & 1(2)+2(-1) \\ 3(-5)+5(3) & 3(2)+5(-1)\end{pmatrix} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
- Verify with the $2\times2$ inverse formula:
  $$\det A = (1)(5) - (2)(3) = 5 - 6 = -1.$$
  $$A^{-1} = \frac{1}{-1}\begin{pmatrix}5&-2\\-3&1\end{pmatrix} = \begin{pmatrix}-5&2\\3&-1\end{pmatrix}.$$
  Both methods produce the identical inverse matrix.
