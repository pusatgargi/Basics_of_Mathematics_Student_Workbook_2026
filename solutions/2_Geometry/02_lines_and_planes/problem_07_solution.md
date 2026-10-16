# Problem 7: A Line Relative to a Plane

## Problem Statement

For
$$L:(x,y,z)=(1,1,0)+t(1,-1,0),\qquad \Pi:x+y+z=2,$$
determine whether the line intersects the plane at one point, is parallel to it, or lies in it. Explain the role of the dot product of the direction vector and the normal vector.

## Theoretical Background and Concepts

Consider a line $L$ and a plane $\Pi$ in $\mathbb{R}^3$:
$$L: \vec{x}(t) = P_0 + t\vec{v} \quad (t \in \mathbb{R}) \qquad \text{and} \qquad \Pi: \vec{n} \cdot \vec{x} = d,$$
where $P_0 = (x_0, y_0, z_0)$ is a reference point on the line, $\vec{v} = (v_x, v_y, v_z) \neq \vec{0}$ is the direction vector of the line, and $\vec{n} = (a, b, c) \neq \vec{0}$ is a normal vector to the plane.

To find the points of $L$ that also lie in $\Pi$, we substitute $\vec{x}(t) = P_0 + t\vec{v}$ into the plane equation $\vec{n} \cdot \vec{x} = d$:
$$\vec{n} \cdot (P_0 + t\vec{v}) = d \iff (\vec{n} \cdot P_0) + t(\vec{n} \cdot \vec{v}) = d \iff (\vec{n} \cdot \vec{v})\,t = d - \vec{n} \cdot P_0.$$
This is a single linear equation in $t$ of the form $A t = B$, where $A = \vec{n} \cdot \vec{v}$ and $B = d - \vec{n} \cdot P_0$. There are three possible geometric configurations:

1. **Unique Intersection Point ($\vec{n} \cdot \vec{v} \neq 0$)**:
   When $\vec{n} \cdot \vec{v} \neq 0$, we can divide by $\vec{n} \cdot \vec{v}$ to get the unique parameter value:
   $$t = \frac{d - \vec{n} \cdot P_0}{\vec{n} \cdot \vec{v}}.$$
   The line pierces the plane at exactly one point.

2. **Strictly Parallel with No Common Points ($\vec{n} \cdot \vec{v} = 0$ and $\vec{n} \cdot P_0 \neq d$)**:
   The direction of the line is parallel to the plane ($\vec{v} \perp \vec{n}$), and the base point $P_0$ does not lie in the plane. The equation for $t$ becomes $0 \cdot t = B$ with $B \neq 0$, which has **no solution**.

3. **Line Contained in the Plane ($\vec{n} \cdot \vec{v} = 0$ and $\vec{n} \cdot P_0 = d$)**:
   The direction of the line is parallel to the plane ($\vec{v} \perp \vec{n}$), and the base point $P_0$ already lies in the plane. The equation for $t$ becomes $0 \cdot t = 0$, which is satisfied by **every $t \in \mathbb{R}$**. Every point of $L$ lies in $\Pi$ ($L \subset \Pi$).

## Detailed Step-by-Step Solution

### Step 1: Extract the Characteristic Vectors and Reference Point

From the given descriptions:
- For the line $L: (x, y, z) = (1, 1, 0) + t(1, -1, 0)$:
  - Reference point: $P_0 = (1, 1, 0)$
  - Direction vector: $\vec{v} = (1, -1, 0)$
- For the plane $\Pi: x + y + z = 2$:
  - Normal vector: $\vec{n} = (1, 1, 1)$
  - Right-hand side constant: $d = 2$

### Step 2: Compute the Dot Product $\vec{n} \cdot \vec{v}$

We first test whether the direction of the line has any component perpendicular to the plane by computing the dot product of $\vec{n}$ and $\vec{v}$:
$$\vec{n} \cdot \vec{v} = (1, 1, 1) \cdot (1, -1, 0) = (1)(1) + (1)(-1) + (1)(0) = 1 - 1 + 0 = 0.$$
Since $\vec{n} \cdot \vec{v} = 0$, the direction vector $\vec{v}$ is orthogonal to the plane's normal vector $\vec{n}$. This means the line $L$ cannot intersect the plane $\Pi$ at a single point; instead, $L$ is either strictly parallel to $\Pi$ or contained entirely within $\Pi$.

