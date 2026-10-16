# Problem 1: Line Through Two Points

## Problem Statement

Find the equation of the line through $A=(1,2)$ and $B=(4,-1)$ in parametric and general form. Identify a direction vector and an example of a normal vector. Check that both points satisfy the equation you obtain.

## Theoretical Background and Concepts

In the two-dimensional Cartesian plane $\mathbb{R}^2$, a straight line is completely determined by two distinct points, or equivalently by one point and a vector specifying either the line's direction or a direction perpendicular to it.

1. **Direction Vector**: Given two distinct points $A=(x_A, y_A)$ and $B=(x_B, y_B)$ on a line, the displacement vector from $A$ to $B$,
   $$\vec{v} = \overrightarrow{AB} = B - A = (x_B - x_A, y_B - y_A),$$
   points along the line and is called a **direction vector** of the line. Any non-zero scalar multiple $k\vec{v}$ ($k \neq 0$) is also a valid direction vector for the same line.

2. **Parametric Form of a Line**: A point $X=(x,y)$ lies on the line passing through $A=(x_A, y_A)$ with direction vector $\vec{v}=(v_x, v_y)$ if and only if the vector $\overrightarrow{AX}$ is a scalar multiple of $\vec{v}$. Introducing a real parameter $t \in \mathbb{R}$, we write the vector/parametric equation:
   $$(x, y) = (x_A, y_A) + t(v_x, v_y), \quad t \in \mathbb{R},$$
   or in component form:
   $$\begin{cases} x = x_A + t v_x, \\ y = y_A + t v_y, \end{cases} \quad t \in \mathbb{R}.$$

3. **Normal Vector**: A non-zero vector $\vec{n} = (a, b)$ is called a **normal vector** to the line if it is orthogonal (perpendicular) to the line's direction vector $\vec{v} = (v_x, v_y)$. Orthogonality is characterized by the vanishing of the dot product:
   $$\vec{n} \cdot \vec{v} = a v_x + b v_y = 0.$$
   In $\mathbb{R}^2$, given $\vec{v} = (v_x, v_y)$, we can immediately construct a normal vector by swapping the components and negating one of them: $\vec{n} = (-v_y, v_x)$ or $\vec{n} = (v_y, -v_x)$.

4. **General (Implicit) Form of a Line**: A point $X=(x,y)$ lies on the line through $A=(x_A, y_A)$ with normal vector $\vec{n}=(a,b)$ if and only if $\overrightarrow{AX}$ is orthogonal to $\vec{n}$:
   $$\vec{n} \cdot (X - A) = a(x - x_A) + b(y - y_A) = 0.$$
   Expanding and collecting constants yields the **general form** of the equation of a line:
   $$ax + by + c = 0 \quad (\text{or } ax + by = d),$$
   where the coefficients $(a,b)$ of $x$ and $y$ directly form a normal vector to the line.

## Detailed Step-by-Step Solution

### Step 1: Identify a Direction Vector

We are given the two points $A = (1, 2)$ and $B = (4, -1)$. To find a direction vector $\vec{v}$ of the line passing through $A$ and $B$, we compute the displacement vector $\overrightarrow{AB}$ by subtracting the coordinates of $A$ from the coordinates of $B$:
$$\vec{v} = \overrightarrow{AB} = B - A = (x_B - x_A, y_B - y_A).$$
Substituting the given coordinates:
$$\vec{v} = (4 - 1, -1 - 2) = (3, -3).$$
Since any non-zero scalar multiple of a direction vector also directs the same line, we can optionally factor out $3$ to obtain a simpler, parallel direction vector:
$$\vec{u} = \frac{1}{3}\vec{v} = (1, -1).$$
Both $\vec{v} = (3, -3)$ and $\vec{u} = (1, -1)$ are valid direction vectors for the line.

### Step 2: Find the Parametric Form of the Line

