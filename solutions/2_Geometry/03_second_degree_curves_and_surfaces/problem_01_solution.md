# Problem 1: Recognizing Curves from Canonical Form

## Problem Statement

Recognize the curves
$$x^2+y^2=9,$$
$$\frac{x^2}{16}+\frac{y^2}{9}=1,$$
$$y^2=8x,$$
$$\frac{x^2}{9}-\frac{y^2}{4}=1.$$
For each one, identify the most important features and make a sketch. Explain which parts of the equation let you recognize the type of curve.

## Theoretical Background and Concepts

In analytic geometry, a **second-degree curve** (also called a **conic section**) in the plane $\mathbb{R}^2$ is the set of points $(x,y)$ satisfying a polynomial equation of degree two. When the curve is centered at the origin (or has its vertex at the origin) and its axes of symmetry align with the coordinate axes, its equation takes a standard, simplified form known as the **canonical form**:

1. **Circle:**
   $$x^2 + y^2 = r^2 \quad (r > 0)$$
   - **Algebraic signature:** Both $x^2$ and $y^2$ appear with the same positive coefficient (equal to $1$ when written as $x^2 + y^2 = r^2$, or equivalently $\frac{x^2}{r^2} + \frac{y^2}{r^2} = 1$).
   - **Geometric features:** Set of all points at a fixed distance $r$ (the **radius**) from the **center** $(0,0)$. It is symmetric with respect to both axes and every line through the origin.

2. **Ellipse:**
   $$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 \quad (a > 0, \; b > 0)$$
   - **Algebraic signature:** A sum of two positive squared terms $x^2$ and $y^2$ with *different* positive denominators $a^2 \neq b^2$, set equal to $1$.
   - **Geometric features:** Centered at $(0,0)$, with **horizontal semiaxis** $a$ and **vertical semiaxis** $b$. Its **vertices** (axis intercepts) are $(\pm a, 0)$ and $(0, \pm b)$. If $a > b$, the major axis lies along the $x$-axis; if $b > a$, it lies along the $y$-axis.

3. **Parabola:**
   $$y^2 = 2px \quad \text{or} \quad x^2 = 2py \quad (p \neq 0)$$
   (Often also written as $y^2 = 4fx$, where $f = p/2$ is the focal distance.)
   - **Algebraic signature:** Exactly **one** variable is squared ($y^2$ or $x^2$), while the other variable appears only to the **first power** ($x$ or $y$).
   - **Geometric features:** For $y^2 = 2px$, the **vertex** is at $(0,0)$, the **axis of symmetry** is the $x$-axis ($y=0$), the **focus** is at $(p/2, 0) = (f, 0)$, and the **directrix** is the vertical line $x = -p/2 = -f$. When the coefficient of $x$ is positive, the parabola opens to the right ($x \ge 0$).

4. **Hyperbola:**
   $$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1 \quad \text{or} \quad \frac{y^2}{b^2} - \frac{x^2}{a^2} = 1 \quad (a > 0, \; b > 0)$$
   - **Algebraic signature:** Both $x^2$ and $y^2$ appear, but with **opposite signs** (a difference of two squared terms equal to $1$).
   - **Geometric features:** For $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$, the curve is centered at $(0,0)$ and consists of two separate branches opening left and right along the **transverse axis** ($x$-axis). The **vertices** are at $(\pm a, 0)$, there are no $y$-intercepts, and the two branches approach the **asymptotes** $y = \pm \frac{b}{a}x$ as $|x| \to \infty$.

## Detailed Step-by-Step Solution

---

### Curve 1: $x^2 + y^2 = 9$

#### Step 1: Recognize the Type of Curve from the Equation
Looking at the equation $x^2 + y^2 = 9$:
- Both variables $x$ and $y$ are squared ($x^2$ and $y^2$).
- They are added together with **identical positive coefficients** ($1$ and $1$), and the right-hand side is a positive constant ($9 > 0$).
- Dividing both sides by $9$ gives $\frac{x^2}{9} + \frac{y^2}{9} = 1$, showing equal denominators under $x^2$ and $y^2$.

This matches the canonical equation of a **circle** centered at the origin:
$$x^2 + y^2 = r^2.$$

