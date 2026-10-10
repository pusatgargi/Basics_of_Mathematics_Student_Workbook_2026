# Problem 12: Formula for a Matrix Power

## Problem Statement
Let

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix}.$$
Compute $A^2$, $A^3$, and $A^4$, and use them to formulate a conjecture for $A^n$. Then do not stop after checking one more case: assume the formula is true for $n$, multiply by $A$, and explain why you obtain exactly the formula for $n+1$.

## Theoretical Background and Concepts
A pattern in powers of a matrix can often be guessed from a few examples and then proved by induction.

## Detailed Step-by-Step Solution
Compute the powers:

$$A^2 = \begin{pmatrix}1&1\\0&1\end{pmatrix}^2
=\begin{pmatrix}1&2\\0&1\end{pmatrix}.$$

$$A^3 = A^2A = \begin{pmatrix}1&2\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}
=\begin{pmatrix}1&3\\0&1\end{pmatrix}.$$

$$A^4 = A^3A = \begin{pmatrix}1&3\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}
=\begin{pmatrix}1&4\\0&1\end{pmatrix}.$$

We observe the pattern:

$$A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}.$$

Now assume this formula is true for some $n$:

$$A^n = \begin{pmatrix}1&n\\0&1\end{pmatrix}.$$
Then

$$A^{n+1}=A^nA = \begin{pmatrix}1&n\\0&1\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}
=\begin{pmatrix}1&n+1\\0&1\end{pmatrix}.$$

This is exactly the same formula with $n$ replaced by $n+1$. Therefore the pattern is proved by induction.

## Verification and Consistency Checks
The formula gives:
- $A^2 = \begin{pmatrix}1&2\\0&1\end{pmatrix}$,
- $A^3 = \begin{pmatrix}1&3\\0&1\end{pmatrix}$,
- $A^4 = \begin{pmatrix}1&4\\0&1\end{pmatrix}$,
which matches the explicit calculations. The inductive step confirms the general rule.
