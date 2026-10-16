# Problem 13: Intersection of a Sphere and a Plane

## Problem Statement

Given the sphere
$$x^2+y^2+z^2=25$$
and the plane $z=3$, find the equation of the intersection curve and its radius. Then describe what happens for $z=c$ depending on $c$.

## Theoretical Background and Concepts

A **sphere** centered at the origin $(0,0,0)$ with radius $R > 0$ has the canonical equation:
$$x^2 + y^2 + z^2 = R^2.$$
When we intersect this sphere with a horizontal plane $z = c$ (which lies at a signed vertical distance $c$ from the center $(0,0,0)$), a point $(x, y, z)$ lies on the intersection if and only if it satisfies the simultaneous system:
$$\begin{cases} x^2 + y^2 + z^2 = R^2, \\ z = c. \end{cases}$$
Substituting $z = c$ into the sphere's equation gives the 2D equation of the cross-section inside the plane $z = c$:
$$x^2 + y^2 = R^2 - c^2.$$

Geometrically, this algebraic relation is simply the **Pythagorean theorem** applied to the right triangle formed by:
- The sphere's center $O(0,0,0)$,
- The center of the cross-section $C(0,0,c)$ directly on the $Oz$-axis (at distance $|c|$ from $O$),
- Any point $P(x, y, c)$ on the intersection curve (at distance $R$ from $O$ and radial distance $r = \sqrt{x^2 + y^2}$ from $C$).

By the Pythagorean theorem, $r^2 + |c|^2 = R^2 \implies r = \sqrt{R^2 - c^2}$ whenever $|c| \le R$. Depending on how the distance $|c|$ of the plane from the origin compares to the sphere's radius $R$, there are three geometric regimes:
1. **$|c| < R$ (Secant plane):** The plane cuts through the interior of the sphere, producing a **circle** of radius $r(c) = \sqrt{R^2 - c^2} > 0$.
2. **$|c| = R$ (Tangent plane):** The plane just touches the sphere at its north or south pole $(0, 0, \pm R)$, producing a **single point** ($r = 0$).
3. **$|c| > R$ (Exterior plane):** The plane passes completely above or below the sphere, so the intersection is **empty** ($\varnothing$).

## Detailed Step-by-Step Solution

### Step 1: Identify the Sphere's Parameters
The given sphere has the equation:
$$x^2 + y^2 + z^2 = 25 = 5^2.$$
Thus, the sphere is centered at the origin $O = (0, 0, 0)$ and has radius $R = \sqrt{25} = 5$.

---

### Step 2: Find the Intersection Curve and Its Radius for $z = 3$
To find the intersection of the sphere $x^2 + y^2 + z^2 = 25$ and the plane $z = 3$, we substitute $z = 3$ into the sphere equation:
$$x^2 + y^2 + 3^2 = 25$$
$$x^2 + y^2 + 9 = 25$$
$$x^2 + y^2 = 25 - 9$$
$$x^2 + y^2 = 16.$$

Therefore:
- **Equation of the intersection curve:** In three-dimensional space, the curve is described by the system:
  $$\begin{cases} x^2 + y^2 = 16, \\ z = 3. \end{cases}$$
- **Type and Center of the Curve:** It is a **circle** lying in the horizontal plane $z = 3$, centered at the point $(0, 0, 3)$.
- **Radius of the Intersection Curve:** Comparing $x^2 + y^2 = 16$ with $x^2 + y^2 = r^2$:
  $$r^2 = 16 \implies r = \sqrt{16} = 4.$$

*(Geometric note: The sphere radius $R = 5$, plane height $c = 3$, and cross-section radius $r = 4$ form the classic $3\text{–}4\text{–}5$ right triangle: $3^2 + 4^2 = 5^2$.)*

---

### Step 3: Describe What Happens for $z = c$ Depending on $c$
Now substitute a general constant $z = c$ into the sphere equation $x^2 + y^2 + z^2 = 25$:
$$x^2 + y^2 + c^2 = 25 \implies x^2 + y^2 = 25 - c^2.$$

