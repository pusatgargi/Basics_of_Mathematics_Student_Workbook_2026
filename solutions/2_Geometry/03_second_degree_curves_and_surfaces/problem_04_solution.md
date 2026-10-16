# Problem 4: Parabola

## Problem Statement

For
$$y^2=12x,$$
identify the vertex, axis of symmetry, and opening direction. Find points on the parabola for $x=3$ and use them to make a sketch.

## Theoretical Background and Concepts

A **parabola** is the locus of points in a plane that are equidistant from a fixed point $F$ (the **focus**) and a fixed line $d$ (the **directrix**). When the vertex is placed at the origin $(0,0)$ and the axis of symmetry lies along one of the coordinate axes, the canonical equation takes one of two forms:

1. **Horizontal axis of symmetry ($x$-axis, line $y = 0$):**
   $$y^2 = 2px \quad (\text{or } y^2 = 4fx),$$
   where $f = \frac{p}{2}$ is the signed focal distance from the vertex $(0,0)$ to the focus $F = (f, 0)$, and the directrix is the vertical line $x = -f$:
   - If the coefficient of $x$ is **positive** ($2p > 0$), then $x = \frac{y^2}{2p} \ge 0$ for all real $y$, so the parabola **opens to the right** (along the positive $x$-axis).
   - If the coefficient of $x$ is **negative** ($2p < 0$), then $x \le 0$ for all real $y$, so the parabola **opens to the left** (along the negative $x$-axis).

2. **Vertical axis of symmetry ($y$-axis, line $x = 0$):**
   $$x^2 = 2py \quad (\text{or } x^2 = 4fy),$$
   which has its vertex at $(0,0)$, axis of symmetry along the $y$-axis ($x=0$), and opens upward if $2p > 0$ or downward if $2p < 0$.

Key geometric features of $y^2 = 2px$:
- **Vertex:** The point where the parabola turns and intersects its axis of symmetry, located at $(0,0)$.
- **Symmetry:** Because $y$ appears only as $y^2$, if $(x, y)$ lies on the curve, then $(x, -y)$ also lies on the curve (since $(-y)^2 = y^2$). Thus the line $y = 0$ ($x$-axis) is the axis of symmetry.

## Detailed Step-by-Step Solution

### Step 1: Identify the Vertex, Axis of Symmetry, and Opening Direction
We examine the given canonical equation:
$$y^2 = 12x.$$

1. **Vertex:**
   There are no constant shifts added to $x$ or $y$ (the equation has the form $(y - y_0)^2 = 2p(x - x_0)$ with $(x_0, y_0) = (0,0)$). When $x = 0$, $y^2 = 0 \implies y = 0$.
   - **Vertex:** $V = (0, 0)$.

2. **Axis of Symmetry:**
   Replacing $y$ by $-y$ leaves the equation unchanged because $(-y)^2 = y^2 = 12x$. This means that for every point $(x, y)$ on the curve above the $x$-axis, its reflection $(x, -y)$ across the $x$-axis is also on the curve.
   - **Axis of symmetry:** The $x$-axis ($Ox$), whose equation is $y = 0$.

3. **Opening Direction:**
   For any real number $y \in \mathbb{R}$, the square $y^2$ is non-negative ($y^2 \ge 0$). Since $12x = y^2 \ge 0$ and the coefficient $12 > 0$ is positive, dividing by $12$ yields:
   $$x = \frac{y^2}{12} \ge 0.$$
   Therefore, no points of the parabola exist for $x < 0$, and as $|y|$ increases, $x$ increases toward $+\infty$.
   - **Opening direction:** The parabola opens **to the right** (in the direction of the positive $x$-axis).

4. **Focus and Directrix (Additional Canonical Parameters):**
   Comparing $y^2 = 12x$ with $y^2 = 4fx = 2px$:
   $$4f = 12 \implies f = 3 \quad (p = 6).$$
   Thus, the **focus** is at $F = (3, 0)$ and the **directrix** is the vertical line $x = -3$.

### Step 2: Find Points on the Parabola for $x = 3$
Substitute $x = 3$ into the equation $y^2 = 12x$:
$$y^2 = 12 \cdot 3$$
$$y^2 = 36.$$
Taking the square root of both sides gives two symmetric values for $y$:
$$y = \pm \sqrt{36} = \pm 6.$$
Therefore, for $x = 3$, we obtain the two points on the parabola:
$$P_1 = (3, 6) \quad \text{and} \quad P_2 = (3, -6).$$
*(Note: Because $x = 3$ is the $x$-coordinate of the focus $F(3,0)$, the vertical segment connecting $P_1(3,6)$ and $P_2(3,-6)$ is the **latus rectum** of the parabola, which has length $4f = 12$.)*

### Step 3: Coordinate Sketch and Geometric Description
- **Vertex:** $(0,0)$, where the parabola is tangent to the vertical $y$-axis ($x=0$).
- **Axis of Symmetry:** The horizontal $x$-axis ($y=0$).
- **Key Points Plotted:** Vertex $V(0,0)$, upper point $P_1(3,6)$, and lower point $P_2(3,-6)$, along with the focus $F(3,0)$ midway between $P_1$ and $P_2$.

```text
                y
                ^
              6 +            * P1(3,6)
                |        . ' :
                |     . '    :
              3 +  . '       :
                |.'          :
  --------------+------------+------------> x
               0|V(0,0)     3 F(3,0)
                |'.          :
             -3 +  ' .       :
                |     ' .    :
                |        ' . :
             -6 +            * P2(3,-6)
                |
```

## Verification and Consistency Checks

1. **Direct Substitution of Found Points into $y^2 = 12x$:**
   - **Vertex $V(0,0)$:**
     $$\text{LHS} = 0^2 = 0, \qquad \text{RHS} = 12(0) = 0. \quad (\text{LHS} = \text{RHS}) \quad \checkmark$$
   - **Upper point $P_1(3, 6)$:**
     $$\text{LHS} = 6^2 = 36, \qquad \text{RHS} = 12(3) = 36. \quad (\text{LHS} = \text{RHS}) \quad \checkmark$$
   - **Lower point $P_2(3, -6)$:**
     $$\text{LHS} = (-6)^2 = 36, \qquad \text{RHS} = 12(3) = 36. \quad (\text{LHS} = \text{RHS}) \quad \checkmark$$

2. **Focus–Directrix Distance Check:**
   By definition of a parabola, the distance from $P_1(3,6)$ to the focus $F(3,0)$ must equal the perpendicular distance from $P_1(3,6)$ to the directrix $x = -3$:
   - Distance to focus: $|P_1 F| = \sqrt{(3 - 3)^2 + (6 - 0)^2} = \sqrt{0 + 36} = 6$.
   - Distance to directrix $x = -3$: $|3 - (-3)| = 6$.
   Both distances equal $6$, confirming the geometric accuracy of our points and parameters.
