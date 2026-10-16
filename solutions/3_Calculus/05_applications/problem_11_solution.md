# Problem 11: Volume of a Solid of Revolution

## Problem Statement

The region under the graph
$$
y=\sqrt{x},\qquad x\in[0,4],
$$
is rotated about the $x$-axis.

1. Construct the integral describing the volume using the disk method.
2. Compute the volume.
3. Explain where the factor $\pi y^2$ in the integral comes from.

## Theoretical Background and Concepts

1. **Volume via Cross-Sectional Slicing (Cavalieri's Principle)**:
   Suppose a three-dimensional solid lies between the planes perpendicular to the $x$-axis at $x = a$ and $x = b$. If the plane perpendicular to the $x$-axis at abscissa $x \in [a, b]$ intersects the solid in a planar region of cross-sectional area $A(x)$, and $A(x)$ is continuous on $[a, b]$, then the volume $V$ of the solid is the definite integral of the cross-sectional area:
   $$
   V = \int_a^b A(x)\,dx.
   $$

2. **Solids of Revolution and the Disk Method**:
   When the planar region bounded by a non-negative curve $y = f(x) \ge 0$, the $x$-axis ($y = 0$), and the vertical lines $x = a$ and $x = b$ is revolved by a full turn ($2\pi$ radians) about the $x$-axis, every vertical cross-section at coordinate $x$ sweeps out a **circular disk** of radius $R(x) = f(x)$ centered on the $x$-axis. Since the area of a circle of radius $R$ is $\pi R^2$, the cross-sectional area function is:
   $$
   A(x) = \pi \big(R(x)\big)^2 = \pi \big(f(x)\big)^2 = \pi y^2,
   $$
   leading to the disk-method volume integral:
   $$
   V = \int_a^b \pi \big(f(x)\big)^2\,dx = \pi \int_a^b y^2\,dx.
   $$

## Detailed Step-by-Step Solution

### Part 1: Constructing the Integral Using the Disk Method

We consider the planar region bounded above by $y = f(x) = \sqrt{x}$, below by the $x$-axis ($y = 0$), and horizontally by $x \in [0, 4]$.
- When rotated about the $x$-axis, the cross-section at each $x \in [0, 4]$ is a circle of radius:
  $$
  R(x) = y = \sqrt{x}.
  $$
- The area of this circular cross-section is:
  $$
  A(x) = \pi R(x)^2 = \pi \left(\sqrt{x}\right)^2 = \pi x \quad \text{for } x \in [0, 4].
  $$
- Integrating $A(x)$ over $[0, 4]$ gives the volume integral:
  $$
  V = \int_0^4 \pi \left(\sqrt{x}\right)^2 dx = \pi \int_0^4 x\,dx.
  $$

---

### Part 2: Computing the Volume

Evaluating the definite integral constructed in Part 1 using the power rule $\int x\,dx = \frac{x^2}{2} + C$ and the Fundamental Theorem of Calculus:
$$
\begin{aligned}
V &= \pi \int_0^4 x\,dx \\
&= \pi \left[\frac{x^2}{2}\right]_0^4 \\
&= \pi \left(\frac{4^2}{2} - \frac{0^2}{2}\right) \\
&= \pi \left(\frac{16}{2} - 0\right) \\
&= 8\pi \approx 25.1327.
\end{aligned}
$$
Thus, the volume of the solid of revolution (a paraboloid of revolution) is **$V = 8\pi$** cubic units.

---

### Part 3: Explaining Where the Factor $\pi y^2$ in the Integral Comes From

The factor $\pi y^2$ arises directly from the **geometry of rotation** and the **Riemann-sum construction of volume**:

1. **Circular Cross-Sections Created by Rotation**:
   Fix any coordinate $x \in [0, 4]$. Before rotation, the vertical slice of the region at $x$ is a line segment connecting $(x, 0)$ on the axis of rotation to $(x, y)$ on the curve $y = f(x)$, so its length is $y$. When the region is rotated $360^\circ$ about the $x$-axis, the point $(x, 0)$ stays fixed while the endpoint $(x, y)$ traces a circle in the plane perpendicular to the $x$-axis with center $(x, 0)$ and radius $r = y$. The entire vertical segment therefore sweeps out a filled **circle of radius $y$**, whose planar area is:
   $$
   A_{\text{circle}}(x) = \pi r^2 = \pi y^2.
   $$

2. **Infinitesimal Cylindrical Disks ($\Delta V_i \approx \pi y_i^2 \Delta x_i$)**:
   Partition the interval $[0, 4]$ into $n$ small subintervals $[x_{i-1}, x_i]$ of thickness $\Delta x_i = x_i - x_{i-1}$. The slice of the solid between the planes $x = x_{i-1}$ and $x = x_i$ has the shape of a thin circular coin (right circular cylinder or **disk**) with:
   - circular face radius $r_i = y(x_i^*)$,
   - circular face area $A(x_i^*) = \pi \big(y(x_i^*)\big)^2$, and
   - thickness (height) $\Delta x_i$.
   Since the volume of a cylinder is $\text{base area} \times \text{thickness}$, the elementary volume of the $i$-th disk is:
   $$
   \Delta V_i \approx \underbrace{\pi \big(y(x_i^*)\big)^2}_{\text{circular base area}} \cdot \underbrace{\Delta x_i}_{\text{thickness}}.
   $$
   Summing the volumes of all $n$ disks and taking the limit as $\max \Delta x_i \to 0$ yields the definite integral $\int_0^4 \pi y^2\,dx$.

## Verification and Consistency Checks

1. **Comparison with the Enclosing Cylinder and Inscribed Cone**:
   At $x = 4$, the radius of the solid reaches its maximum value $R_{\max} = \sqrt{4} = 2$.
   - The solid is contained strictly inside the right circular cylinder of radius $R_{\max} = 2$ and length $H = 4$, whose volume is:
     $$
     V_{\text{cylinder}} = \pi R_{\max}^2 H = \pi (2^2)(4) = 16\pi.
     $$
   - The solid strictly contains (due to concavity of $y = \sqrt{x}$) the right circular cone of base radius $R_{\max} = 2$ and height $H = 4$, whose volume is:
     $$
     V_{\text{cone}} = \frac{1}{3}\pi R_{\max}^2 H = \frac{16\pi}{3} \approx 5.33\pi.
     $$
   Our computed volume $V = 8\pi$ satisfies $V_{\text{cone}} = \frac{16\pi}{3} < 8\pi < 16\pi = V_{\text{cylinder}}$ and equals exactly half of the circumscribing cylinder's volume ($\frac{1}{2} V_{\text{cylinder}}$), which is Archimedes' classic theorem for a paraboloid of revolution.

2. **Verification via the Cylindrical Shell Method**:
   Integrating with respect to $y \in [0, 2]$, a horizontal strip at height $y$ extends from $x = y^2$ to $x = 4$ (length $4 - y^2$) and rotates around the $x$-axis to form a cylindrical shell of radius $y$ and circumference $2\pi y$:
   $$
   V = \int_0^2 2\pi y (4 - y^2)\,dy = 2\pi \left[2y^2 - \frac{y^4}{4}\right]_0^2 = 2\pi(8 - 4) = 8\pi,
   $$
   confirming the result obtained by the disk method.
