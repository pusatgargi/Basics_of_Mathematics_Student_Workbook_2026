# Problem 14: Supplementary Cross-Sectional Problem — Maximum-Volume Cylinder Inscribed in a Paraboloid of Revolution

## Problem Statement

*(Note: The official problem set `05_applications_en.md` intentionally contains 12 problems. This file provides a supplementary cross-sectional application problem and complete worked solution combining solids of revolution and geometric optimization in the style of the workbook.)*

Consider the planar region bounded by the curve
$$
y = \sqrt{4 - x}, \qquad x \in [0, 4],
$$
and the coordinate axes $x = 0$ and $y = 0$. Rotating this region about the $x$-axis generates a solid paraboloid of revolution of total height $4$.

1. Construct the definite integral using the disk method and compute the total volume $V_{\text{par}}$ of the paraboloid of revolution.
2. A right circular cylinder is inscribed inside this paraboloid with its axis along the $x$-axis, one circular base lying in the plane $x = 0$, and the opposite circular rim touching the paraboloid surface at coordinate $x \in (0, 4)$. Write the volume $V_{\text{cyl}}(x)$ of the inscribed cylinder as a function of $x$, determine its geometric domain, and find the value of $x$ that maximizes $V_{\text{cyl}}(x)$.
3. Compute the maximum fraction $\frac{V_{\text{cyl, max}}}{V_{\text{par}}}$ of the paraboloid's volume that can be occupied by an inscribed cylinder.

## Theoretical Background and Concepts

This problem links **integral calculus (volumes of solids of revolution)** with **differential calculus (geometric optimization)**:

1. **Volume of a Solid of Revolution (Disk Method)**:
   Rotating the region under $y = f(x) \ge 0$ on $[a, b]$ about the $x$-axis yields circular cross-sections of radius $R(x) = f(x)$ and area $A(x) = \pi \big(f(x)\big)^2$, so the total volume of the ambient solid is:
   $$
   V_{\text{par}} = \pi \int_a^b \big(f(x)\big)^2\,dx.
   $$

2. **Optimization of an Inscribed Solid**:
   Because the profile curve $y = \sqrt{4 - x}$ is strictly decreasing on $[0, 4]$, a cylinder extending along the $x$-axis from $0$ to $x$ fits inside the paraboloid if and only if its radius does not exceed the paraboloid radius at its narrower end $x$, so the maximal radius for a given length $x$ is $r(x) = \sqrt{4 - x}$. This reduces the 3D inscription problem to maximizing the single-variable function $V_{\text{cyl}}(x) = \pi \big(r(x)\big)^2 x$ on $(0, 4)$.

## Detailed Step-by-Step Solution

### Part 1: Volume of the Paraboloid of Revolution

For each $x \in [0, 4]$, the cross-section of the paraboloid perpendicular to the $x$-axis is a disk of radius $y = \sqrt{4 - x}$ and area:
$$
A(x) = \pi y^2 = \pi \left(\sqrt{4 - x}\right)^2 = \pi(4 - x).
$$
Integrating $A(x)$ from $x = 0$ to $x = 4$ gives the volume of the paraboloid:
$$
\begin{aligned}
V_{\text{par}} &= \pi \int_0^4 (4 - x)\,dx \\
&= \pi \left[4x - \frac{x^2}{2}\right]_0^4 \\
&= \pi \left(\left(4(4) - \frac{4^2}{2}\right) - (0 - 0)\right) \\
&= \pi (16 - 8) = 8\pi \approx 25.1327.
\end{aligned}
$$

---

### Part 2: Optimizing the Volume of the Inscribed Cylinder

