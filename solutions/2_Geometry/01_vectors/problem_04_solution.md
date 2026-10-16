# Problem 4: Dot Product and Perpendicularity

## Problem Statement

For $u=(1,2,-1)$ and $v=(2,-1,3)$ compute $u\cdot v$ and determine whether the vectors are perpendicular. Then find $a$ so that $w=(2,-1,a)$ is perpendicular to $u$, and check the result.

## Theoretical Background and Concepts

1. **Algebraic Definition of the Dot Product (Scalar Product):** For two vectors $u = (u_1, u_2, u_3)$ and $v = (v_1, v_2, v_3)$ in $\mathbb{R}^3$, their dot product $u \cdot v$ is the real number (scalar) obtained by multiplying corresponding components and summing the products:
   $$u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3.$$

2. **Geometric Definition of the Dot Product:** If $\theta \in [0, \pi]$ is the angle between two non-zero vectors $u$ and $v$, then
   $$u \cdot v = \|u\|\,\|v\|\cos\theta.$$

3. **Perpendicularity (Orthogonality) Criterion:** Two non-zero vectors $u$ and $v$ are **perpendicular** (orthogonal, written $u \perp v$) if and only if the angle between them is $\theta = \frac{\pi}{2}$ ($90^\circ$). Since $\cos\left(\frac{\pi}{2}\right) = 0$ and $\|u\|, \|v\| > 0$, it follows immediately that:
   $$u \perp v \iff u \cdot v = 0.$$
   This equivalence works in two ways:
   - As a **test**: compute $u \cdot v$; if the result is $0$, the vectors are perpendicular, and if it is non-zero, they are not.
   - As a **construction tool**: set $u \cdot w = 0$ to form a linear equation and solve for an unknown component so that $w$ is perpendicular to $u$.

## Detailed Step-by-Step Solution

We are given the vectors
$$u = (1, 2, -1) \qquad \text{and} \qquad v = (2, -1, 3).$$

### Step 1: Compute $u \cdot v$ and Determine Whether $u$ and $v$ Are Perpendicular

Using the dot product formula
$$u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3,$$
we substitute the components of $u = (1, 2, -1)$ and $v = (2, -1, 3)$:
$$\begin{aligned}
u \cdot v &= (1)(2) + (2)(-1) + (-1)(3) \\
          &= 2 - 2 - 3 \\
          &= -3.
\end{aligned}$$

**Conclusion on perpendicularity:** Because $u \cdot v = -3 \neq 0$, the vectors $u$ and $v$ are **not perpendicular**. (In fact, since $u \cdot v < 0$, the cosine of the angle between them is negative, meaning the angle between $u$ and $v$ is obtuse.)

### Step 2: Find $a$ So That $w = (2, -1, a)$ Is Perpendicular to $u$

For $w = (2, -1, a)$ to be perpendicular to $u = (1, 2, -1)$, the orthogonality condition requires
$$u \cdot w = 0.$$
Expanding the dot product $u \cdot w = u_1 w_1 + u_2 w_2 + u_3 w_3$:
$$\begin{aligned}
u \cdot w &= (1)(2) + (2)(-1) + (-1)(a) \\
          &= 2 - 2 - a \\
          &= -a.
\end{aligned}$$
Setting $u \cdot w = 0$ gives the linear equation:
$$-a = 0 \implies a = 0.$$
Therefore, the required value of the parameter is $a = 0$, which gives the vector
$$w = (2, -1, 0).$$

### Step 3: Check the Result

We substitute $w = (2, -1, 0)$ back into the dot product with $u = (1, 2, -1)$:
$$\begin{aligned}
u \cdot w &= (1)(2) + (2)(-1) + (-1)(0) \\
          &= 2 - 2 + 0 \\
          &= 0.
\end{aligned}$$
Since $u \cdot w = 0$ and both $u$ and $w$ are non-zero vectors, $w = (2, -1, 0)$ is indeed perpendicular to $u$.

## Verification and Consistency Checks

1. **Pythagorean Theorem Check for $u$ and $w$:** Two vectors $u$ and $w$ are perpendicular if and only if the right triangle they form satisfies the Pythagorean identity $\|u - w\|^2 = \|u\|^2 + \|w\|^2$ (and $\|u + w\|^2 = \|u\|^2 + \|w\|^2$). Let us compute each squared norm independently:
   - $\|u\|^2 = 1^2 + 2^2 + (-1)^2 = 1 + 4 + 1 = 6.$
   - $\|w\|^2 = 2^2 + (-1)^2 + 0^2 = 4 + 1 + 0 = 5.$
   - $u - w = (1 - 2,\; 2 - (-1),\; -1 - 0) = (-1, 3, -1),$ so
     $$\|u - w\|^2 = (-1)^2 + 3^2 + (-1)^2 = 1 + 9 + 1 = 11.$$
   Since $\|u\|^2 + \|w\|^2 = 6 + 5 = 11 = \|u - w\|^2$, the Pythagorean theorem holds, confirming $u \perp w$. $\checkmark$

2. **Law of Cosines Check for $u$ and $v$:** For $u = (1, 2, -1)$ and $v = (2, -1, 3)$, we have $u - v = (-1, 3, -4)$, so:
   - $\|u\|^2 = 6$ and $\|v\|^2 = 2^2 + (-1)^2 + 3^2 = 4 + 1 + 9 = 14.$
   - $\|u - v\|^2 = (-1)^2 + 3^2 + (-4)^2 = 1 + 9 + 16 = 26.$
   By the vector identity $\|u - v\|^2 = \|u\|^2 + \|v\|^2 - 2(u \cdot v)$, we have:
   $$6 + 14 - 2(-3) = 20 + 6 = 26 = \|u - v\|^2. \quad \checkmark$$
   This independently confirms our dot product calculation $u \cdot v = -3 \neq 0$.
