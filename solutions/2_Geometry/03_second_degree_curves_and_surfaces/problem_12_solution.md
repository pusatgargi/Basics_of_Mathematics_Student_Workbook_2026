# Problem 12: Recognizing a Surface from Cross-Sections

## Problem Statement

A certain surface has the following properties:
- the cross-section $z=0$ is a point,
- for $z>0$, the cross-sections $z=\text{const}$ are circles with increasing radius,
- vertical cross-sections through the $Oz$ axis are parabolas.

Propose a simple equation for such a surface and justify your choice.

## Theoretical Background and Concepts

Reconstructing an algebraic equation from geometric cross-sections is the inverse of the method of traces:
1. **Rotational Symmetry (Circles in Horizontal Planes $z = \text{const}$):**
   If every horizontal cross-section $z = c$ is a **circle** centered on the $Oz$-axis, then in each plane $z = c$ the coordinates $(x, y)$ satisfy an equation of the form:
   $$x^2 + y^2 = R(z)^2,$$
   where $R(z) \ge 0$ is the radius of the horizontal circle at height $z$. Notice that $x$ and $y$ appear only through the rotationally invariant combination $r^2 = x^2 + y^2$, where $r = \sqrt{x^2 + y^2}$ is the radial distance from the $Oz$-axis.

2. **Determining the Profile $R(z)$ from Vertical Cross-Sections:**
   Any vertical plane passing through the $Oz$-axis can be parameterized by a fixed angle $\theta$ in cylindrical coordinates ($x = r\cos\theta$, $y = r\sin\theta$), where $r = \pm\sqrt{x^2 + y^2}$ is the signed horizontal coordinate in that vertical plane. In particular:
   - If $R(z)^2 = k z$ ($k > 0$), then $r^2 = kz$, so the vertical cross-sections through the $Oz$-axis are **parabolas** ($z = \frac{1}{k}r^2$), and the surface is a **circular paraboloid**.
   - By contrast, if $R(z)^2 = k^2 z^2$ ($z \ge 0$), then $r = \pm kz$, so the vertical cross-sections would be straight lines (a **cone**), not parabolas.

## Detailed Step-by-Step Solution

### Step 1: Propose a Simple Equation
The simplest second-degree equation satisfying all three given geometric conditions is the **circular paraboloid**:
$$z = x^2 + y^2$$
*(More generally, any equation of the form $z = a(x^2 + y^2)$ with a positive constant $a > 0$, or $x^2 + y^2 = 2pz$ with $p > 0$, satisfies all three conditions; choosing $a = 1$ gives the simplest canonical example $z = x^2 + y^2$.)*

---

### Step 2: Step-by-Step Justification of Every Property

Let us verify how the proposed equation $z = x^2 + y^2$ fulfills each of the three stated geometric requirements and why alternative surfaces are ruled out:

#### Property 1: "The cross-section $z = 0$ is a point."
Substitute $z = 0$ into the equation $z = x^2 + y^2$:
$$x^2 + y^2 = 0.$$
Since $x$ and $y$ are real numbers, $x^2 \ge 0$ and $y^2 \ge 0$. A sum of two non-negative numbers equals zero if and only if both numbers are zero:
$$x^2 = 0 \quad \text{and} \quad y^2 = 0 \implies x = 0 \quad \text{and} \quad y = 0.$$
Therefore, the intersection of the surface with the plane $z = 0$ consists of the **single point** $(0, 0, 0)$ (the vertex of the paraboloid).

#### Property 2: "For $z > 0$, the cross-sections $z = \text{const}$ are circles with increasing radius."
Fix any positive constant height $z = c > 0$. Substituting $z = c$ into $z = x^2 + y^2$ gives:
$$x^2 + y^2 = c \quad \Longleftrightarrow \quad x^2 + y^2 = (\sqrt{c})^2.$$
- In the horizontal plane $z = c$, this is the canonical equation of a **circle** centered at $(0, 0, c)$ on the $Oz$-axis with radius:
  $$R(c) = \sqrt{c}.$$
