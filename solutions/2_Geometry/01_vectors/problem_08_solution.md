# Problem 8: Linear Combination and Checking the Result

## Problem Statement

Check whether $w=(5,1)$ can be written as
$$w=au+bv,$$
where $u=(1,1)$ and $v=(2,-1)$. If so, find $a,b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

## Theoretical Background and Concepts

1. **Linear Combination:** Given vectors $u$ and $v$ in $\mathbb{R}^2$ and scalars $a, b \in \mathbb{R}$, the vector
   $$w = au + bv$$
   is called a **linear combination** of $u$ and $v$ with weights (or coordinates) $a$ and $b$.

2. **Equivalence to a System of Linear Equations:** Writing out the vector equation $au + bv = w$ in components for $u = (u_1, u_2)$, $v = (v_1, v_2)$, and $w = (w_1, w_2)$ gives
   $$(au_1 + bv_1,\; au_2 + bv_2) = (w_1, w_2),$$
   which is equivalent to a system of two linear equations in the two unknowns $a$ and $b$:
   $$\begin{cases} u_1 a + v_1 b = w_1, \\ u_2 a + v_2 b = w_2. \end{cases}$$

3. **Span and Basis in $\mathbb{R}^2$:** If two vectors $u, v \in \mathbb{R}^2$ are **not collinear** (they do not lie on the same line through the origin, so $u_1 v_2 - u_2 v_1 \neq 0$), then they are linearly independent and form a **basis** of $\mathbb{R}^2$. Geometrically, they **span** the entire plane $\mathbb{R}^2$, meaning every vector $w \in \mathbb{R}^2$ can be expressed uniquely as $w = au + bv$.

## Detailed Step-by-Step Solution

We are given the vectors
$$u = (1, 1), \qquad v = (2, -1), \qquad w = (5, 1).$$

### Step 1: Set Up the System of Linear Equations for $a$ and $b$

We substitute the components of $u, v, w$ into the vector equation $au + bv = w$:
$$a(1, 1) + b(2, -1) = (5, 1).$$
Performing the scalar multiplications and vector addition on the left-hand side:
$$(a, a) + (2b, -b) = (5, 1) \implies (a + 2b,\; a - b) = (5, 1).$$
Two vectors are equal if and only if their corresponding components are equal. Equating the first and second components gives the linear system:
$$\begin{cases}
a + 2b = 5 & \text{(Equation 1)} \\
a - b = 1  & \text{(Equation 2)}
\end{cases}$$

### Step 2: Solve for $a$ and $b$

We eliminate $a$ by subtracting Equation 2 from Equation 1:
$$\begin{aligned}
(a + 2b) - (a - b) &= 5 - 1 \\
a + 2b - a + b &= 4 \\
3b &= 4 \\
b &= \frac{4}{3}.
\end{aligned}$$

Next, we substitute $b = \frac{4}{3}$ into Equation 2 ($a - b = 1$) to find $a$:
$$\begin{aligned}
a &= 1 + b \\
  &= 1 + \frac{4}{3} \\
  &= \frac{3}{3} + \frac{4}{3} \\
  &= \frac{7}{3}.
\end{aligned}$$

Because the system has a unique solution, **yes**, $w = (5, 1)$ can be written as $w = au + bv$ with coefficients
$$a = \frac{7}{3} \qquad \text{and} \qquad b = \frac{4}{3}.$$

### Step 3: Reconstruct $w$ from $a$ and $b$

We substitute $a = \frac{7}{3}$ and $b = \frac{4}{3}$ back into the linear combination $au + bv$:
$$\begin{aligned}
au + bv &= \frac{7}{3}(1, 1) + \frac{4}{3}(2, -1) \\
        &= \left(\frac{7}{3} \cdot 1,\; \frac{7}{3} \cdot 1\right) + \left(\frac{4}{3} \cdot 2,\; \frac{4}{3} \cdot (-1)\right) \\
        &= \left(\frac{7}{3},\; \frac{7}{3}\right) + \left(\frac{8}{3},\; -\frac{4}{3}\right) \\
        &= \left(\frac{7}{3} + \frac{8}{3},\; \frac{7}{3} + \left(-\frac{4}{3}\right)\right) \\
        &= \left(\frac{15}{3},\; \frac{3}{3}\right) \\
        &= (5, 1) = w.
