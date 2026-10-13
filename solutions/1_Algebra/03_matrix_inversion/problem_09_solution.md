# Problem 9: Matrix Equation

## Problem Statement
Given

$$A=\begin{pmatrix}1&2\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}3&1\\2&4\end{pmatrix}.$$

Solve the equation $AX=B$ for $X$. Before calculating, decide on which side of the equation $A^{-1}$ must be used. Then check the result by computing $AX$.

## Theoretical Background and Concepts
In the matrix equation $AX = B$, matrix $A$ multiplies $X$ from the left.
To isolate $X$, we must multiply both sides **from the left** by $A^{-1}$:
$$A^{-1}(AX) = A^{-1}B \implies (A^{-1}A)X = A^{-1}B \implies IX = A^{-1}B \implies X = A^{-1}B.$$
Multiplying on the right would give $AX A^{-1} = B A^{-1}$, which does not place $A^{-1}$ next to $A$ and fails to cancel $A$. Therefore, left multiplication is mandatory.

## Detailed Step-by-Step Solution
1. **Derive $A^{-1}$:**
   For $A = \begin{pmatrix}1&2\\0&1\end{pmatrix}$:
   Using the $2\times2$ inverse formula:
   $$\det A = 1(1) - 2(0) = 1.$$
   Swapping diagonal entries and negating off-diagonal entries gives:
   $$A^{-1} = \begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix}.$$
   *(Alternatively, $A$ maps $(u, v) \mapsto (u + 2v, v)$; undoing this coordinate shift requires $(u, v) \mapsto (u - 2v, v)$, which directly gives $A^{-1}$).*

2. **Compute $X = A^{-1}B$:**
   $$X = \begin{pmatrix}1 & -2 \\ 0 & 1\end{pmatrix}\begin{pmatrix}3 & 1 \\ 2 & 4\end{pmatrix}.$$
   Computing the entries by the row-column rule:
   - $x_{11} = 1(3) - 2(2) = 3 - 4 = -1$
   - $x_{12} = 1(1) - 2(4) = 1 - 8 = -7$
   - $x_{21} = 0(3) + 1(2) = 2$
   - $x_{22} = 0(1) + 1(4) = 4$

   Therefore:
   $$X = \begin{pmatrix}-1 & -7 \\ 2 & 4\end{pmatrix}.$$

3. **Check by computing $AX$:**
   $$AX = \begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}-1&-7\\2&4\end{pmatrix}$$
   Computing entries:
   - $(AX)_{11} = 1(-1) + 2(2) = -1 + 4 = 3$
   - $(AX)_{12} = 1(-7) + 2(4) = -7 + 8 = 1$
   - $(AX)_{21} = 0(-1) + 1(2) = 2$
   - $(AX)_{22} = 0(-7) + 1(4) = 4$

   Thus,
   $$AX = \begin{pmatrix}3&1\\2&4\end{pmatrix} = B.$$
   Recovering $B$ verifies that $X$ satisfies the original equation.

## Verification and Consistency Checks
The computed matrix $X$ satisfies $AX = B$ entry for entry. The derivation confirms that left cancellation is the unique valid algebraic path to isolate $X$.
