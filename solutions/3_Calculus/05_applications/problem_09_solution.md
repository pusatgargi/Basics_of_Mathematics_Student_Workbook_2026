# Problem 9: Minimizing the Material Used for a Can

## Problem Statement

A closed cylinder has fixed volume $V$.

1. Write the volume constraint.
2. Eliminate one of the variables.
3. Express the surface area as a function of the radius $r$.
4. Find the relation between the height $h$ and the radius $r$ for which the material usage is minimal.

Interpret the obtained relation geometrically.

## Theoretical Background and Concepts

In three-dimensional packaging and structural optimization, minimizing the material required to enclose a given volume $V > 0$ (assuming uniform wall thickness) is equivalent to minimizing the **total surface area** $S$ of the solid subject to the fixed-volume constraint:

1. **Geometry of a Closed Right Circular Cylinder**:
   Let $r > 0$ be the radius of the circular base and $h > 0$ be the height of the cylinder.
   - **Volume**: The base area $\pi r^2$ multiplied by the height $h$:
     $$
     V = \pi r^2 h.
     $$
   - **Total Surface Area**: A closed cylindrical can consists of two circular disks (the bottom base and the top lid), each of area $\pi r^2$, and a lateral curved wall which unrolls into a rectangle of width $2\pi r$ (the circumference of the base) and height $h$:
     $$
     S(r, h) = 2\pi r^2 + 2\pi r h.
     $$

2. **Reduction to a Single-Variable Unconstrained Problem**:
   Because $V$ is a fixed positive constant, the constraint $\pi r^2 h = V$ uniquely determines $h$ as a function of $r$ on the open domain $r \in (0, \infty)$. Substituting $h(r)$ into $S(r, h)$ produces a single-variable objective function $S(r)$ on $(0, \infty)$ whose global minimum can be found via first and second derivative analysis.

## Detailed Step-by-Step Solution

### Part 1: Writing the Volume Constraint

Let $r > 0$ denote the base radius and $h > 0$ denote the height of the closed cylinder. For a fixed positive volume $V > 0$, the volume constraint is:
$$
\pi r^2 h = V.
$$

---

### Part 2: Eliminating One of the Variables

Since $r > 0$, we can divide both sides of the volume constraint by $\pi r^2$ to express the height $h$ explicitly in terms of the radius $r$:
$$
h = \frac{V}{\pi r^2}.
$$

---

### Part 3: Expressing the Surface Area as a Function of the Radius $r$

The total surface area $S$ of a closed cylinder (two circular ends plus the lateral wall) is:
$$
S = 2\pi r^2 + 2\pi r h.
$$
Substituting $h = \frac{V}{\pi r^2}$ from Part 2 into the surface area formula:
$$
\begin{aligned}
S(r) &= 2\pi r^2 + 2\pi r \left(\frac{V}{\pi r^2}\right) \\
&= 2\pi r^2 + \frac{2V}{r}, \qquad r \in (0, \infty).
\end{aligned}
$$

---

### Part 4: Finding the Optimal Relation Between $h$ and $r$

**Step 4a: Differentiate $S(r)$ with respect to $r$.**
Writing $S(r) = 2\pi r^2 + 2V r^{-1}$ and differentiating on $(0, \infty)$:
$$
\begin{aligned}
S'(r) &= \frac{d}{dr}\left(2\pi r^2 + 2V r^{-1}\right) \\
&= 4\pi r - \frac{2V}{r^2} \\
&= \frac{4\pi r^3 - 2V}{r^2}.
\end{aligned}
$$

**Step 4b: Find the stationary point.**
Since $r > 0$, $S'(r) = 0$ if and only if the numerator vanishes:
$$
4\pi r^3 - 2V = 0 \iff 4\pi r^3 = 2V \iff 2\pi r^3 = V.
$$
Solving for the critical radius $r^*$ gives:
$$
r^* = \sqrt[3]{\frac{V}{2\pi}}.
$$