### Step 3: Check Whether a Point of $L$ Lies in $\Pi$

To distinguish between being strictly parallel ($L \cap \Pi = \emptyset$) and lying inside the plane ($L \subset \Pi$), we check whether the reference point $P_0 = (1, 1, 0)$ satisfies the plane equation $x + y + z = 2$:
$$\vec{n} \cdot P_0 = 1 + 1 + 0 = 2.$$
Comparing with $d = 2$, we see that $\vec{n} \cdot P_0 = 2 = d$, so the point $P_0 = (1, 1, 0)$ lies in the plane $\Pi$.

**Conclusion**: Because the line starts at a point $P_0$ inside the plane $\Pi$ and moves in a direction $\vec{v}$ parallel to the plane ($\vec{v} \perp \vec{n}$), **the line $L$ lies entirely in the plane $\Pi$** ($L \subset \Pi$).

### Step 4: Explain the Role of the Dot Product $\vec{n} \cdot \vec{v}$

The dot product $\vec{n} \cdot \vec{v}$ is the fundamental algebraic and geometric test for the relative orientation of a line and a plane:

1. **Geometric Meaning (Rate of Change along the Normal)**:
   The normal vector $\vec{n}$ points perpendicular to the plane $\Pi$, while $\vec{v}$ describes how a point on the line $L$ moves as the parameter $t$ increases by $1$ unit. The dot product $\vec{n} \cdot \vec{v}$ measures the component of the line's velocity vector $\vec{v}$ in the direction perpendicular to the plane:
   - If $\vec{n} \cdot \vec{v} \neq 0$, moving along the line changes the "height" $\vec{n} \cdot \vec{x}$ relative to the plane at a non-zero rate, forcing the line to cross the plane $\vec{n} \cdot \vec{x} = d$ at a single, unique time $t$.
   - If $\vec{n} \cdot \vec{v} = 0$, the vector $\vec{v}$ is perpendicular to $\vec{n}$, meaning $\vec{v}$ is parallel to the plane. Moving along the line never changes the quantity $\vec{n} \cdot \vec{x}$; the line maintains a constant signed distance from the plane for all $t \in \mathbb{R}$.
2. **Algebraic Meaning (Coefficient of $t$)**:
   When substituting $\vec{x} = P_0 + t\vec{v}$ into $\vec{n} \cdot \vec{x} = d$, we obtain $(\vec{n} \cdot \vec{v})t = d - \vec{n} \cdot P_0$. Thus, $\vec{n} \cdot \vec{v}$ is literally the coefficient of the unknown parameter $t$. A linear equation $At = B$ has a unique solution if and only if the coefficient $A = \vec{n} \cdot \vec{v} \neq 0$.

## Verification and Consistency Checks

1. **Direct Substitution of the Parametric Equations into the Plane Equation**:
   From $L: (x, y, z) = (1, 1, 0) + t(1, -1, 0)$, the coordinates of any point on $L$ are:
   $$x(t) = 1 + t, \qquad y(t) = 1 - t, \qquad z(t) = 0.$$
   Substituting these into the left-hand side of $\Pi: x + y + z = 2$ gives:
   $$x(t) + y(t) + z(t) = (1 + t) + (1 - t) + 0 = (1 + 1 + 0) + (1 - 1)t = 2 + 0t = 2.$$
   Since $2 = 2$ is an identity that holds for **all** $t \in \mathbb{R}$, every point on $L$ satisfies the equation of $\Pi$.

2. **Testing Specific Points on $L$**:
   - For $t = 0$: $(x, y, z) = (1, 1, 0) \implies 1 + 1 + 0 = 2 \quad \checkmark$
   - For $t = 1$: $(x, y, z) = (2, 0, 0) \implies 2 + 0 + 0 = 2 \quad \checkmark$
   - For $t = -3$: $(x, y, z) = (-2, 4, 0) \implies -2 + 4 + 0 = 2 \quad \checkmark$
   All sampled points on the line lie in the plane $\Pi$.
