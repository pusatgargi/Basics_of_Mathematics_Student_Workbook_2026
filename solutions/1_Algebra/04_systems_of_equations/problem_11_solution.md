# Problem 11: A Parameter in a System of Three Equations

## Problem Statement
Analyze the number of solutions depending on $t$:

$$\begin{cases}x+y+z=1,\\x+ty+z=2,\\x+y+tz=3.\end{cases}$$

Use elimination and separately analyze the parameter values for which a standard calculation step ceases to be valid.

## Theoretical Background and Concepts
When performing Gaussian elimination on a system with a parameter, dividing by an expression involving the parameter is valid only when that expression is non-zero. Values where the expression vanishes are exceptional cases that must be analyzed separately.

## Detailed Step-by-Step Solution
1. **Set up augmented matrix $[A \mid b]$:**
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 1 & t & 1 & 2 \\ 1 & 1 & t & 3 \end{array}\right]$$

2. **Elimination using Row 1:**
   Subtract row 1 from row 2 and row 3:
   - $R_2 \leftarrow R_2 - R_1$: $(0,\; t - 1,\; 0 \mid 1)$
   - $R_3 \leftarrow R_3 - R_1$: $(0,\; 0,\; t - 1 \mid 2)$

   The augmented matrix becomes:
   $$\left[\begin{array}{ccc|c} 1 & 1 & 1 & 1 \\ 0 & t - 1 & 0 & 1 \\ 0 & 0 & t - 1 & 2 \end{array}\right]$$

3. **Analysis of the exceptional value $t = 1$:**
   The pivot coefficient is $t - 1$, so division by $t - 1$ is invalid when $t = 1$.
   Substituting $t = 1$ into row 2:
   $$0 \cdot y = 1 \implies 0 = 1.$$
   This is an explicit contradiction.
   Therefore, for **$t = 1$**, the system is inconsistent and has **no solution**.

4. **Analysis for $t \neq 1$:**
   When $t \neq 1$, $t - 1 \neq 0$, so we can divide by $t - 1$:
   - From row 2: $y = \frac{1}{t - 1}$.
   - From row 3: $z = \frac{2}{t - 1}$.
   - From row 1:
     $$x = 1 - y - z = 1 - \frac{1}{t - 1} - \frac{2}{t - 1} = 1 - \frac{3}{t - 1} = \frac{t - 4}{t - 1}.$$

   Thus, for every **$t \neq 1$**, the system has **exactly one solution**:
   $$(x, y, z) = \left(\frac{t - 4}{t - 1},\; \frac{1}{t - 1},\; \frac{2}{t - 1}\right).$$

## Verification and Consistency Checks
- For $t \neq 1$, substitute into equation 2:
  $$x + ty + z = \frac{t - 4}{t - 1} + \frac{t}{t - 1} + \frac{2}{t - 1} = \frac{2t - 2}{t - 1} = 2.$$
  This matches the right-hand side $2$.
- For $t = 1$, equations 1 and 2 become $x+y+z=1$ and $x+y+z=2$, which immediately yields the contradiction $1 = 2$.
