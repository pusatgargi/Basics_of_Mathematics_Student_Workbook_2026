# Problem 10: Paraboloids

## Problem Statement

Compare
$$z=x^2+y^2$$
and
$$z=x^2-y^2.$$
For each surface, describe the cross-sections $x=0$, $y=0$, and $z=c$, then make a qualitative sketch.

## Theoretical Background and Concepts

A **paraboloid** is a second-degree surface in $\mathbb{R}^3$ in which one variable (typically $z$) appears linearly (to the first power) while the other two variables ($x$ and $y$) appear quadratically (squared):
$$z = \frac{x^2}{a^2} \pm \frac{y^2}{b^2}.$$
Depending on whether the two squared terms have the **same sign** or **opposite signs**, there are two fundamentally different geometric types of paraboloids:

1. **Elliptic Paraboloid (Circular Paraboloid when $a = b$):**
   $$z = \frac{x^2}{a^2} + \frac{y^2}{b^2}.$$
   - **Algebraic structure:** $z$ is the **sum** of two non-negative squares.
   - **Geometry:** Both vertical cross-sections ($x = 0$ and $y = 0$) are parabolas opening in the **same direction** (upward toward $+z$). Horizontal cross-sections ($z = c > 0$) are ellipses (or circles if $a = b$). The surface is shaped like a **bowl** or satellite dish with a minimum vertex at $(0,0,0)$.

2. **Hyperbolic Paraboloid ("Saddle Surface"):**
   $$z = \frac{x^2}{a^2} - \frac{y^2}{b^2}.$$
   - **Algebraic structure:** $z$ is the **difference** of two squares.
   - **Geometry:** Vertical cross-sections along the $x$- and $y$-axes are parabolas opening in **opposite directions** (one opens upward, the other opens downward). Horizontal cross-sections ($z = c \neq 0$) are **hyperbolas**, and at $z = 0$ the cross-section is a pair of intersecting lines. The surface is shaped like a **saddle** or mountain pass, with a saddle point at $(0,0,0)$.

## Detailed Step-by-Step Solution

---

### Surface 1: $z = x^2 + y^2$ (Circular / Elliptic Paraboloid)

#### 1. Vertical Cross-Section $x = 0$ (in the $yz$-plane):
Substitute $x = 0$ into $z = x^2 + y^2$:
$$z = 0^2 + y^2 \implies z = y^2, \quad x = 0.$$
- **Description:** A **parabola** in the $yz$-plane with vertex at $(0,0,0)$, axis of symmetry along the $Oz$-axis, opening **upward** (in the $+z$ direction).

#### 2. Vertical Cross-Section $y = 0$ (in the $xz$-plane):
Substitute $y = 0$ into $z = x^2 + y^2$:
$$z = x^2 + 0^2 \implies z = x^2, \quad y = 0.$$
- **Description:** A **parabola** in the $xz$-plane with vertex at $(0,0,0)$, axis of symmetry along the $Oz$-axis, also opening **upward** (in the $+z$ direction).

#### 3. Horizontal Cross-Sections $z = c$ (parallel to the $xy$-plane):
Substitute $z = c$ into $z = x^2 + y^2$:
$$x^2 + y^2 = c.$$
Because $x^2 + y^2 \ge 0$ for all real $x, y$, the behavior depends on the sign of $c$:
- **For $c < 0$:** $x^2 + y^2 = c < 0$ has **no real solutions** (the cross-section is the **empty set** $\varnothing$). No part of the surface lies below the plane $z = 0$.
- **For $c = 0$:** $x^2 + y^2 = 0 \implies x = 0 \text{ and } y = 0$. The cross-section is a **single point**, the vertex $(0,0,0)$.
- **For $c > 0$:** $x^2 + y^2 = (\sqrt{c})^2$. The cross-section is a **circle** centered at $(0,0,c)$ with radius $r(c) = \sqrt{c}$, which grows larger as $c$ increases.

#### 4. Qualitative Sketch of $z = x^2 + y^2$:
The surface is a rotationally symmetric **bowl** (circular paraboloid) resting on its vertex at $(0,0,0)$ and opening upward along $+z$, built from horizontal circular rings $x^2 + y^2 = c$ stacked on upward-opening parabolic ribs $z = x^2$ and $z = y^2$.

```text
                        z
                        ^
                        |
                . - ~ ~ | ~ ~ - .
             . '        |        ' .    <-- Circular cross-section z = c > 0
             ' . _ _ _  |  _ _ _ . '        (radius r = sqrt(c))
              \         |         /
               \  z=x^2 | z=y^2  /
                \       |       /       <-- Upward parabolas in x=0 and y=0
                 \      |      /
                  ' .   |   . '
                     ' .*. '            <-- Vertex at (0,0,0)
                       /|\
                      / | \
                     x  |  y
```

---

### Surface 2: $z = x^2 - y^2$ (Hyperbolic Paraboloid / Saddle)

#### 1. Vertical Cross-Section $x = 0$ (in the $yz$-plane):
Substitute $x = 0$ into $z = x^2 - y^2$:
$$z = 0^2 - y^2 \implies z = -y^2, \quad x = 0.$$
- **Description:** A **parabola** in the $yz$-plane with vertex at $(0,0,0)$, axis of symmetry along the $Oz$-axis, opening **downward** (in the $-z$ direction, since $z = -y^2 \le 0$). Along the $y$-direction, the origin is a local **maximum**.

