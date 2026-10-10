# Problem 13: A Recurrence Written in Matrix Form

## Problem Statement
Let

$$F=\begin{pmatrix}1&1\\1&0\end{pmatrix}.$$
Compute $F^2$, $F^3$, $F^4$, and $F^5$. Compare the numbers obtained with the sequence

$$0,1,1,2,3,5,8,\ldots$$
and describe the relationship you observe. Then compute

$$F\begin{pmatrix}a\\b\end{pmatrix}$$
and explain how this multiplication performs one recurrence step: it creates the sum of two consecutive terms and keeps one of them for the next step.

## Theoretical Background and Concepts
This matrix encodes the Fibonacci recurrence. Each multiplication by $F$ updates a pair of consecutive terms.

## Detailed Step-by-Step Solution
Compute powers:

$$F^2 = \begin{pmatrix}1&1\\1&0\end{pmatrix}^2
=\begin{pmatrix}2&1\\1&1\end{pmatrix}.$$

$$F^3 = F^2F = \begin{pmatrix}2&1\\1&1\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}
=\begin{pmatrix}3&2\\2&1\end{pmatrix}.$$

$$F^4 = F^3F = \begin{pmatrix}3&2\\2&1\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}
=\begin{pmatrix}5&3\\3&2\end{pmatrix}.$$

$$F^5 = F^4F = \begin{pmatrix}5&3\\3&2\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}
=\begin{pmatrix}8&5\\5&3\end{pmatrix}.$$

These numbers are Fibonacci-like: the entries are consecutive Fibonacci numbers. In fact,

$$F^n = \begin{pmatrix}F_{n+1} & F_n \\ F_n & F_{n-1}\end{pmatrix},$$
where $F_0=0$, $F_1=1$.

Now compute:

$$F\begin{pmatrix}a\\b\end{pmatrix}
=\begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}a\\b\end{pmatrix}
=\begin{pmatrix}a+b\\a\end{pmatrix}.$$

This is the recurrence step: if $(a,b)$ are two consecutive terms, then the new pair is $(a+b,a)$. The first component is the next Fibonacci number, and the second component is the previous one, ready for the next step.

## Verification and Consistency Checks
The entries of the powers match the Fibonacci sequence shifted by index. For example, $F^5$ contains $8,5,5,3$, and these are exactly the Fibonacci numbers $F_6,F_5,F_5,F_4$.
