# Problem 6: Projection and Perpendicular Component

## Problem Statement

Find the projection of $u=(4,2)$ onto the direction $v=(1,1)$. Then compute
$$r=u-\operatorname{proj}_v u$$
and verify that $r\cdot v=0$. Explain this result geometrically.

## Theoretical Background and Concepts

1. **Orthogonal Projection of a Vector:** Given a vector $u$ and a non-zero direction vector $v \neq \mathbf{0}$, the **orthogonal projection** of $u$ onto $v$, denoted $\operatorname{proj}_v u$, is the vector lying along the line spanned by $v$ obtained by dropping a perpendicular from the tip of $u$ onto that line:
   $$\operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right) v = \left(\frac{u \cdot v}{\|v\|^2}\right) v.$$
   Here, the scalar coefficient $\lambda = \frac{u \cdot v}{v \cdot v}$ tells us by what factor $v$ must be scaled to reach the foot of the perpendicular.

2. **Perpendicular (Residual) Component:** Subtracting the parallel projection $\operatorname{proj}_v u$ from $u$ leaves the **residual** (or **perpendicular component**) vector:
   $$r = u - \operatorname{proj}_v u.$$
   By construction, $u = \operatorname{proj}_v u + r$, where $\operatorname{proj}_v u$ is parallel to $v$ and $r$ is orthogonal to $v$ ($r \cdot v = 0$).

## Detailed Step-by-Step Solution

We are given the vectors in $\mathbb{R}^2$:
$$u = (4, 2) \qquad \text{and} \qquad v = (1, 1).$$

### Step 1: Find the Projection $\operatorname{proj}_v u$

The formula for the orthogonal projection of $u$ onto the direction of $v$ is:
$$\operatorname{proj}_v u = \left(\frac{u \cdot v}{v \cdot v}\right) v.$$

First, we compute the dot product $u \cdot v = u_1 v_1 + u_2 v_2$:
$$\begin{aligned}
u \cdot v &= (4)(1) + (2)(1) \\
          &= 4 + 2 \\
          &= 6.
\end{aligned}$$

Second, we compute the dot product $v \cdot v = \|v\|^2 = v_1^2 + v_2^2$:
$$\begin{aligned}
v \cdot v &= 1^2 + 1^2 \\
          &= 1 + 1 \\
          &= 2.
\end{aligned}$$

Now substitute $u \cdot v = 6$ and $v \cdot v = 2$ into the projection formula:
$$\begin{aligned}
\operatorname{proj}_v u &= \left(\frac{6}{2}\right)(1, 1) \\
                        &= 3(1, 1) \\
                        &= (3 \cdot 1,\; 3 \cdot 1) \\
                        &= (3, 3).
\end{aligned}$$

### Step 2: Compute the Residual Vector $r = u - \operatorname{proj}_v u$

Using component-wise subtraction $r = (u_1 - (\operatorname{proj}_v u)_1,\; u_2 - (\operatorname{proj}_v u)_2)$ with $u = (4, 2)$ and $\operatorname{proj}_v u = (3, 3)$:
$$\begin{aligned}
r = u - \operatorname{proj}_v u &= (4, 2) - (3, 3) \\
                                &= (4 - 3,\; 2 - 3) \\
                                &= (1, -1).
\end{aligned}$$

### Step 3: Verify That $r \cdot v = 0$

We compute the dot product of $r = (1, -1)$ and $v = (1, 1)$ using $r \cdot v = r_1 v_1 + r_2 v_2$:
$$\begin{aligned}
r \cdot v &= (1)(1) + (-1)(1) \\
          &= 1 - 1 \\
          &= 0.
\end{aligned}$$
Since $r \cdot v = 0$, the vector $r = (1, -1)$ is strictly perpendicular to $v = (1, 1)$.

### Step 4: Explain This Result Geometrically

Imagine shining a light beam perpendicularly onto the line $y = x$ spanned by $v = (1, 1)$:
- The vector $\operatorname{proj}_v u = (3, 3)$ is the **shadow** of $u = (4, 2)$ cast onto the line of $v$. Its tip $(3, 3)$ is the point on the line $y = x$ closest to $(4, 2)$.
- By the tip-to-tail rule of vector addition ($\operatorname{proj}_v u + r = u$), the residual vector $r = u - \operatorname{proj}_v u = (1, -1)$ is the arrow pointing from the tip of the shadow $(3, 3)$ directly to the tip of $u$ at $(4, 2)$.
- Because the shadow was formed by dropping an altitude **perpendicularly** onto the line of $v$, the connecting segment $r$ is the altitude of a right-angled triangle whose base lies along $v$. Consequently, $r$ forms a $90^\circ$ angle with $v$, which algebraically means $r \cdot v = 0$.

```
      y ^
      4 |             /
        |           * Q = (3, 3) = proj_v(u)
      3 |         /   \
        |       /       \  r = (1, -1)
      2 |     /           v
        |   * v = (1,1)    * P = (4, 2) = u
      1 | /
        |/
      0 +----+----+----+----+----> x
        0    1    2    3    4
```

## Verification and Consistency Checks

1. **Vector Reconstruction Check ($\operatorname{proj}_v u + r = u$):** Adding the parallel projection and the perpendicular residual must recover the original vector $u$:
   $$\operatorname{proj}_v u + r = (3, 3) + (1, -1) = (3 + 1,\; 3 + (-1)) = (4, 2) = u. \quad \checkmark$$

2. **Pythagorean Theorem Check ($\|\operatorname{proj}_v u\|^2 + \|r\|^2 = \|u\|^2$):** Because $\operatorname{proj}_v u$ and $r$ are orthogonal legs of a right triangle with hypotenuse $u$, the sum of their squared lengths must equal $\|u\|^2$:
   - $\|\operatorname{proj}_v u\|^2 = 3^2 + 3^2 = 9 + 9 = 18.$
   - $\|r\|^2 = 1^2 + (-1)^2 = 1 + 1 = 2.$
   - $\|u\|^2 = 4^2 + 2^2 = 16 + 4 = 20.$
   Checking the sum:
   $$\|\operatorname{proj}_v u\|^2 + \|r\|^2 = 18 + 2 = 20 = \|u\|^2. \quad \checkmark$$