#### Step 2: Identify the Most Important Features
Comparing $x^2 + y^2 = 9$ with $x^2 + y^2 = r^2$:
$$r^2 = 9 \implies r = \sqrt{9} = 3 \quad (\text{since } r > 0).$$
- **Type:** Circle.
- **Center:** $(0,0)$.
- **Radius:** $r = 3$.
- **$x$-intercepts (set $y=0$):** $x^2 = 9 \implies x = \pm 3$, giving $(-3,0)$ and $(3,0)$.
- **$y$-intercepts (set $x=0$):** $y^2 = 9 \implies y = \pm 3$, giving $(0,-3)$ and $(0,3)$.
- **Domain and Range:** $x \in [-3, 3]$ and $y \in [-3, 3]$.
- **Symmetry:** Symmetric about the $x$-axis, the $y$-axis, and the origin $(0,0)$.

#### Step 3: Coordinate Sketch and Geometric Description
Geometrically, the curve is a round closed loop centered at $(0,0)$ passing through $(3,0)$, $(0,3)$, $(-3,0)$, and $(0,-3)$ at equal distance $3$ from the origin in all directions.

```text
                  y
                  ^
                  |
                3 + (0,3)
             . - ~ ~ - .
          . '     |     ' .
        .         |         .
       .          |          .
  -----+----------+----------+-----> x
     -3 (-3,0)    |0        3 (3,0)
       .          |          .
        .         |         .
          .       |       .
            ' - . _ . - '
               -3 + (0,-3)
                  |
```

---

### Curve 2: $\frac{x^2}{16} + \frac{y^2}{9} = 1$

#### Step 1: Recognize the Type of Curve from the Equation
Looking at the equation $\frac{x^2}{16} + \frac{y^2}{9} = 1$:
- Both $x^2$ and $y^2$ are present and connected by a **plus sign** ($+$), with the right-hand side equal to $1$.
- The denominators under $x^2$ and $y^2$ are positive but **unequal** ($16 \neq 9$), meaning the curve is scaled differently along the $x$-axis and $y$-axis.

This matches the canonical equation of an **ellipse** centered at the origin:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1.$$

#### Step 2: Identify the Most Important Features
Comparing $\frac{x^2}{16} + \frac{y^2}{9} = 1$ with $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$:
$$a^2 = 16 \implies a = 4, \qquad b^2 = 9 \implies b = 3.$$
- **Type:** Ellipse.
- **Center:** $(0,0)$.
- **Horizontal semiaxis (semi-major axis):** $a = 4$ (along the $x$-axis, since $a > b$). Major axis length is $2a = 8$.
- **Vertical semiaxis (semi-minor axis):** $b = 3$ (along the $y$-axis). Minor axis length is $2b = 6$.
- **Vertices ($x$-intercepts, set $y=0$):** $\frac{x^2}{16} = 1 \implies x = \pm 4$, giving $(-4,0)$ and $(4,0)$.
- **Co-vertices ($y$-intercepts, set $x=0$):** $\frac{y^2}{9} = 1 \implies y = \pm 3$, giving $(0,-3)$ and $(0,3)$.
- **Foci:** Since $a > b$, the focal distance $c$ satisfies $c^2 = a^2 - b^2 = 16 - 9 = 7$, so the foci are at $(-\sqrt{7}, 0)$ and $(\sqrt{7}, 0)$ (approximately $(\pm 2.65, 0)$).
- **Domain and Range:** $x \in [-4, 4]$, $y \in [-3, 3]$.

#### Step 3: Coordinate Sketch and Geometric Description
Geometrically, the curve is an oval centered at $(0,0)$, stretched further horizontally (between $x=-4$ and $x=4$) than vertically (between $y=-3$ and $y=3$).

```text
                      y
                      ^
                      |
                    3 + (0,3)
               . - ~ ~ ~ ~ - .
          . '         |         ' .
       .              |              .
  ----+---------------+---------------+-----> x
    -4 (-4,0)         |0              4 (4,0)
       .              |              .
          .           |           .
               ' - . _ _ _ . - '
                   -3 + (0,-3)
                      |
```

---

### Curve 3: $y^2 = 8x$

