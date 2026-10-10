# Problem 3: Inconsistent System

## Detailed Step-by-Step Solution
The augmented matrix is

$$
\left[\begin{array}{cc|c}1&2&3\\2&4&7\end{array}\right].
$$

Apply $R_2\leftarrow R_2-2R_1$:

$$
\left[\begin{array}{cc|c}1&2&3\\0&0&1\end{array}\right].
$$

The second row represents $0=1$, a contradiction. Equivalently, doubling the first equation would give $2x+4y=6$, not the required $2x+4y=7$.

## Verification
The system has no solution.