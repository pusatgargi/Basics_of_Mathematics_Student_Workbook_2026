# Problem 11: When Do Matrices Commute?

## Problem Statement
Given

$$A=\begin{pmatrix}1&1\\0&1\end{pmatrix},\qquad B=\begin{pmatrix}a&b\\c&d\end{pmatrix}.$$

Find the conditions on $a,b,c,d$ under which $AB=BA$. Describe the general form of all such matrices $B$.

## Theoretical Background and Concepts
Two square matrices $A$ and $B$ commute if and only if $AB = BA$. Matrix multiplication is carried out using the row-by-column rule. Equating the resulting matrices entry by entry produces a system of linear equations in the parameters $a, b, c, d$.

## Detailed Step-by-Step Solution
1. **Compute $AB$ using the row-by-column rule:**
   $$(AB)_{11} = 1\cdot a + 1\cdot c = a + c,$$
   $$(AB)_{12} = 1\cdot b + 1\cdot d = b + d,$$
   $$(AB)_{21} = 0\cdot a + 1\cdot c = c,$$
   $$(AB)_{22} = 0\cdot b + 1\cdot d = d.$$
   Thus,
   $$AB = \begin{pmatrix}a+c & b+d\\ c & d\end{pmatrix}.$$

2. **Compute $BA$ using the row-by-column rule:**
   $$(BA)_{11} = a\cdot 1 + b\cdot 0 = a,$$
   $$(BA)_{12} = a\cdot 1 + b\cdot 1 = a + b,$$
   $$(BA)_{21} = c\cdot 1 + d\cdot 0 = c,$$
   $$(BA)_{22} = c\cdot 1 + d\cdot 1 = c + d.$$
   Thus,
   $$BA = \begin{pmatrix}a & a+b\\ c & c+d\end{pmatrix}.$$

3. **Set $AB = BA$ and equate corresponding entries:**

   $$\begin{pmatrix}a+c & b+d\\ c & d\end{pmatrix} = \begin{pmatrix}a & a+b\\ c & c+d\end{pmatrix}.$$

   Comparing entries:
   - Row 1, Column 1: $a + c = a \implies c = 0$.
   - Row 1, Column 2: $b + d = a + b \implies d = a$.
   - Row 2, Column 1: $c = c$ (identically satisfied).
   - Row 2, Column 2: $d = c + d \implies c = 0$ (consistent with the first equation).

4. **General form of all commuting matrices:**
   The required conditions are:
   $$c = 0 \qquad \text{and} \qquad d = a.$$
   The entries $a$ and $b$ can be chosen arbitrarily. Therefore, the general form of all matrices $B$ that commute with $A$ is:

   $$B = \begin{pmatrix}a & b \\ 0 & a\end{pmatrix},\quad a, b \in \mathbb{R}.$$

## Verification and Consistency Checks
Substitute the general form $B = \begin{pmatrix}a & b \\ 0 & a\end{pmatrix}$ back into both products:
$$AB = \begin{pmatrix}1&1\\0&1\end{pmatrix}\begin{pmatrix}a&b\\0&a\end{pmatrix} = \begin{pmatrix}a & b+a\\ 0 & a\end{pmatrix},$$
$$BA = \begin{pmatrix}a&b\\0&a\end{pmatrix}\begin{pmatrix}1&1\\0&1\end{pmatrix} = \begin{pmatrix}a & a+b\\ 0 & a\end{pmatrix}.$$
Since $b+a = a+b$, we have $AB = BA$ for all choices of $a$ and $b$. The condition is confirmed.
