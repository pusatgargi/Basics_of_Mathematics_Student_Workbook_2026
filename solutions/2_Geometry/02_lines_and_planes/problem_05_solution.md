# Problem 5: Relative Position of Two Lines

## Problem Statement

Analyze the position of
$$L_1:(x,y,z)=(1,1,0)+t(1,2,1),$$
$$L_2:(x,y,z)=(2,0,1)+s(0,1,-1).$$
If they intersect, give the intersection point. If not, determine whether they are parallel or skew. Justify the classification.

## Theoretical Background and Concepts

In three-dimensional space $\mathbb{R}^3$, consider two lines given in parametric form:
$$L_1: \vec{x} = P_1 + t\vec{v}_1 \quad (t \in \mathbb{R}) \qquad \text{and} \qquad L_2: \vec{x} = P_2 + s\vec{v}_2 \quad (s \in \mathbb{R}).$$
Unlike in a two-dimensional plane—where two lines that do not intersect must be parallel—lines in $\mathbb{R}^3$ have an additional possibility because they need not lie in a common plane. Specifically, two lines in $\mathbb{R}^3$ fall into one of four mutually exclusive cases:

1. **Collinear Direction Vectors ($\vec{v}_1 = k\vec{v}_2$ for some $k \neq 0$, or $\vec{v}_1 \times \vec{v}_2 = \vec{0}$)**:
   - **Coincident (Identical)**: The lines share the same direction and have at least one point in common (hence all points in common).
   - **Strictly Parallel**: The lines share the same direction ($\vec{v}_1 \parallel \vec{v}_2$) but have no points in common; they lie in a common plane and never meet.

2. **Non-Collinear Direction Vectors ($\vec{v}_1 \nparallel \vec{v}_2$, i.e., $\vec{v}_1 \times \vec{v}_2 \neq \vec{0}$)**:
   - **Intersecting at a Single Point**: The system of equations $P_1 + t\vec{v}_1 = P_2 + s\vec{v}_2$ has a unique solution $(t, s)$. The two lines meet at one point and together span a common plane.
   - **Skew Lines**: The direction vectors are not parallel ($\vec{v}_1 \nparallel \vec{v}_2$) **and** the system $P_1 + t\vec{v}_1 = P_2 + s\vec{v}_2$ has no solution. Geometrically, skew lines neither intersect nor are parallel; they pass by each other in different planes (they are non-coplanar). Equivalently, the scalar triple product $(P_2 - P_1) \cdot (\vec{v}_1 \times \vec{v}_2) \neq 0$.

## Detailed Step-by-Step Solution

### Step 1: Extract Reference Points and Direction Vectors

From the given equations:
- For line $L_1: (x, y, z) = (1, 1, 0) + t(1, 2, 1)$:
  $$P_1 = (1, 1, 0), \qquad \vec{v}_1 = (1, 2, 1).$$
- For line $L_2: (x, y, z) = (2, 0, 1) + s(0, 1, -1)$:
  $$P_2 = (2, 0, 1), \qquad \vec{v}_2 = (0, 1, -1).$$

### Step 2: Check for Parallelism

Two lines are parallel (or coincident) if and only if their direction vectors $\vec{v}_1$ and $\vec{v}_2$ are proportional, meaning $\vec{v}_1 = k\vec{v}_2$ for some non-zero scalar $k \in \mathbb{R}$:
$$(1, 2, 1) = k(0, 1, -1) = (0, k, -k).$$
Comparing the first ($x$) components gives $1 = 0$, which is impossible.
*(Equivalently, their cross product is $\vec{v}_1 \times \vec{v}_2 = \big((2)(-1)-(1)(1),\; (1)(0)-(1)(-1),\; (1)(1)-(2)(0)\big) = (-3, 1, 1) \neq (0, 0, 0)$.)*

Therefore, $\vec{v}_1$ and $\vec{v}_2$ are linearly independent, so **$L_1$ and $L_2$ are not parallel** (and not identical).

### Step 3: Test for Intersection by Setting Up the Coordinate System