#### 2. Vertical Cross-Section $y = 0$ (in the $xz$-plane):
Substitute $y = 0$ into $z = x^2 - y^2$:
$$z = x^2 - 0^2 \implies z = x^2, \quad y = 0.$$
- **Description:** A **parabola** in the $xz$-plane with vertex at $(0,0,0)$, axis of symmetry along the $Oz$-axis, opening **upward** (in the $+z$ direction, since $z = x^2 \ge 0$). Along the $x$-direction, the origin is a local **minimum**.

#### 3. Horizontal Cross-Sections $z = c$ (parallel to the $xy$-plane):
Substitute $z = c$ into $z = x^2 - y^2$:
$$x^2 - y^2 = c.$$
Unlike the first surface, cross-sections exist for **every** real value $c \in \mathbb{R}$, and their geometry depends on the sign of $c$:
- **For $c > 0$:** Dividing by $c$ gives $\frac{x^2}{c} - \frac{y^2}{c} = 1$. This is a **hyperbola** opening along the **$x$-axis** (left/right in the $x$-direction), with vertices at $(\pm \sqrt{c}, 0, c)$.
- **For $c = 0$:** $x^2 - y^2 = 0 \implies (x - y)(x + y) = 0 \implies y = x \text{ or } y = -x$. The cross-section is a **pair of intersecting straight lines** passing through the origin $(0,0,0)$.
- **For $c < 0$:** Let $c = -k$ with $k = |c| > 0$. Then $x^2 - y^2 = -k \implies y^2 - x^2 = k \implies \frac{y^2}{k} - \frac{x^2}{k} = 1$. This is a **hyperbola** opening along the **$y$-axis** (front/back in the $y$-direction), with vertices at $(0, \pm \sqrt{|c|}, c)$.

#### 4. Qualitative Sketch of $z = x^2 - y^2$:
The surface is a **saddle** centered at the origin $(0,0,0)$: it curves **upward** along the $x$-axis ($z = x^2$, like the front and back pommel/cantle of a horse saddle) and curves **downward** along the $y$-axis ($z = -y^2$, where a rider's legs hang down).

```text
                        z
                        ^
          *             |             *
          :\            |            /:
          : \   z = x^2 |           / :   <-- Curves UP along x-axis (y=0)
          :  ' .        |        . '  :
          :     ' .     |     . '     :
          :        ' . _*_ . '        :   <-- Saddle point at (0,0,0)
          :        . '  |  ' .        :
          :     . '     |     ' .     :
          :   /         | z=-y^2  \   :   <-- Curves DOWN along y-axis (x=0)
           \ /          |          \ /
            *           |           *
                       / \
                      x   y

     Horizontal Cross-Sections (Top View in xy-plane for z = c):
                   y
                   ^
          \   . '  |  ' .   /   <-- c < 0: hyperbola opening along y-axis
           \    ' .|. '    /
            \     /|\     /     <-- c = 0: intersecting lines y = x, y = -x
         .   \   / | \   /   .
          .   \ /  |  \ /   .
     ------+---*---+---*---+------> x
          .   / \  |0 / \   .   <-- c > 0: hyperbola opening along x-axis
         .   /   \ | /   \   .
            /     \|/     \
           /    . '|'.     \
          /   ' .  |  . '   \
```

---

### Summary Comparison of the Two Paraboloids

| Feature | $z = x^2 + y^2$ (Elliptic / Circular Paraboloid) | $z = x^2 - y^2$ (Hyperbolic Paraboloid) |
| :--- | :--- | :--- |
| **Cross-section $x = 0$** | Parabola $z = y^2$ (opens **upward**) | Parabola $z = -y^2$ (opens **downward**) |
| **Cross-section $y = 0$** | Parabola $z = x^2$ (opens **upward**) | Parabola $z = x^2$ (opens **upward**) |
| **Cross-section $z = c > 0$** | Circle $x^2 + y^2 = c$ of radius $\sqrt{c}$ | Hyperbola $x^2 - y^2 = c$ opening along $Ox$ |
| **Cross-section $z = 0$** | Single point $(0,0,0)$ | Two intersecting lines $y = \pm x$ |
| **Cross-section $z = c < 0$** | Empty set $\varnothing$ (no real points) | Hyperbola $y^2 - x^2 = |c|$ opening along $Oy$ |
| **Range of $z$** | $z \in [0, +\infty)$ | $z \in (-\infty, +\infty)$ |
| **Nature of $(0,0,0)$** | Global **minimum** (bowl bottom) | **Saddle point** (min along $x$, max along $y$) |

## Verification and Consistency Checks

1. **Checking Sample Points on $z = x^2 + y^2$:**
   - At $(x, y) = (2, 0)$ (on the $y=0$ parabola): $z = 2^2 + 0^2 = 4 > 0$.
   - At $(x, y) = (0, 2)$ (on the $x=0$ parabola): $z = 0^2 + 2^2 = 4 > 0$.
   - Both $(2, 0, 4)$ and $(0, 2, 4)$ lie at the same positive height $z = 4$ on the circle $x^2 + y^2 = 4$ of radius $2$. $\checkmark$

2. **Checking Sample Points on $z = x^2 - y^2$:**
   - At $(x, y) = (2, 0)$ (on the $y=0$ parabola): $z = 2^2 - 0^2 = +4$ (above $z=0$, on hyperbola $x^2 - y^2 = 4$).
   - At $(x, y) = (0, 2)$ (on the $x=0$ parabola): $z = 0^2 - 2^2 = -4$ (below $z=0$, on hyperbola $y^2 - x^2 = 4$).
   - At $(x, y) = (2, 2)$ (on the line $y = x$): $z = 2^2 - 2^2 = 0$ (lies in the plane $z = 0$). $\checkmark$
