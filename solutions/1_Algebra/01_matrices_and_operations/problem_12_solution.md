# Problem 12: Formula for a Matrix Power

## Problem Statement
Let

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix}.$$

Compute $A^2$, $A^3$, and $A^4$, and use them to formulate a conjecture for $A^n$. Then do not stop after checking one more case: assume the formula is true for $n$, multiply by $A$, and explain why you obtain exactly the formula for $n+1$.

## Theoretical Background and Concepts
Powers of a matrix are defined recursively: $A^1 = A$ and $A^{n+1} = A^n A$. A pattern observed in the first few powers can be proven for all positive integers $n$ using mathematical induction.

## Detailed Step-by-Step Solution
Compute the initial powers:

$$A^2 = A \cdot A = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}
=\begin{pmatrix}1&2\\0&1\end{pmatrix}.$$

To find $A^3$, multiply $A^2$ by $A$:
Numerical calculation of the key upper-right entry:
$$(A^3)_{12} = (A^2 A)_{12} = 1\cdot1 + 2\cdot1 = 1 + 2 = 3.$$
The remaining entries are $(A^3)_{11}=1, (A^3)_{21}=0, (A^3)_{22}=1$.
Thus,

$$A^3 = \begin{pmatrix}1&3\\0&1\end{pmatrix}.$$

Similarly, multiplying $A^3$ by $A$:
$$(A^4)_{12} = (A^3 A)_{12} = 1\cdot1 + 3\cdot1 = 4.$$
Thus,

$$A^4 = \begin{pmatrix}1&4\\0&1\end{pmatrix}.$$

### Formulating the Conjecture
Based on these calculations, we conjecture:

$$A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}\quad \text{for all } n \ge 1.$$

### Inductive Step
- **Base Case:** For $n = 1$, the formula gives $\begin{pmatrix}1&1\\0&1\end{pmatrix} = A$, which matches the given matrix $A$.
- **Inductive Step:** Assume the formula holds for an integer $n \ge 1$, so:
  $$A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}.$$
  We now compute $A^{n+1} = A^n A$:
  $$A^{n+1} = \begin{pmatrix}1&n\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}.$$
  In this product, the key upper-right entry expands as:
  $$(A^{n+1})_{12} = 1\cdot 1 + n\cdot 1 = 1 + n = n + 1.$$
  The other entries are:
  - $(A^{n+1})_{11} = 1\cdot 1 + n\cdot 0 = 1$
  - $(A^{n+1})_{21} = 0\cdot 1 + 1\cdot 0 = 0$
  - $(A^{n+1})_{22} = 0\cdot 1 + 1\cdot 1 = 1$

  Putting these together yields:
  $$A^{n+1} = \begin{pmatrix}1 & n+1 \\ 0 & 1\end{pmatrix}.$$

This general calculation carries any verified case $n$ to the next case $n+1$. Since the base case $n=1$ is true, the formula holds for all positive integers $n$.

## Verification and Consistency Checks
The formula $A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}$ matches:
- $n=1: A^1 = \begin{pmatrix}1&1\\0&1\end{pmatrix}$,
- $n=2: A^2 = \begin{pmatrix}1&2\\0&1\end{pmatrix}$,
- $n=3: A^3 = \begin{pmatrix}1&3\\0&1\end{pmatrix}$,
- $n=4: A^4 = \begin{pmatrix}1&4\\0&1\end{pmatrix}$.
The inductive step rigorously guarantees consistency for all $n$.