Next, we check whether $L_1$ and $L_2$ intersect at a point by equating their parametric coordinates $(x, y, z)$:
$$(1, 1, 0) + t(1, 2, 1) = (2, 0, 1) + s(0, 1, -1).$$
Writing this vector equation out component by component yields a system of three linear equations in the two unknowns $t$ and $s$:
$$\begin{cases} 1 + t = 2 + 0s & \text{(Equation 1: } x\text{-coordinate)} \\ 1 + 2t = 0 + s & \text{(Equation 2: } y\text{-coordinate)} \\ 0 + t = 1 - s & \text{(Equation 3: } z\text{-coordinate)} \end{cases}$$
which simplifies to:
$$\begin{cases} 1 + t = 2 & (1) \\ 1 + 2t = s & (2) \\ t = 1 - s & (3) \end{cases}$$

### Step 4: Solve the System and Check for Consistency

1. From Equation (1), we immediately solve for $t$:
   $$1 + t = 2 \implies t = 2 - 1 = 1.$$
2. Substituting $t = 1$ into Equation (2) determines the required value of $s$:
   $$s = 1 + 2(1) = 1 + 2 = 3.$$
3. Finally, we substitute $(t, s) = (1, 3)$ into Equation (3) ($t = 1 - s$) to check whether the $z$-coordinates match:
   - Left-hand side of Equation (3):
     $$\text{LHS} = t = 1.$$
   - Right-hand side of Equation (3):
     $$\text{RHS} = 1 - s = 1 - 3 = -2.$$

Since $1 \neq -2$, the third equation is violated! The overdetermined system of equations has **no solution**.

### Step 5: Classification and Justification

- Because the direction vectors $\vec{v}_1 = (1, 2, 1)$ and $\vec{v}_2 = (0, 1, -1)$ are not scalar multiples of each other, the lines are **not parallel**.
- Because the system $P_1 + t\vec{v}_1 = P_2 + s\vec{v}_2$ is inconsistent, the lines **do not intersect** (they have no common point).

Therefore, **$L_1$ and $L_2$ are skew lines**.

## Verification and Consistency Checks

1. **Direct Coordinate Comparison at $(t, s) = (1, 3)$**:
   For $L_1$ at $t = 1$ and $L_2$ at $s = 3$ (the unique parameter pair where both the $x$- and $y$-coordinates agree):
   - On $L_1$ at $t = 1$:
     $$(x_1, y_1, z_1) = (1, 1, 0) + 1(1, 2, 1) = (2, 3, 1).$$
   - On $L_2$ at $s = 3$:
     $$(x_2, y_2, z_2) = (2, 0, 1) + 3(0, 1, -1) = (2, 3, -2).$$
   Notice that both lines pass through $(x, y) = (2, 3)$ in horizontal projection, but at different heights: $L_1$ is at $z_1 = 1$ while $L_2$ is directly below it at $z_2 = -2$. Hence they miss each other in 3D space.

2. **Coplanarity Test via the Scalar Triple Product**:
   Two lines $L_1$ and $L_2$ lie in the same plane if and only if the vector joining their base points, $\overrightarrow{P_1 P_2} = P_2 - P_1$, is orthogonal to $\vec{v}_1 \times \vec{v}_2$.
   - Base-point displacement:
     $$\overrightarrow{P_1 P_2} = (2 - 1,\; 0 - 1,\; 1 - 0) = (1, -1, 1).$$
   - Cross product of direction vectors:
     $$\vec{v}_1 \times \vec{v}_2 = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ 1 & 2 & 1 \\ 0 & 1 & -1 \end{vmatrix} = (-2 - 1,\; 0 - (-1),\; 1 - 0) = (-3, 1, 1).$$
   - Scalar triple product:
     $$\overrightarrow{P_1 P_2} \cdot (\vec{v}_1 \times \vec{v}_2) = (1)(-3) + (-1)(1) + (1)(1) = -3 - 1 + 1 = -3 \neq 0.$$
   Because the scalar triple product is $-3 \neq 0$, the vectors $\overrightarrow{P_1 P_2}$, $\vec{v}_1$, and $\vec{v}_2$ span a three-dimensional parallelepiped of non-zero volume ($|-3| = 3$), confirming that $L_1$ and $L_2$ are non-coplanar and therefore **skew**.
