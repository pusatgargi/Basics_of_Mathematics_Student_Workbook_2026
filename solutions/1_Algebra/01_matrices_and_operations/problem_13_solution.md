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
The Fibonacci sequence is defined by the recurrence relation $F_0 = 0, F_1 = 1$, and $F_{n+1} = F_n + F_{n-1}$. This recurrence can be modeled linearly as a transition matrix acting on a vector storing two consecutive terms.

## Detailed Step-by-Step Solution
### Row-by-Column Computation of $F^2$
Compute $F^2 = F \cdot F$:

$$F^2 = \begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}1&1\\1&0\end{pmatrix}
=\begin{pmatrix}1\cdot1+1\cdot1 & 1\cdot1+1\cdot0\\1\cdot1+0\cdot1 & 1\cdot1+0\cdot0\end{pmatrix}
=\begin{pmatrix}2&1\\1&1\end{pmatrix}.$$

### Reusable Update Rule for Powers
Notice what happens when an arbitrary row $(u, v)$ is multiplied on the right by $F$:

$$(u, v)\begin{pmatrix}1&1\\1&0\end{pmatrix} = (u\cdot1 + v\cdot1, \; u\cdot1 + v\cdot0) = (u+v, \; u).$$

This means that multiplying any matrix by $F$ updates each row $(u, v)$ to $(u+v, u)$. Each subsequent power $F^{k+1} = F^k F$ is therefore obtained simply by applying $(u, v) \mapsto (u+v, u)$ to the two rows of $F^k$.

- **Transition from $F^2$ to $F^3$:**
  $F^2 = \begin{pmatrix}2&1\\1&1\end{pmatrix}$.
  - Row 1 $(2, 1) \mapsto (2+1, 2) = (3, 2)$.
  - Row 2 $(1, 1) \mapsto (1+1, 1) = (2, 1)$.
  Thus,
  $$F^3 = \begin{pmatrix}3&2\\2&1\end{pmatrix}.$$

- **Computing $F^4$ and $F^5$ using the update rule:**
  - For $F^4 = F^3 F$:
    Row 1 $(3, 2) \mapsto (3+2, 3) = (5, 3)$ and Row 2 $(2, 1) \mapsto (2+1, 2) = (3, 2)$.
    $$F^4 = \begin{pmatrix}5&3\\3&2\end{pmatrix}.$$
  - For $F^5 = F^4 F$:
    Row 1 $(5, 3) \mapsto (5+3, 5) = (8, 5)$ and Row 2 $(3, 2) \mapsto (3+2, 3) = (5, 3)$.
    $$F^5 = \begin{pmatrix}8&5\\5&3\end{pmatrix}.$$

### Relationship to the Fibonacci Sequence
Comparing the entries with the Fibonacci sequence:
$$F_0 = 0,\; F_1 = 1,\; F_2 = 1,\; F_3 = 2,\; F_4 = 3,\; F_5 = 5,\; F_6 = 8,\dots$$
The entries of $F^n$ consist of consecutive Fibonacci numbers:
- $F^2$ contains $2, 1, 1, 1$, which are $F_3, F_2, F_2, F_1$.
- $F^3$ contains $3, 2, 2, 1$, which are $F_4, F_3, F_3, F_2$.
- $F^4$ contains $5, 3, 3, 2$, which are $F_5, F_4, F_4, F_3$.
- $F^5$ contains $8, 5, 5, 3$, which are $F_6, F_5, F_5, F_4$.

### Vector Recurrence Step
Compute the product:

$$F\begin{pmatrix}a\\b\end{pmatrix} = \begin{pmatrix}1&1\\1&0\end{pmatrix}\begin{pmatrix}a\\b\end{pmatrix}
=\begin{pmatrix}1\cdot a + 1\cdot b\\1\cdot a + 0\cdot b\end{pmatrix}
=\begin{pmatrix}a+b\\a\end{pmatrix}.$$

**Interpretation:**
In the vector $\begin{pmatrix}a\\b\end{pmatrix}$, $a$ represents the **more recent term** and $b$ represents the **preceding term**.
Multiplying by $F$ outputs:
1. The new first component $a+b$, which is the sum of the two terms (the next Fibonacci number).
2. The new second component $a$, which retains the more recent term as the preceding term for the subsequent step.
This single matrix multiplication advances the Fibonacci recurrence by exactly one step.

## Verification and Consistency Checks
Starting with the base vector $\begin{pmatrix}F_1\\F_0\end{pmatrix} = \begin{pmatrix}1\\0\end{pmatrix}$:
- $F\begin{pmatrix}1\\0\end{pmatrix} = \begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}F_2\\F_1\end{pmatrix}$,
- $F\begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}2\\1\end{pmatrix} = \begin{pmatrix}F_3\\F_2\end{pmatrix}$,
- $F\begin{pmatrix}2\\1\end{pmatrix} = \begin{pmatrix}3\\2\end{pmatrix} = \begin{pmatrix}F_4\\F_3\end{pmatrix}$.
This matches the columns of the computed powers of $F$, confirming the model.
