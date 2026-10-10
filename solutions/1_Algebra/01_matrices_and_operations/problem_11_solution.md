# Problem 11: When Do Matrices Commute?

## Problem Statement
Given

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}a&b\\c&d\end{pmatrix}.$$
Find the conditions on $a,b,c,d$ under which $AB=BA$. Describe the general form of all such matrices $B$.

## Theoretical Background and Concepts
Two matrices commute if their products in either order are equal. For this problem, we solve the matrix equation $AB=BA$ entry by entry.

## Detailed Step-by-Step Solution
Compute $AB$:

$$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&b\\c&d\end{pmatrix}
=\begin{pmatrix}a+c & b+d\\ c & d\end{pmatrix}.$$

Compute $BA$:

$$BA = \begin{pmatrix}a&b\\c&d\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix}
=\begin{pmatrix}a & a+b\\ c & c+d\end{pmatrix}.$$

Set them equal:

$$\begin{pmatrix}a+c & b+d\\ c & d\end{pmatrix} = \begin{pmatrix}a & a+b\\ c & c+d\end{pmatrix}.$$

Matching entries gives:
- $a+c=a$, so $c=0$
- $b+d=a+b$, so $d=a$
- $c=c$ is automatic
- $d=c+d$ becomes $a=0+a$, which is automatic once $c=0$

Thus the necessary and sufficient conditions are:

$$c=0,\qquad d=a.$$
So all commuting matrices are of the form

$$B = \begin{pmatrix}a&b\\0&a\end{pmatrix},$$
where $a,b$ are arbitrary real numbers.

## Verification and Consistency Checks
Substituting this form into $AB$ and $BA$ yields the same matrix in both orders:

$$AB=BA=\begin{pmatrix}a & a+b\\ 0 & a\end{pmatrix}.$$
Hence the condition is correct.