#### Step 1: Recognize the Type of Curve from the Equation
Looking at the equation $y^2 = 8x$:
- Only the variable $y$ is squared ($y^2$), whereas the variable $x$ appears only linearly (to the first power, $8x$).
- Whenever one variable is quadratic and the other is linear, the curve is a **parabola**.

This matches the canonical equation of a horizontal **parabola**:
$$y^2 = 2px \quad (\text{or } y^2 = 4fx).$$

#### Step 2: Identify the Most Important Features
Comparing $y^2 = 8x$ with $y^2 = 2px = 4fx$:
$$2p = 8 \implies p = 4, \qquad 4f = 8 \implies f = 2.$$
- **Type:** Parabola.
- **Vertex:** $(0,0)$.
- **Axis of symmetry:** The $x$-axis (the line $y = 0$), because replacing $y$ with $-y$ leaves $y^2 = 8x$ unchanged.
- **Opening direction:** Opens to the **right** (in the positive $x$-direction), because $y^2 \ge 0$ for all real $y$, which forces $8x \ge 0 \implies x \ge 0$.
- **Focus and Directrix:** Focus at $F = (f, 0) = (2, 0)$; directrix is the vertical line $x = -2$.
- **Sample symmetric points:** Setting $x = 2$ gives $y^2 = 16 \implies y = \pm 4$, yielding the points $(2,4)$ and $(2,-4)$ (the endpoints of the latus rectum).

#### Step 3: Coordinate Sketch and Geometric Description
Geometrically, the curve starts at its vertex $(0,0)$ tangent to the $y$-axis and opens rightward as two symmetric upper and lower arms passing through $(2,4)$ and $(2,-4)$.

```text
              y
              ^
            4 +        * (2,4)
              |     . '
              |  . '
              |.'
  ------------+--------+--------> x
             0|(0,0)   2
              |'.
              |  ' .
              |     ' .
           -4 +        * (2,-4)
              |
```

---

### Curve 4: $\frac{x^2}{9} - \frac{y^2}{4} = 1$

#### Step 1: Recognize the Type of Curve from the Equation
Looking at the equation $\frac{x^2}{9} - \frac{y^2}{4} = 1$:
- Both $x$ and $y$ appear squared ($x^2$ and $y^2$), and the right-hand side is $1$.
- Crucially, the two squared terms have **opposite signs**: the $x^2$ term is positive ($+\frac{x^2}{9}$) and the $y^2$ term is negative ($-\frac{y^2}{4}$).

This difference of squares matches the canonical equation of a **hyperbola** centered at the origin:
$$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1.$$

#### Step 2: Identify the Most Important Features
Comparing $\frac{x^2}{9} - \frac{y^2}{4} = 1$ with $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$:
$$a^2 = 9 \implies a = 3, \qquad b^2 = 4 \implies b = 2.$$
- **Type:** Hyperbola (opening left and right).
- **Center:** $(0,0)$.
- **Transverse axis:** Along the $x$-axis (since the $x^2$ term is positive), with semi-transverse axis $a = 3$.
- **Conjugate axis:** Along the $y$-axis, with semi-conjugate axis $b = 2$.
- **Vertices ($x$-intercepts, set $y=0$):** $\frac{x^2}{9} = 1 \implies x^2 = 9 \implies x = \pm 3$, giving $(-3,0)$ and $(3,0)$.
- **$y$-intercepts (set $x=0$):** $-\frac{y^2}{4} = 1 \implies y^2 = -4$, which has **no real solutions**. Thus, the curve never crosses the $y$-axis. Indeed, $\frac{x^2}{9} = 1 + \frac{y^2}{4} \ge 1 \implies |x| \ge 3$.
- **Asymptotes:** Found by replacing the $1$ on the right-hand side with $0$:
  $$\frac{x^2}{9} - \frac{y^2}{4} = 0 \implies \frac{y^2}{4} = \frac{x^2}{9} \implies y = \pm \frac{b}{a}x = \pm \frac{2}{3}x.$$
- **Foci:** The focal distance $c$ satisfies $c^2 = a^2 + b^2 = 9 + 4 = 13$, so the foci are at $(-\sqrt{13}, 0)$ and $(\sqrt{13}, 0)$.