Using the starting point $A = (1, 2)$ and the direction vector $\vec{v} = (3, -3)$, we substitute into the parametric formula $(x, y) = A + t\vec{v}$:
$$(x, y) = (1, 2) + t(3, -3), \quad t \in \mathbb{R}.$$
Writing this out in coordinate system form gives:
$$\begin{cases} x(t) = 1 + 3t, \\ y(t) = 2 - 3t, \end{cases} \quad t \in \mathbb{R}.$$

*(Note: If we instead use the simplified direction vector $\vec{u} = (1, -1)$ with parameter $s \in \mathbb{R}$, the equivalent parametric form is $(x, y) = (1, 2) + s(1, -1)$, or $x = 1 + s$, $y = 2 - s$.)*

### Step 3: Identify an Example of a Normal Vector

A normal vector $\vec{n} = (a, b)$ must be perpendicular to the direction vector $\vec{v} = (3, -3)$, meaning it must satisfy:
$$\vec{n} \cdot \vec{v} = 3a - 3b = 0.$$
Using the standard 2D perpendicular construction $\vec{n} = (-v_y, v_x)$ on $\vec{v} = (3, -3)$, we obtain:
$$\vec{n}_1 = (-(-3), 3) = (3, 3).$$
Dividing by $3$ gives the simplest integer normal vector:
$$\vec{n} = (1, 1).$$
Let us check orthogonality via the dot product:
$$\vec{n} \cdot \vec{v} = (1)(3) + (1)(-3) = 3 - 3 = 0.$$
Thus, $\vec{n} = (1, 1)$ (or $\vec{n}_1 = (3, 3)$) is a normal vector to the line.

### Step 4: Find the General Form of the Line

We can obtain the general form in two equivalent ways:

**Method 1 (Using the normal vector and point $A$):**
Using the point-normal formula $a(x - x_A) + b(y - y_A) = 0$ with $\vec{n} = (1, 1)$ and $A = (1, 2)$:
$$1(x - 1) + 1(y - 2) = 0.$$
Expanding the parentheses and combining constant terms:
$$x - 1 + y - 2 = 0 \implies x + y - 3 = 0 \quad (\text{or } x + y = 3).$$
*(If we used $\vec{n}_1 = (3, 3)$, we would get $3x + 3y - 9 = 0$, which simplifies to $x + y - 3 = 0$ upon dividing by $3$.)*

**Method 2 (Eliminating the parameter $t$ from the parametric equations):**
From the parametric system:
$$\begin{cases} x = 1 + 3t, \\ y = 2 - 3t, \end{cases}$$
we add the two equations together to eliminate $3t$:
$$x + y = (1 + 3t) + (2 - 3t) = 3 \implies x + y - 3 = 0.$$

Both methods yield the exact same general equation:
$$x + y - 3 = 0.$$

## Verification and Consistency Checks

We now verify that both given points $A = (1, 2)$ and $B = (4, -1)$ satisfy both the parametric and general equations of the line.

1. **Checking the General Form ($x + y - 3 = 0$)**:
   - **Point $A = (1, 2)$**: Substitute $x = 1$ and $y = 2$ into the left-hand side:
     $$1 + 2 - 3 = 3 - 3 = 0.$$
     The equation holds ($0 = 0$).
   - **Point $B = (4, -1)$**: Substitute $x = 4$ and $y = -1$ into the left-hand side:
     $$4 + (-1) - 3 = 3 - 3 = 0.$$
     The equation holds ($0 = 0$).

2. **Checking the Parametric Form ($x = 1 + 3t,\; y = 2 - 3t$)**:
   - **Point $A = (1, 2)$**: Setting $t = 0$ gives:
     $$x = 1 + 3(0) = 1, \qquad y = 2 - 3(0) = 2,$$
     which recovers $A = (1, 2)$.
   - **Point $B = (4, -1)$**: Setting $t = 1$ gives:
     $$x = 1 + 3(1) = 4, \qquad y = 2 - 3(1) = -1,$$
     which recovers $B = (4, -1)$. (In the simplified parametric form $(x,y) = (1,2) + s(1,-1)$, $A$ corresponds to $s = 0$ and $B$ corresponds to $s = 3$.)
