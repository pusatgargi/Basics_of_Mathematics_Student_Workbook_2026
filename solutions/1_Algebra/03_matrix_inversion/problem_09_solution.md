# Problem 9: Matrix Equation

## Problem Statement
Given

$$A=\begin{pmatrix}1&2\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}3&1\\2&4\end{pmatrix}.$$

Solve the equation $AX=B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

## Theoretical Background and Concepts
In matrix algebra, multiplication is non-commutative ($MN \neq NM$ in general). Therefore, when solving a matrix equation:
- To eliminate $A$ from the left of $X$ in $AX = B$, we must multiply **from the left** by $A^{-1}$:
  $$A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies X = A^{-1}B.$$
- Multiplying from the right would yield $AX A^{-1} = B A^{-1}$, which does not isolate $X$.
Hence, the side from which we multiply is uniquely determined by the position of the coefficient matrix.

## Detailed Step-by-Step Solution
1. **Decide the side for $A^{-1}$:**
   Since $A$ appears on the left of $X$, we must multiply by $A^{-1}$ from the **left**:
   $$X = A^{-1}B.$$

2. **Compute $A^{-1}$:**
   For $A = \begin{pmatrix}1&2\\0&1\end{pmatrix}$:
   $$\det A = (1)(1) - (2)(0) = 1.$$
   Using the $2\times2$ inverse formula:
   $$A^{-1} = \frac{1}{1}\begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix} = \begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix}.$$

3. **Compute $X = A^{-1}B$:**
   $$X = \begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix}\begin{pmatrix}3 & 1 \\ 2 & 4\end{pmatrix}$$
   Computing entries:
   - Row 1, Column 1: $1(3) + (-2)(2) = 3 - 4 = -1$
   - Row 1, Column 2: $1(1) + (-2)(4) = 1 - 8 = -7$
   - Row 2, Column 1: $0(3) + 1(2) = 2$
   - Row 2, Column 2: $0(1) + 1(4) = 4$

   Therefore:
   $$X = \begin{pmatrix}-1 & -7 \\ 2 & 4\end{pmatrix}.$$

4. **Check by computing $AX$:**
   $$AX = \begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}-1&-7\\2&4\end{pmatrix}$$
   - Row 1, Column 1: $1(-1) + 2(2) = -1 + 4 = 3$
   - Row 1, Column 2: $1(-7) + 2(4) = -7 + 8 = 1$
   - Row 2, Column 1: $0(-1) + 1(2) = 2$
   - Row 2, Column 2: $0(-7) + 1(4) = 4$

   $$AX = \begin{pmatrix}3&1\\2&4\end{pmatrix} = B.$$

## Verification and Consistency Checks
- The computed product $AX$ matches matrix $B$ exactly.
- If we had mistakenly multiplied from the right, $B A^{-1}$ would have given:
  $$\begin{pmatrix}3&1\\2&4\end{pmatrix}\begin{pmatrix}1&-2\\0&1\end{pmatrix} = \begin{pmatrix}3&-5\\2&0\end{pmatrix} \neq X,$$
  confirming that multiplying from the correct side is critical.