- Because the square-root function $R(c) = \sqrt{c}$ is strictly increasing for $c > 0$ (if $0 < c_1 < c_2$, then $\sqrt{c_1} < \sqrt{c_2}$), the radius of the circular cross-section **strictly increases** as the height $z = c$ increases.
- Moreover, for $z = c < 0$, $x^2 + y^2 = c < 0$ has no real solutions, which is consistent with the surface starting at $z = 0$ and opening into the upper half-space $z > 0$.

#### Property 3: "Vertical cross-sections through the $Oz$ axis are parabolas."
Consider first the two coordinate vertical planes containing the $Oz$-axis:
- **Plane $x = 0$ ($yz$-plane):** Substituting $x = 0$ into $z = x^2 + y^2$ gives:
  $$z = y^2, \quad x = 0,$$
  which is a **parabola** in the $yz$-plane with vertex at $(0,0,0)$ opening upward along $+Oz$.
- **Plane $y = 0$ ($xz$-plane):** Substituting $y = 0$ into $z = x^2 + y^2$ gives:
  $$z = x^2, \quad y = 0,$$
  which is an identical **parabola** in the $xz$-plane with vertex at $(0,0,0)$ opening upward along $+Oz$.

More generally, **every** vertical plane passing through the $Oz$-axis can be described by rotated horizontal coordinates $(r, z)$ where $x = r\cos\theta$ and $y = r\sin\theta$ for a fixed angle $\theta \in [0, \pi)$, with $r \in (-\infty, \infty)$ measuring signed horizontal distance along the plane's intersection with the $xy$-plane. Substituting this into $z = x^2 + y^2$ yields:
$$z = (r\cos\theta)^2 + (r\sin\theta)^2 = r^2(\cos^2\theta + \sin^2\theta) = r^2.$$
Thus, in **every** vertical plane through the $Oz$-axis, the cross-section has the equation $z = r^2$, which is a **parabola** with vertex at the origin!

*(Note why this third condition is essential: an upper half-cone $z = \sqrt{x^2 + y^2}$ also has a point at $z = 0$ and circles of increasing radius $R(c) = c$ for $z = c > 0$, but its vertical cross-sections through the $Oz$-axis are $z = |r|$—a V-shaped pair of rays—rather than parabolas. Requiring parabolic vertical cross-sections uniquely selects the quadratic relationship $z \propto r^2 = x^2 + y^2$.)*

## Verification and Consistency Checks

Let us check the proposed equation $z = x^2 + y^2$ at concrete heights $z = c$ and along specific vertical planes:

1. **At $z = 0$:**
   $$x^2 + y^2 = 0 \implies (x, y, z) = (0, 0, 0) \quad (\text{1 point, radius } R(0) = 0). \quad \checkmark$$

2. **Increasing radii for $z = 1, 4, 9$:**
   - At $z = 1$: $x^2 + y^2 = 1 \implies$ Circle of radius $R(1) = \sqrt{1} = 1$.
   - At $z = 4$: $x^2 + y^2 = 4 \implies$ Circle of radius $R(4) = \sqrt{4} = 2$.
   - At $z = 9$: $x^2 + y^2 = 9 \implies$ Circle of radius $R(9) = \sqrt{9} = 3$.
   Clearly $0 < 1 < 2 < 3$, confirming circles of increasing radius. $\checkmark$

3. **Diagonal Vertical Plane $y = x$ through the $Oz$-Axis:**
   In the plane $y = x$, the horizontal distance from the $Oz$-axis is $r = \pm\sqrt{x^2 + y^2} = \pm\sqrt{2}x$. Substituting $y = x$ into $z = x^2 + y^2$ gives:
   $$z = x^2 + x^2 = 2x^2 = (\sqrt{2}x)^2 = r^2,$$
   confirming once again a parabola in the diagonal plane $y = x$. $\checkmark$
