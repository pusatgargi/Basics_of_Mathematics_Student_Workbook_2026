# Problem 4: Gauss–Jordan

## Problem Statement
Find $A^{-1}$ using the Gauss–Jordan method for

$$A=\begin{pmatrix}1&2\\3&5\end{pmatrix}.$$

Show the augmented matrix $[A\mid I]$ after successive operations and explain why obtaining $I$ on the left gives the inverse on the right.

## Theoretical Background and Concepts
The Gauss–Jordan method sets up the augmented block matrix $[A \mid I]$. Row operations are performed to systematically transform the left block into $I$:
1. Clear entries below the first pivot to create an upper-triangular block.
2. Scale the second pivot to make it $1$.
3. Clear entries above the second pivot to obtain the identity matrix $I$.

**Why the right block becomes $A^{-1}$:**
Elementary row operations correspond to multiplication on the left by elementary matrices. Let $E$ denote the combined action of all row operations applied to the matrix.
Applying this action to the augmented matrix transforms both blocks simultaneously:
$$E[A \mid I] = [EA \mid EI].$$
When the left block becomes the identity matrix, we have $EA = I$, which means $E$ is precisely $A^{-1}$. Consequently, the right block simultaneously becomes $EI = E = A^{-1}$.

## Detailed Step-by-Step Solution
1. **Initial augmented matrix $[A \mid I]$:**
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 3 & 5 & 0 & 1 \end{array}\right]$$

2. **Step 1: Clear below the first pivot ($a_{11} = 1$):**
   Apply $R_2 \leftarrow R_2 - 3R_1$:
   - Left block: $(3 - 3(1),\; 5 - 3(2)) = (0, -1)$
   - Right block: $(0 - 3(1),\; 1 - 3(0)) = (-3, 1)$

   Augmented matrix after clearing below the pivot:
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & -1 & -3 & 1 \end{array}\right]$$

3. **Step 2: Make the second pivot equal to $1$:**
   Apply $R_2 \leftarrow -R_2$:
   - Left block: $(0, 1)$
   - Right block: $(3, -1)$

   Augmented matrix after normalizing the pivot:
   $$\left[\begin{array}{cc|cc} 1 & 2 & 1 & 0 \\ 0 & 1 & 3 & -1 \end{array}\right]$$

4. **Step 3: Clear above the second pivot ($a_{12} = 2$):**
   Apply $R_1 \leftarrow R_1 - 2R_2$:
   - Left block: $(1 - 2(0),\; 2 - 2(1)) = (1, 0)$
   - Right block: $(1 - 2(3),\; 0 - 2(-1)) = (1 - 6,\; 0 + 2) = (-5, 2)$

   Augmented matrix in reduced row echelon form $[I \mid A^{-1}]$:
   $$\left[\begin{array}{cc|cc} 1 & 0 & -5 & 2 \\ 0 & 1 & 3 & -1 \end{array}\right]$$

5. **Read off the inverse matrix:**
   $$A^{-1} = \begin{pmatrix}-5 & 2 \\ 3 & -1\end{pmatrix}.$$

## Verification and Consistency Checks
Check the product $A A^{-1}$ with explicit entry calculations:
$$AA^{-1} = \begin{pmatrix}1&2\\3&5\end{pmatrix}\begin{pmatrix}-5&2\\3&-1\end{pmatrix}$$
- Entry $(1,1)$: $1(-5) + 2(3) = -5 + 6 = 1$
- Entry $(1,2)$: $1(2) + 2(-1) = 2 - 2 = 0$
- Entry $(2,1)$: $3(-5) + 5(3) = -15 + 15 = 0$
- Entry $(2,2)$: $3(2) + 5(-1) = 6 - 5 = 1$

$$AA^{-1} = \begin{pmatrix}1&0\\0&1\end{pmatrix} = I.$$
The product equals the identity matrix, confirming the inverse.
