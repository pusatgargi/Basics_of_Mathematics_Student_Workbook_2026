# Problem 8: Intersection Point of a Line and a Plane

## Problem Statement

Find the intersection point of
$$(x,y,z)=(1,0,2)+t(1,2,-1)$$
with the plane $x+y+z=4$. Check the result by substituting it into both descriptions.

## Theoretical Background and Concepts

To find the intersection of a line $L$ given in parametric form:
$$L: (x, y, z) = (x_0, y_0, z_0) + t(v_x, v_y, v_z), \quad t \in \mathbb{R},$$
and a plane $\Pi$ given in general (scalar) form:
$$\Pi: ax + by + cz = d,$$
we use the method of **parametric substitution**:

1. **Write the line in component parametric form**:
   $$x(t) = x_0 + t v_x, \qquad y(t) = y_0 + t v_y, \qquad z(t) = z_0 + t v_z.$$
2. **Check the non-parallelism condition**:
   If $\vec{n} \cdot \vec{v} = a v_x + b v_y + c v_z \neq 0$, the line is not parallel to the plane and intersects it at a unique point.
3. **Substitute $x(t), y(t), z(t)$ into the plane equation**:
   $$a(x_0 + t v_x) + b(y_0 + t v_y) + c(z_0 + t v_z) = d.$$
   This reduces the three-dimensional geometric intersection problem to a single linear equation in one real unknown $t$.
4. **Solve for $t^*$ and back-substitute**:
   Once the unique parameter value $t = t^*$ is found, substitute $t^*$ back into $(x(t^*), y(t^*), z(t^*))$ to obtain the coordinates of the intersection point.

## Detailed Step-by-Step Solution

### Step 1: Write the Component Parametric Equations of the Line

From the vector equation of the line:
$$(x, y, z) = (1, 0, 2) + t(1, 2, -1), \quad t \in \mathbb{R},$$
we read off the reference point $P_0 = (1, 0, 2)$, the direction vector $\vec{v} = (1, 2, -1)$, and the three coordinate equations:
$$\begin{cases} x = 1 + t, \\ y = 0 + 2t = 2t, \\ z = 2 - t, \end{cases} \quad t \in \mathbb{R}.$$

The plane is $\Pi: x + y + z = 4$, which has normal vector $\vec{n} = (1, 1, 1)$. Note that:
$$\vec{n} \cdot \vec{v} = (1)(1) + (1)(2) + (1)(-1) = 1 + 2 - 1 = 2 \neq 0,$$
which confirms that the line intersects the plane at a single unique point.

### Step 2: Substitute the Parametric Expressions into the Plane Equation

Substituting $x = 1 + t$, $y = 2t$, and $z = 2 - t$ into the plane equation $x + y + z = 4$ gives:
$$(1 + t) + (2t) + (2 - t) = 4.$$

### Step 3: Solve for the Parameter $t$

Grouping the constant terms and the $t$-terms on the left-hand side:
$$\begin{aligned} (1 + 2) + (1 + 2 - 1)t &= 4 \\ 3 + 2t &= 4 \\ 2t &= 4 - 3 \\ 2t &= 1 \\ t &= \frac{1}{2}. \end{aligned}$$
Thus, the line intersects the plane when the parameter takes the value $t = \frac{1}{2}$ (or $0.5$).

### Step 4: Compute the Coordinates of the Intersection Point

We substitute $t = \frac{1}{2}$ back into the parametric equations of the line:
$$\begin{aligned} x\left(\frac{1}{2}\right) &= 1 + \frac{1}{2} = \frac{3}{2}, \\ y\left(\frac{1}{2}\right) &= 2\left(\frac{1}{2}\right) = 1, \\ z\left(\frac{1}{2}\right) &= 2 - \frac{1}{2} = \frac{3}{2}. \end{aligned}$$
Therefore, the intersection point is:
$$I = \left(\frac{3}{2},\; 1,\; \frac{3}{2}\right) = (1.5,\; 1,\; 1.5).$$

## Verification and Consistency Checks

We verify that the point $I = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$ satisfies both the equation of the line and the equation of the plane:

1. **Checking the Line Equation $(x, y, z) = (1, 0, 2) + t(1, 2, -1)$**:
   Setting $(1, 0, 2) + t(1, 2, -1) = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$:
   - First coordinate: $1 + t = \frac{3}{2} \implies t = \frac{3}{2} - 1 = \frac{1}{2}$.
   - Second coordinate: $0 + 2t = 1 \implies 2t = 1 \implies t = \frac{1}{2}$.
   - Third coordinate: $2 - t = \frac{3}{2} \implies t = 2 - \frac{3}{2} = \frac{1}{2}$.
   Since all three coordinates yield the same parameter value $t = \frac{1}{2}$, the point $I = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$ lies on the line.

2. **Checking the Plane Equation $x + y + z = 4$**:
   Substituting $x = \frac{3}{2}$, $y = 1$, and $z = \frac{3}{2}$ into the left-hand side of the plane equation:
   $$x + y + z = \frac{3}{2} + 1 + \frac{3}{2} = \frac{3 + 2 + 3}{2} = \frac{8}{2} = 4.$$
   This matches the right-hand side ($4 = 4$), confirming that $I = \left(\frac{3}{2}, 1, \frac{3}{2}\right)$ also lies on the plane.