Since $x^2 + y^2 \ge 0$ for all real $x, y$, the nature of the intersection depends on the sign of $25 - c^2$:

1. **Case 1: $|c| < 5$ (i.e., $-5 < c < 5$)**
   - Here $c^2 < 25$, so $25 - c^2 > 0$.
   - The intersection is a **circle** in the plane $z = c$ centered at $(0, 0, c)$ with radius:
     $$r(c) = \sqrt{25 - c^2}.$$
   - **Special subcase $c = 0$ (the equatorial plane):** When $c = 0$, the plane passes directly through the center of the sphere, giving the **great circle** $x^2 + y^2 = 25$ of maximum possible radius $r(0) = \sqrt{25 - 0} = 5 = R$.
   - **As $|c|$ increases from $0$ toward $5$:** The plane moves away from the center toward the poles, and the radius $r(c) = \sqrt{25 - c^2}$ **decreases monotonically** from $5$ down toward $0$. By symmetry ($c^2 = (-c)^2$), the circle at height $z = c$ and the circle at height $z = -c$ have the exact same radius.

2. **Case 2: $|c| = 5$ (i.e., $c = 5$ or $c = -5$)**
   - Here $c^2 = 25$, so $25 - c^2 = 0$, and the equation becomes:
     $$x^2 + y^2 = 0 \implies x = 0 \quad \text{and} \quad y = 0.$$
   - The plane $z = 5$ or $z = -5$ is **tangent** to the sphere. The intersection degenerates into a **single point** (a circle of radius $r(\pm 5) = 0$):
     - For $c = 5$: the **north pole** $(0, 0, 5)$.
     - For $c = -5$: the **south pole** $(0, 0, -5)$.

3. **Case 3: $|c| > 5$ (i.e., $c > 5$ or $c < -5$)**
   - Here $c^2 > 25$, so $25 - c^2 < 0$.
   - Because $x^2 + y^2 \ge 0$ cannot equal a negative number, there are **no real solutions**.
   - The intersection is the **empty set** $\varnothing$ (the plane passes completely above or below the sphere without touching it).

---

### Summary Table of Cross-Sections for $z = c$

| Range of $c$ | Sign of $25 - c^2$ | Geometric Object in Plane $z = c$ | Radius $r(c)$ |
| :--- | :--- | :--- | :--- |
| $c = 0$ | $25 > 0$ | **Great circle** (equator) at $(0,0,0)$ | $r(0) = 5$ (maximum) |
| $0 < |c| < 5$ | $25 - c^2 > 0$ | **Circle** centered at $(0,0,c)$ | $r(c) = \sqrt{25 - c^2} \in (0, 5)$ |
| $c = \pm 5$ | $25 - c^2 = 0$ | **Single point** (pole) at $(0, 0, \pm 5)$ | $r(\pm 5) = 0$ |
| $|c| > 5$ | $25 - c^2 < 0$ | **Empty set** $\varnothing$ (no intersection) | Does not exist |

## Verification and Consistency Checks

1. **Verify Cardinal Points on the Intersection Circle for $z = 3$:**
   In the plane $z = 3$, the circle $x^2 + y^2 = 16$ of radius $r = 4$ contains the points $(4, 0, 3)$, $(-4, 0, 3)$, $(0, 4, 3)$, and $(0, -4, 3)$. Substituting $(\pm 4, 0, 3)$ and $(0, \pm 4, 3)$ into the sphere equation $x^2 + y^2 + z^2 = 25$:
   $$(\pm 4)^2 + 0^2 + 3^2 = 16 + 0 + 9 = 25, \qquad 0^2 + (\pm 4)^2 + 3^2 = 0 + 16 + 9 = 25. \quad \checkmark$$

2. **Verify Another Secant Plane ($z = -4$):**
   For $c = -4$, our formula predicts a circle of radius $r(-4) = \sqrt{25 - (-4)^2} = \sqrt{25 - 16} = \sqrt{9} = 3$. Testing the point $(3, 0, -4)$ in the sphere equation:
   $$3^2 + 0^2 + (-4)^2 = 9 + 0 + 16 = 25. \quad \checkmark$$
