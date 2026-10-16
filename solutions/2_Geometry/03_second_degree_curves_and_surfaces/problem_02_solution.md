# Problem 2: Circle by Completing the Square

## Problem Statement

Reduce
$$x^2+y^2-6x+4y-3=0$$
to canonical form. Find the center and radius, then substitute two simple points from the circle into both forms of the equation.

## Theoretical Background and Concepts

A **circle** in the plane is the locus of all points $(x,y)$ that lie at a constant distance $r > 0$ (the **radius**) from a fixed point $S = (x_0, y_0)$ (the **center**). By the Euclidean distance formula, a point $(x,y)$ lies on the circle if and only if
$$\sqrt{(x - x_0)^2 + (y - y_0)^2} = r.$$
Squaring both sides yields the **canonical (or standard) equation of a circle**:
$$(x - x_0)^2 + (y - y_0)^2 = r^2.$$

When the squared binomials are expanded, we obtain the **general equation of a circle**:
$$x^2 + y^2 + Ax + By + C = 0,$$
where $A = -2x_0$, $B = -2y_0$, and $C = x_0^2 + y_0^2 - r^2$.

To convert the general equation back into canonical form, we use the algebraic technique of **completing the square** independently for the $x$-terms and the $y$-terms, based on the identity:
$$u^2 + 2ku = (u + k)^2 - k^2.$$
Specifically, for any expression $u^2 + bu$, we take half of the linear coefficient ($k = b/2$), form the perfect square $(u + b/2)^2$, and subtract $(b/2)^2$ to keep the equality exact. After moving the constant terms to the right-hand side, if the right-hand side equals a positive number $r^2 > 0$, the equation represents a circle with center $(x_0, y_0)$ and radius $r$.

## Detailed Step-by-Step Solution

### Step 1: Group the $x$-terms and $y$-terms Together
We start with the given general equation:
$$x^2 + y^2 - 6x + 4y - 3 = 0.$$
Rearranging the terms to group the $x$-variables together, the $y$-variables together, and moving the constant term $-3$ to the right-hand side gives:
$$(x^2 - 6x) + (y^2 + 4y) = 3.$$

### Step 2: Complete the Square for the $x$-terms
Consider the quadratic expression in $x$:
$$x^2 - 6x.$$
Here, the coefficient of $x$ is $b_x = -6$. Taking half of this coefficient gives:
$$\frac{b_x}{2} = \frac{-6}{2} = -3, \qquad \left(\frac{b_x}{2}\right)^2 = (-3)^2 = 9.$$
Adding and subtracting $9$ (or writing $x^2 - 6x = (x - 3)^2 - 9$):
$$x^2 - 6x = (x^2 - 6x + 9) - 9 = (x - 3)^2 - 9.$$

### Step 3: Complete the Square for the $y$-terms
Consider the quadratic expression in $y$:
$$y^2 + 4y.$$
Here, the coefficient of $y$ is $b_y = 4$. Taking half of this coefficient gives:
$$\frac{b_y}{2} = \frac{4}{2} = 2, \qquad \left(\frac{b_y}{2}\right)^2 = 2^2 = 4.$$
Adding and subtracting $4$ (or writing $y^2 + 4y = (y + 2)^2 - 4$):
$$y^2 + 4y = (y^2 + 4y + 4) - 4 = (y + 2)^2 - 4.$$

### Step 4: Assemble the Canonical Form
Substitute both completed squares back into the grouped equation from Step 1:
$$\big((x - 3)^2 - 9\big) + \big((y + 2)^2 - 4\big) = 3.$$
Combine the subtracted constants on the left-hand side ($-9 - 4 = -13$):
$$(x - 3)^2 + (y + 2)^2 - 13 = 3.$$
Add $13$ to both sides to isolate the sum of squares:
$$(x - 3)^2 + (y + 2)^2 = 3 + 13$$
$$(x - 3)^2 + (y + 2)^2 = 16.$$
This is the **canonical form** of the circle.

### Step 5: Read the Center and Radius
We compare our canonical equation with the standard formula $(x - x_0)^2 + (y - y_0)^2 = r^2$:
$$(x - 3)^2 + \big(y - (-2)\big)^2 = 4^2.$$
From this, we directly read off:
- **Center of the circle:** $S = (x_0, y_0) = (3, -2)$.
- **Radius of the circle:** $r = \sqrt{16} = 4$.

### Step 6: Find Two Simple Points on the Circle and Substitute into Both Equations
The simplest points on a circle with center $(x_0, y_0) = (3, -2)$ and radius $r = 4$ are the four cardinal points obtained by moving $r = 4$ units horizontally or vertically from the center:
- Moving $4$ units right from $(3, -2)$: $P_1 = (3 + 4, -2) = (7, -2)$.
- Moving $4$ units up from $(3, -2)$: $P_2 = (3, -2 + 4) = (3, 2)$.
(Other simple cardinal points are $(3 - 4, -2) = (-1, -2)$ and $(3, -2 - 4) = (3, -6)$.)

Let us substitute $P_1(7, -2)$ and $P_2(3, 2)$ into **both** forms of the equation:

1. **Testing Point $P_1 = (7, -2)$:**
   - **In the canonical form $(x - 3)^2 + (y + 2)^2 = 16$:**
     $$\text{LHS} = (7 - 3)^2 + (-2 + 2)^2 = 4^2 + 0^2 = 16 + 0 = 16 = \text{RHS}. \quad \checkmark$$
   - **In the original general form $x^2 + y^2 - 6x + 4y - 3 = 0$:**
     $$\text{LHS} = 7^2 + (-2)^2 - 6(7) + 4(-2) - 3 = 49 + 4 - 42 - 8 - 3 = 53 - 53 = 0 = \text{RHS}. \quad \checkmark$$

2. **Testing Point $P_2 = (3, 2)$:**
   - **In the canonical form $(x - 3)^2 + (y + 2)^2 = 16$:**
     $$\text{LHS} = (3 - 3)^2 + (2 + 2)^2 = 0^2 + 4^2 = 0 + 16 = 16 = \text{RHS}. \quad \checkmark$$
   - **In the original general form $x^2 + y^2 - 6x + 4y - 3 = 0$:**
     $$\text{LHS} = 3^2 + 2^2 - 6(3) + 4(2) - 3 = 9 + 4 - 18 + 8 - 3 = 21 - 21 = 0 = \text{RHS}. \quad \checkmark$$

## Verification and Consistency Checks

1. **Reverse Algebraic Expansion:**
   Let us expand the canonical form $(x - 3)^2 + (y + 2)^2 = 16$ to confirm it simplifies back to the original equation:
   $$(x^2 - 6x + 9) + (y^2 + 4y + 4) = 16$$
   $$x^2 + y^2 - 6x + 4y + 13 - 16 = 0$$
   $$x^2 + y^2 - 6x + 4y - 3 = 0.$$
   This identically recovers the original equation.

2. **Testing the Remaining Two Cardinal Points:**
   - For $P_3 = (-1, -2)$:
     $$(-1)^2 + (-2)^2 - 6(-1) + 4(-2) - 3 = 1 + 4 + 6 - 8 - 3 = 0. \quad \checkmark$$
   - For $P_4 = (3, -6)$:
     $$3^2 + (-6)^2 - 6(3) + 4(-6) - 3 = 9 + 36 - 18 - 24 - 3 = 0. \quad \checkmark$$