\end{aligned}$$
This explicitly confirms that the linear combination reconstructs $w = (5, 1)$.

### Step 4: Explain the Geometric Meaning of the Existence of Such Coefficients

Geometrically, the existence (and uniqueness) of the coefficients $a = \frac{7}{3}$ and $b = \frac{4}{3}$ means the following:
- The vectors $u = (1, 1)$ and $v = (2, -1)$ point along **two distinct, non-parallel lines** through the origin (one with slope $1$, the other with slope $-\frac{1}{2}$). Because they are not collinear, they form a **coordinate grid (basis)** covering the entire plane $\mathbb{R}^2$.
- Reaching the target point $w = (5, 1)$ from the origin $(0, 0)$ can be accomplished by traveling purely along the two allowed directions $u$ and $v$: first taking a step of $\frac{7}{3}$ times $u$ to reach $\left(\frac{7}{3}, \frac{7}{3}\right)$, and from there taking a step of $\frac{4}{3}$ times $v$, which moves by $\left(\frac{8}{3}, -\frac{4}{3}\right)$ to land at $(5, 1)$.
- Equivalently, by the parallelogram rule, $w = (5, 1)$ is the diagonal of a parallelogram whose adjacent sides lie along the lines of $u$ and $v$ with scaled side vectors $\frac{7}{3}u = \left(\frac{7}{3}, \frac{7}{3}\right)$ and $\frac{4}{3}v = \left(\frac{8}{3}, -\frac{4}{3}\right)$.

```
      y ^
    7/3 |       * (7/3)u = (7/3, 7/3)
      2 |      / .
        |     /    .  +(4/3)v = (8/3, -4/3)
      1 |    * u    .       * w = (5, 1)
        |   /         .   /
      0 +--+----+----+--*-+----+----> x
        |   \             .
     -1 |    * v = (2,-1)   * (4/3)v = (8/3, -4/3)
```

## Verification and Consistency Checks

1. **Determinant and Cramer's Rule Verification:** The $2 \times 2$ matrix whose columns are $u$ and $v$ is $M = \begin{bmatrix} 1 & 2 \\ 1 & -1 \end{bmatrix}$. Its determinant is:
   $$\det(M) = (1)(-1) - (2)(1) = -1 - 2 = -3 \neq 0.$$
   Because $\det(M) \neq 0$, $u$ and $v$ are linearly independent and span $\mathbb{R}^2$. By Cramer's Rule:
   $$a = \frac{\det\begin{bmatrix} 5 & 2 \\ 1 & -1 \end{bmatrix}}{\det(M)} = \frac{(5)(-1) - (2)(1)}{-3} = \frac{-5 - 2}{-3} = \frac{-7}{-3} = \frac{7}{3}, \quad \checkmark$$
   $$b = \frac{\det\begin{bmatrix} 1 & 5 \\ 1 & 1 \end{bmatrix}}{\det(M)} = \frac{(1)(1) - (5)(1)}{-3} = \frac{1 - 5}{-3} = \frac{-4}{-3} = \frac{4}{3}. \quad \checkmark$$

2. **Individual Equation Substitution Check:**
   - Equation 1: $a + 2b = \frac{7}{3} + 2\left(\frac{4}{3}\right) = \frac{7 + 8}{3} = \frac{15}{3} = 5.$ $\checkmark$
   - Equation 2: $a - b = \frac{7}{3} - \frac{4}{3} = \frac{3}{3} = 1.$ $\checkmark$