**Step 2a: Express the cylinder volume $V_{\text{cyl}}(x)$ as a function of $x$.**
Let $x$ denote the coordinate along the $x$-axis where the right circular face of the cylinder touches the paraboloid surface.
- The height (length) of the cylinder is $h = x$.
- The radius of the cylinder is determined by the profile curve at $x$: $r(x) = y(x) = \sqrt{4 - x}$.
- The volume of the cylinder is $V_{\text{cyl}} = \pi r^2 h$:
  $$
  V_{\text{cyl}}(x) = \pi \left(\sqrt{4 - x}\right)^2 x = \pi(4 - x)x = \pi\left(4x - x^2\right).
  $$

**Step 2b: Determine the geometric domain.**
For a non-degenerate cylinder, both its length $h = x$ and its radius $r = \sqrt{4 - x}$ must be strictly positive:
$$
\begin{cases}
x > 0, \\
\sqrt{4 - x} > 0 \iff 4 - x > 0 \iff x < 4.
\end{cases}
$$
Hence, the geometric domain is the open interval:
$$
D = (0, 4).
$$

**Step 2c: Differentiate $V_{\text{cyl}}(x)$ and find the global maximum.**
Differentiating $V_{\text{cyl}}(x) = \pi(4x - x^2)$ with respect to $x$:
$$
V'_{\text{cyl}}(x) = \pi(4 - 2x) = 2\pi(2 - x).
$$
Setting $V'_{\text{cyl}}(x) = 0$:
$$
2\pi(2 - x) = 0 \implies x^* = 2 \in (0, 4).
$$
- **First Derivative Test**: For $x \in (0, 2)$, $V'_{\text{cyl}}(x) > 0$ (strictly increasing); for $x \in (2, 4)$, $V'_{\text{cyl}}(x) < 0$ (strictly decreasing).
- **Second Derivative Test**: $V''_{\text{cyl}}(x) = -2\pi < 0$ for all $x \in (0, 4)$.

Thus, $x^* = 2$ gives the unique global maximum of the inscribed cylinder's volume. At $x^* = 2$:
- Optimal cylinder length (height): $h^* = x^* = 2$.
- Optimal cylinder radius: $r^* = \sqrt{4 - 2} = \sqrt{2} \approx 1.4142$.
- Maximum cylinder volume:
  $$
  V_{\text{cyl, max}} = V_{\text{cyl}}(2) = \pi\left(4(2) - 2^2\right) = 4\pi \approx 12.5664.
  $$

---

### Part 3: Maximum Volume Fraction

Taking the ratio of the maximum inscribed cylinder volume to the total paraboloid volume:
$$
\frac{V_{\text{cyl, max}}}{V_{\text{par}}} = \frac{4\pi}{8\pi} = \frac{1}{2} = 50\%.
$$
**Geometric Interpretation**: The largest cylinder that can be inscribed in a paraboloid of revolution extends halfway from the base to the vertex ($x^* = \frac{1}{2} \cdot 4 = 2$) and occupies **exactly half ($50\%$)** of the paraboloid's volume.

## Verification and Consistency Checks

1. **Boundary Degeneracy Checks**:
   - As $x \to 0^+$, the cylinder becomes an infinitely thin disk of radius $2$ and length $0$: $V_{\text{cyl}}(0) = 0$.
   - As $x \to 4^-$, the cylinder becomes an infinitely thin needle of length $4$ and radius $0$: $V_{\text{cyl}}(4) = 0$.

2. **Graphical / Numerical Comparison**:
   - At $x = 1$: $r = \sqrt{3}$, $V_{\text{cyl}}(1) = 3\pi < 4\pi$.
   - At $x = 2$: $r = \sqrt{2}$, $V_{\text{cyl}}(2) = 4\pi$ (maximum).
   - At $x = 3$: $r = 1$, $V_{\text{cyl}}(3) = 3\pi < 4\pi$.
   Notice also that $V_{\text{cyl}}(x) = \pi x(4-x) = A(x) \cdot x$ is simply the area of a rectangle inscribed under the linear cross-sectional area curve $A(x) = \pi(4-x)$ on $[0, 4]$, whose maximum area $\frac{1}{2} V_{\text{par}} = 4\pi$ occurs at the midpoint $x^* = 2$.