#### Step 3: Coordinate Sketch and Geometric Description
Geometrically, the hyperbola consists of two disconnected branches: a left branch for $x \le -3$ with vertex $(-3,0)$ and a right branch for $x \ge 3$ with vertex $(3,0)$. As $|x|$ grows large, both branches approach the diagonal asymptote lines $y = \frac{2}{3}x$ and $y = -\frac{2}{3}x$, which pass through the corners $(\pm 3, \pm 2)$ of the central reference rectangle.

```text
        \           y           /
         \          ^          /  y = (2/3)x
     .    \         |         /    .
      .    \      2 +---.---+/    .
       .    \   .---|---.   /    .
        .    \  |   |   |  /    .
  -------+----*-+---+---+--*---+-------> x
        -3 (-3,0)   |0    (3,0) 3
        .    /  |   |   |  \    .
       .    /   '---|---'   \    .
      .    /     -2 +---'---+\    .
     .    /         |         \    .
         /          |          \  y = -(2/3)x
        /                       \
```

---

### Summary Comparison: How to Recognize Each Curve from Its Equation

| Equation | Degrees of Variables | Signs of Squared Terms | Scale / Denominators | Resulting Curve Type |
| :--- | :--- | :--- | :--- | :--- |
| $x^2 + y^2 = 9$ | Both $x^2$ and $y^2$ (degree 2) | Both positive ($+, +$) | Equal ($r^2 = 9$) | **Circle** |
| $\frac{x^2}{16} + \frac{y^2}{9} = 1$ | Both $x^2$ and $y^2$ (degree 2) | Both positive ($+, +$) | Unequal ($16 \neq 9$) | **Ellipse** |
| $y^2 = 8x$ | $y^2$ (degree 2), $x$ (degree 1) | Only one squared term | Linear scale $2p = 8$ | **Parabola** |
| $\frac{x^2}{9} - \frac{y^2}{4} = 1$ | Both $x^2$ and $y^2$ (degree 2) | Opposite signs ($+, -$) | $a^2 = 9$, $b^2 = 4$ | **Hyperbola** |

## Verification and Consistency Checks

Let us verify the key intercepts and sample points by substituting their coordinates directly into each original equation:

1. **Circle ($x^2 + y^2 = 9$):**
   - Substitute vertex $(3,0)$: $3^2 + 0^2 = 9 + 0 = 9$. (Matches RHS $= 9$.)
   - Substitute vertex $(0,-3)$: $0^2 + (-3)^2 = 0 + 9 = 9$. (Matches RHS $= 9$.)

2. **Ellipse ($\frac{x^2}{16} + \frac{y^2}{9} = 1$):**
   - Substitute major vertex $(-4,0)$: $\frac{(-4)^2}{16} + \frac{0^2}{9} = \frac{16}{16} + 0 = 1$. (Matches RHS $= 1$.)
   - Substitute minor vertex $(0,3)$: $\frac{0^2}{16} + \frac{3^2}{9} = 0 + \frac{9}{9} = 1$. (Matches RHS $= 1$.)

3. **Parabola ($y^2 = 8x$):**
   - Substitute vertex $(0,0)$: $\text{LHS} = 0^2 = 0$, $\text{RHS} = 8(0) = 0$. (Matches.)
   - Substitute sample points $(2, \pm 4)$: $\text{LHS} = (\pm 4)^2 = 16$, $\text{RHS} = 8(2) = 16$. (Matches.)

4. **Hyperbola ($\frac{x^2}{9} - \frac{y^2}{4} = 1$):**
   - Substitute vertices $(\pm 3, 0)$: $\frac{(\pm 3)^2}{9} - \frac{0^2}{4} = \frac{9}{9} - 0 = 1$. (Matches RHS $= 1$.)
   - Check another point on the hyperbola, e.g., $x = 6$: $\frac{6^2}{9} - \frac{y^2}{4} = 1 \implies 4 - \frac{y^2}{4} = 1 \implies y^2 = 12 \implies y = \pm 2\sqrt{3} \approx \pm 3.464$. Notice that at $x = 6$, the asymptote height is $y = \pm \frac{2}{3}(6) = \pm 4$, confirming that the hyperbola lies slightly inside its asymptotes ($3.464 < 4$).
