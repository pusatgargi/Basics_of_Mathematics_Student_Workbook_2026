# Problem 3: Plane Through a Point with a Given Normal Vector

## Problem Statement

Find the equation of the plane through $P=(1,-2,3)$ and perpendicular to $n=(2,1,-1)$. Check the result by substituting the point $P$ and explain the role of the normal vector.

## Theoretical Background and Concepts

In three-dimensional space $\mathbb{R}^3$, a plane $\Pi$ is uniquely determined by a single fixed point $P_0 = (x_0, y_0, z_0)$ lying on the plane and a non-zero **normal vector** $\vec{n} = (a, b, c)$ that is perpendicular (orthogonal) to the plane.

1. **Geometric Condition for a Plane**:
   Let $X = (x, y, z)$ be an arbitrary point in $\mathbb{R}^3$. The displacement vector from the known point $P_0$ to $X$ is:
   $$\overrightarrow{P_0 X} = X - P_0 = (x - x_0, y - y_0, z - z_0).$$
   The point $X$ lies in the plane $\Pi$ if and only if the segment $P_0 X$ lies completely flat within the plane, which is equivalent to saying that $\overrightarrow{P_0 X}$ is orthogonal to the normal vector $\vec{n}$. Using the dot product criterion for orthogonality, we obtain the **vector equation of a plane**:
   $$\vec{n} \cdot (X - P_0) = 0.$$

2. **Point-Normal Form**:
   Expanding the dot product in coordinates gives the **point-normal form** of the equation of a plane:
   $$a(x - x_0) + b(y - y_0) + c(z - z_0) = 0.$$

3. **General (Scalar) Form**:
   Distributing the coefficients and collecting the constant terms yields the **general form**:
   $$ax + by + cz + d = 0 \quad \text{or} \quad ax + by + cz = D,$$
   where $D = -d = ax_0 + by_0 + cz_0 = \vec{n} \cdot P_0$. Notice that the coefficients $(a, b, c)$ multiplying $(x, y, z)$ in the general equation are always the components of a normal vector to the plane.

## Detailed Step-by-Step Solution

### Step 1: Set Up the Point-Normal Equation

We are given:
- A point on the plane: $P = (x_0, y_0, z_0) = (1, -2, 3)$,
- A normal vector to the plane: $\vec{n} = (a, b, c) = (2, 1, -1)$.

The point-normal equation of a plane is given by the formula:
$$a(x - x_0) + b(y - y_0) + c(z - z_0) = 0.$$

Substituting $a = 2$, $b = 1$, $c = -1$ and $x_0 = 1$, $y_0 = -2$, $z_0 = 3$ into the formula gives:
$$2(x - 1) + 1(y - (-2)) + (-1)(z - 3) = 0,$$
which simplifies to:
$$2(x - 1) + 1(y + 2) - 1(z - 3) = 0.$$

### Step 2: Simplify to General Form

We expand each term and combine the constant terms:
$$\begin{aligned} 2x - 2 + y + 2 - z + 3 &= 0 \\ 2x + y - z + (-2 + 2 + 3) &= 0 \\ 2x + y - z + 3 &= 0. \end{aligned}$$
Moving the constant to the right-hand side gives the equivalent standard form:
$$2x + y - z = -3.$$

### Step 3: Explain the Role of the Normal Vector

In three-dimensional space, why do we describe a plane using a single *perpendicular* vector $\vec{n}$ rather than one direction vector along the plane?

1. **Uniqueness of Orientation in $\mathbb{R}^3$**: A single direction vector lying *inside* a plane is not enough to fix the plane's tilt, because infinitely many planes can rotate around a single line (like pages of a book rotating around its spine). By contrast, once a base point $P$ is fixed, there is **one and only one** two-dimensional flat surface passing through $P$ that is perpendicular to a given vector $\vec{n}$. Thus, the single vector $\vec{n}$ completely locks the orientation (tilt) of the plane in 3D space.
2. **Algebraic Constraint via the Dot Product**: The normal vector reduces the two-dimensional freedom of a plane to a single linear equation. Any vector $\overrightarrow{PX} = (x - 1, y + 2, z - 3)$ lying in the plane must make a $90^\circ$ angle with $\vec{n} = (2, 1, -1)$, which is enforced by the single equation $\vec{n} \cdot \overrightarrow{PX} = 0$.
3. **Direct Reading from the Equation**: In the general equation $2x + y - z + 3 = 0$, the coefficients of $x$, $y$, and $z$ are $(2, 1, -1)$, which immediately gives the normal vector $\vec{n}$. The constant term ($-3$ on the right-hand side of $2x + y - z = -3$) shifts the plane parallel to itself so that it passes through the specific point $P=(1, -2, 3)$.

## Verification and Consistency Checks

1. **Substituting the Point $P = (1, -2, 3)$ into the Plane Equation**:
   We substitute $x = 1$, $y = -2$, and $z = 3$ into $2x + y - z + 3 = 0$:
   $$\text{LHS} = 2(1) + 1(-2) - 1(3) + 3 = 2 - 2 - 3 + 3 = 0 = \text{RHS}.$$
   In the form $2x + y - z = -3$:
   $$\text{LHS} = 2(1) + (-2) - 3 = -3 = \text{RHS}.$$
   Thus, the point $P=(1, -2, 3)$ satisfies the plane equation.

2. **Checking Orthogonality with Another Point on the Plane**:
   Let us pick another point $Q$ that satisfies $2x + y - z = -3$, for example by setting $x = 0$ and $y = 0$, which gives $-z = -3 \implies z = 3$, so $Q = (0, 0, 3)$.
   The vector in the plane from $P$ to $Q$ is:
   $$\overrightarrow{PQ} = Q - P = (0 - 1, 0 - (-2), 3 - 3) = (-1, 2, 0).$$
   Taking the dot product with the normal vector $\vec{n} = (2, 1, -1)$:
   $$\vec{n} \cdot \overrightarrow{PQ} = (2)(-1) + (1)(2) + (-1)(0) = -2 + 2 + 0 = 0.$$
   Since the dot product is zero, $\overrightarrow{PQ}$ is indeed perpendicular to $\vec{n}$.