**Step 4c: Determine the relation between $h$ and $r$.**
To find the relationship between the height $h$ and the radius $r$ at the optimum without needing the numerical value of $V$, we substitute the volume formula $V = \pi r^2 h$ directly into the optimality condition $2\pi r^3 = V$:
$$
2\pi r^3 = \pi r^2 h.
$$
Dividing both sides by $\pi r^2 > 0$ yields the fundamental relation:
$$
h = 2r.
$$
*(Equivalently, the optimal height is $h^* = 2r^* = 2\sqrt[3]{\frac{V}{2\pi}} = \sqrt[3]{\frac{4V}{\pi}}$.)*

**Step 4d: Justify that $h = 2r$ gives the global minimum of material usage.**
- **First Derivative Test**:
  Since $S'(r) = \frac{2(2\pi r^3 - V)}{r^2}$:
  - For $r \in (0, r^*)$, we have $2\pi r^3 < V \implies S'(r) < 0$, so $S(r)$ is strictly decreasing.
  - For $r \in (r^*, \infty)$, we have $2\pi r^3 > V \implies S'(r) > 0$, so $S(r)$ is strictly increasing.
  Therefore, $r^*$ is the unique global minimum of $S(r)$ on $(0, \infty)$.
- **Second Derivative Test**:
  $$
  S''(r) = \frac{d}{dr}\left(4\pi r - 2V r^{-2}\right) = 4\pi + \frac{4V}{r^3} > 0 \quad \text{for all } r > 0.
  $$
  At $r^* = (V/(2\pi))^{1/3}$, $S''(r^*) = 4\pi + 8\pi = 12\pi > 0$, confirming a strict global minimum.

---

### Geometric Interpretation of the Result $h = 2r$

Since the diameter of the circular base is $d = 2r$, the optimality relation $h = 2r$ means that:
1. **Height Equals Diameter ($h = d$)**: The most material-efficient closed cylindrical can has a height exactly equal to the diameter of its base.
2. **Square Axial Cross-Section**: If we slice the cylinder with a plane passing through its central vertical axis of symmetry, the resulting cross-section is a rectangle of width $d = 2r$ and height $h$. When $h = 2r$, this axial cross-section is a **square** of side $2r \times 2r$.
3. **Circumscribed Sphere Property**: A cylinder with $h = 2r$ can be circumscribed tightly around a sphere of radius $r$ touching both circular ends and the lateral wall, making it the most "isotropic" (sphere-like) cylinder possible.

## Verification and Consistency Checks

1. **Boundary / Limiting Behavior**:
   - As $r \to 0^+$ (an extremely thin, tall tube with $h \to \infty$), $S(r) \sim \frac{2V}{r} \to +\infty$.
   - As $r \to +\infty$ (an extremely wide, flat disk with $h \to 0^+$), $S(r) \sim 2\pi r^2 \to +\infty$.
   Since $S(r) \to +\infty$ at both ends of $(0, \infty)$, a global minimum in the interior is guaranteed.

2. **Area Partition Check / AM-GM Inequality**:
   At the optimum $h = 2r$, the area of the two circular lids is $S_{\text{ends}} = 2\pi r^2$ and the lateral area is $S_{\text{lat}} = 2\pi r(2r) = 4\pi r^2 = 2 S_{\text{ends}}$ (total area $S_{\min} = 6\pi (r^*)^2 = 3\sqrt[3]{2\pi V^2}$).
   By the three-term AM-GM inequality applied to $S(r) = 2\pi r^2 + \frac{V}{r} + \frac{V}{r}$:
   $$
   S(r) = 2\pi r^2 + \frac{V}{r} + \frac{V}{r} \ge 3\sqrt[3]{(2\pi r^2)\left(\frac{V}{r}\right)\left(\frac{V}{r}\right)} = 3\sqrt[3]{2\pi V^2},
   $$
   with equality if and only if $2\pi r^2 = \frac{V}{r} \iff 2\pi r^3 = V \iff h = 2r$.
