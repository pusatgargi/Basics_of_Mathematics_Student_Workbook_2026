# Problem 8: Sphere

## Problem Statement

Reduce
$$x^2+y^2+z^2-4x+2y-6z-2=0$$
to canonical form. Find the center and radius. Give two points on the sphere and check them in the equation.

## Theoretical Background and Concepts

A **sphere** in three-dimensional space $\mathbb{R}^3$ is the set of all points $P = (x, y, z)$ whose Euclidean distance from a fixed point $S = (x_0, y_0, z_0)$ (the **center**) is equal to a positive constant $R > 0$ (the **radius**). Using the 3D distance formula:
$$\sqrt{(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2} = R.$$
Squaring both sides yields the **canonical equation of a sphere**:
$$(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2.$$

Expanding the three squared binomials produces the **general equation of a sphere**:
$$x^2 + y^2 + z^2 + Ax + By + Cz + D = 0,$$
where $A = -2x_0$, $B = -2y_0$, $C = -2z_0$, and $D = x_0^2 + y_0^2 + z_0^2 - R^2$.

Just as with a circle in $\mathbb{R}^2$, we reduce the general equation of a sphere to canonical form by **completing the square** independently for each of the three variables $x$, $y$, and $z$ using the identity:
$$u^2 + bu = \left(u + \frac{b}{2}\right)^2 - \left(\frac{b}{2}\right)^2.$$
Once reduced to $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$, we can immediately find six simple cardinal points on the sphere by stepping a distance of $\pm R$ from the center $(x_0, y_0, z_0)$ along any of the three coordinate axes:
$$(x_0 \pm R, y_0, z_0), \qquad (x_0, y_0 \pm R, z_0), \qquad (x_0, y_0, z_0 \pm R).$$

## Detailed Step-by-Step Solution

### Step 1: Group Variables by Coordinate
Start with the given equation:
$$x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0.$$
Group the $x$-terms, $y$-terms, and $z$-terms together, and move the constant term $-2$ to the right-hand side:
$$(x^2 - 4x) + (y^2 + 2y) + (z^2 - 6z) = 2.$$

### Step 2: Complete the Square for $x$, $y$, and $z$
1. **For the $x$-terms ($x^2 - 4x$):**
   Half of $-4$ is $-2$, and $(-2)^2 = 4$:
   $$x^2 - 4x = (x^2 - 4x + 4) - 4 = (x - 2)^2 - 4.$$

2. **For the $y$-terms ($y^2 + 2y$):**
   Half of $+2$ is $+1$, and $1^2 = 1$:
   $$y^2 + 2y = (y^2 + 2y + 1) - 1 = (y + 1)^2 - 1.$$

3. **For the $z$-terms ($z^2 - 6z$):**
   Half of $-6$ is $-3$, and $(-3)^2 = 9$:
   $$z^2 - 6z = (z^2 - 6z + 9) - 9 = (z - 3)^2 - 9.$$

### Step 3: Substitute Back and Simplify to Canonical Form
Substitute the three completed squares into the grouped equation from Step 1:
$$\big((x - 2)^2 - 4\big) + \big((y + 1)^2 - 1\big) + \big((z - 3)^2 - 9\big) = 2.$$
Combine the subtracted constants on the left-hand side ($-4 - 1 - 9 = -14$):
$$(x - 2)^2 + (y + 1)^2 + (z - 3)^2 - 14 = 2.$$
Add $14$ to both sides:
$$(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 2 + 14$$
$$(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16.$$
This is the **canonical form** of the sphere.

### Step 4: Identify the Center and Radius
Comparing $(x - 2)^2 + \big(y - (-1)\big)^2 + (z - 3)^2 = 4^2$ with the canonical equation $(x - x_0)^2 + (y - y_0)^2 + (z - z_0)^2 = R^2$:
- **Center of the sphere:** $S = (x_0, y_0, z_0) = (2, -1, 3)$.
- **Radius of the sphere:** $R = \sqrt{16} = 4$.

### Step 5: Find Two Points on the Sphere and Check Them in the Equation
We can obtain simple points on the sphere by starting at the center $S = (2, -1, 3)$ and moving by the radius $R = 4$ along one of the coordinate directions while keeping the other two coordinates equal to the center's coordinates:
- **Point 1 (moving $+4$ along the $x$-axis):**
  $$P_1 = (2 + 4, -1, 3) = (6, -1, 3).$$
- **Point 2 (moving $+4$ along the $y$-axis):**
  $$P_2 = (2, -1 + 4, 3) = (2, 3, 3).$$
*(Other simple cardinal points include $(-2, -1, 3)$, $(2, -5, 3)$, $(2, -1, 7)$, and $(2, -1, -1)$.)*

Let us check both $P_1(6, -1, 3)$ and $P_2(2, 3, 3)$ in both the canonical and original equations:

1. **Checking Point $P_1 = (6, -1, 3)$:**
   - **In the original equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**
     $$\text{LHS} = 6^2 + (-1)^2 + 3^2 - 4(6) + 2(-1) - 6(3) - 2$$
     $$= 36 + 1 + 9 - 24 - 2 - 18 - 2 = 46 - 46 = 0 = \text{RHS}. \quad \checkmark$$
   - **In the canonical equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**
     $$\text{LHS} = (6 - 2)^2 + (-1 + 1)^2 + (3 - 3)^2 = 4^2 + 0^2 + 0^2 = 16 = \text{RHS}. \quad \checkmark$$

2. **Checking Point $P_2 = (2, 3, 3)$:**
   - **In the original equation $x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0$:**
     $$\text{LHS} = 2^2 + 3^2 + 3^2 - 4(2) + 2(3) - 6(3) - 2$$
     $$= 4 + 9 + 9 - 8 + 6 - 18 - 2 = 28 - 28 = 0 = \text{RHS}. \quad \checkmark$$
   - **In the canonical equation $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:**
     $$\text{LHS} = (2 - 2)^2 + (3 + 1)^2 + (3 - 3)^2 = 0^2 + 4^2 + 0^2 = 16 = \text{RHS}. \quad \checkmark$$

## Verification and Consistency Checks

1. **Algebraic Expansion Verification:**
   Expanding the canonical form $(x - 2)^2 + (y + 1)^2 + (z - 3)^2 = 16$:
   $$(x^2 - 4x + 4) + (y^2 + 2y + 1) + (z^2 - 6z + 9) = 16$$
   $$x^2 + y^2 + z^2 - 4x + 2y - 6z + 14 - 16 = 0$$
   $$x^2 + y^2 + z^2 - 4x + 2y - 6z - 2 = 0.$$
   This matches the original equation term for term.

2. **Checking a Third Point Along the $z$-Axis:**
   Consider $P_3 = (2, -1, 3 + 4) = (2, -1, 7)$:
   $$2^2 + (-1)^2 + 7^2 - 4(2) + 2(-1) - 6(7) - 2 = 4 + 1 + 49 - 8 - 2 - 42 - 2 = 54 - 54 = 0. \quad \checkmark$$
