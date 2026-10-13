# Problem 6: Parameter and Invertibility

## Problem Statement
For

$$A(t)=\begin{pmatrix}t&1\\2&t\end{pmatrix}$$

find all values of $t$ for which the matrix is not invertible. Explain how your answer is related to the determinant being zero.

## Theoretical Background and Concepts
For any $2\times2$ matrix $\begin{pmatrix}a&b\\c&d\end{pmatrix}$, its determinant is:

$$\det\begin{pmatrix}a&b\\c&d\end{pmatrix} = ad - bc.$$

A matrix being noninvertible means that it has no multiplicative inverse that undoes its action. Under the zero-determinant criterion, a square matrix fails to have an inverse if and only if its determinant is zero ($\det A(t) = 0$). Thus, finding when $A(t)$ is not invertible reduces to solving $\det A(t) = 0$.

## Detailed Step-by-Step Solution
1. **Compute $\det A(t)$:**
   Applying the $2\times2$ determinant rule:
   $$\det A(t) = (t)(t) - (1)(2) = t^2 - 2.$$

2. **Find values of $t$ where $A(t)$ is not invertible:**
   By the zero-determinant criterion, $A(t)$ is not invertible exactly when:
   $$\det A(t) = 0 \implies t^2 - 2 = 0 \implies t^2 = 2.$$
   Taking the square root gives both signs:
   $$t = \sqrt{2}\qquad \text{and}\qquad t = -\sqrt{2}.$$

   Thus, the matrix is not invertible for $t = \pm\sqrt{2}$.

3. **Proportional-row check:**
   When $t^2 = 2$, examine the rows of $A(t)$:
   $$R_1 = (t, 1),\qquad R_2 = (2, t).$$
   Multiplying $R_1$ by $t$:
   $$t \cdot R_1 = t(t, 1) = (t^2, t).$$
   Since $t^2 = 2$, this becomes:
   $$t \cdot R_1 = (2, t) = R_2.$$
   Therefore, $R_2 = t \cdot R_1$ when $t^2 = 2$.
   The second row is an exact scalar multiple of the first row, confirming that the rows are linearly dependent and that the matrix cannot be inverted.

## Verification and Consistency Checks
- For $t = \sqrt{2}$: $\det A(\sqrt{2}) = (\sqrt{2})^2 - 2 = 2 - 2 = 0$.
- For $t = -\sqrt{2}$: $\det A(-\sqrt{2}) = (-\sqrt{2})^2 - 2 = 2 - 2 = 0$.
For any other real value $t \neq \pm\sqrt{2}$, $\det A(t) \neq 0$, so the matrix is invertible.
