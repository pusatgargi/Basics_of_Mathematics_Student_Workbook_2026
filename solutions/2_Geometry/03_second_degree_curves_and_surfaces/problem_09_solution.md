# Problem 9: Ellipsoid and Its Cross-Sections

## Problem Statement

Consider
$$\frac{x^2}{9}+\frac{y^2}{4}+\frac{z^2}{16}=1.$$
Give the semiaxis lengths, describe the cross-section $z=0$, and explain how the cross-sections $z=c$ change for $|c|<4$.

## Theoretical Background and Concepts

An **ellipsoid** centered at the origin $(0,0,0)$ with axes aligned along the coordinate axes in $\mathbb{R}^3$ has the **canonical equation**:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1 \quad (a > 0, \; b > 0, \; c_0 > 0).$$
(Here we denote the third semiaxis by $c_0$ to avoid confusion with the cross-section plane height $z = c$.)

Key geometric properties of an ellipsoid:
1. **Semiaxes and Intercepts:** The positive constants $a$, $b$, and $c_0$ are the **semiaxis lengths** along the $Ox$, $Oy$, and $Oz$ axes, respectively. Because each squared fraction is non-negative, the surface is bounded within the rectangular box $[-a, a] \times [-b, b] \times [-c_0, c_0]$, intersecting the axes at the six vertices $(\pm a, 0, 0)$, $(0, \pm b, 0)$, and $(0, 0, \pm c_0)$.
2. **Method of Cross-Sections (Traces):** To understand a 3D surface $F(x,y,z) = 1$, we slice it with horizontal planes $z = c$ (where $c$ is a constant). Substituting $z = c$ reduces the 3D surface equation to a 2D curve equation in $x$ and $y$ lying in the plane $z = c$:
   $$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1 - \frac{c^2}{c_0^2}.$$
   When $|c| < c_0$, the right-hand side $k = 1 - \frac{c^2}{c_0^2}$ is strictly positive ($0 < k \le 1$). Dividing both sides by $k$ yields an **ellipse** whose semiaxes $a(c) = a\sqrt{1 - c^2/c_0^2}$ and $b(c) = b\sqrt{1 - c^2/c_0^2}$ are scaled down proportionally by the same factor $\sqrt{1 - c^2/c_0^2}$.

## Detailed Step-by-Step Solution

### Step 1: Find the Semiaxis Lengths
We compare the given equation
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{z^2}{16} = 1$$
with the canonical equation of an ellipsoid:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} + \frac{z^2}{c_0^2} = 1.$$
Matching the denominators under $x^2$, $y^2$, and $z^2$:
- $a^2 = 9 \implies a = \sqrt{9} = 3$ (semiaxis length along the **$x$-axis**; $x$-intercepts at $(\pm 3, 0, 0)$).
- $b^2 = 4 \implies b = \sqrt{4} = 2$ (semiaxis length along the **$y$-axis**; $y$-intercepts at $(0, \pm 2, 0)$).
- $c_0^2 = 16 \implies c_0 = \sqrt{16} = 4$ (semiaxis length along the **$z$-axis**; $z$-intercepts at $(0, 0, \pm 4)$).

Notice that $c_0 = 4 > a = 3 > b = 2$, so the ellipsoid is most elongated vertically along the $z$-axis and narrowest along the $y$-axis.

### Step 2: Describe the Cross-Section $z = 0$
To find the cross-section (trace) of the ellipsoid in the horizontal coordinate plane $z = 0$ (the $xy$-plane), we substitute $z = 0$ into the equation of the ellipsoid:
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{0^2}{16} = 1 \implies \frac{x^2}{9} + \frac{y^2}{4} = 1, \quad z = 0.$$

**Geometric Description of the Cross-Section $z = 0$:**
- It is an **ellipse** lying in the plane $z = 0$, centered at the origin $(0,0,0)$.
- Its semiaxis along the $x$-axis is $a = 3$ (with vertices at $(\pm 3, 0, 0)$).
- Its semiaxis along the $y$-axis is $b = 2$ (with vertices at $(0, \pm 2, 0)$).
- It is stretched more along the $x$-axis than along the $y$-axis, and it represents the **largest** ("equatorial") horizontal cross-section of the ellipsoid.

### Step 3: Explain How the Cross-Sections $z = c$ Change for $|c| < 4$
Now let us intersect the ellipsoid with a general horizontal plane $z = c$, where $|c| < 4$ (i.e., $-4 < c < 4$). Substituting $z = c$ into the surface equation gives:
$$\frac{x^2}{9} + \frac{y^2}{4} + \frac{c^2}{16} = 1.$$
Subtracting $\frac{c^2}{16}$ from both sides:
$$\frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{c^2}{16}.$$

Since $|c| < 4$, we have $c^2 < 16$, which means $0 < 1 - \frac{c^2}{16} \le 1$. To put this 2D cross-section equation into canonical ellipse form, we divide both sides by the positive number $1 - \frac{c^2}{16}$:
$$\frac{x^2}{9\left(1 - \frac{c^2}{16}\right)} + \frac{y^2}{4\left(1 - \frac{c^2}{16}\right)} = 1.$$
Equivalently, we can read off the $c$-dependent semiaxes $a(c)$ and $b(c)$:
$$a(c) = 3\sqrt{1 - \frac{c^2}{16}}, \qquad b(c) = 2\sqrt{1 - \frac{c^2}{16}}.$$

**How the Cross-Sections Change as $c$ Varies:**
1. **Shape and Similarity:** For every $c \in (-4, 4)$, the cross-section is an **ellipse** centered at $(0, 0, c)$ in the plane $z = c$. Notice that the ratio of its semiaxes is constant and independent of $c$:
   $$\frac{a(c)}{b(c)} = \frac{3\sqrt{1 - c^2/16}}{2\sqrt{1 - c^2/16}} = \frac{3}{2}.$$
   Thus, all horizontal cross-sections for $|c| < 4$ are **geometrically similar ellipses** with the same aspect ratio $3:2$ (always stretched more along the $x$-direction than the $y$-direction).
2. **Symmetry in $c$:** Because $c$ appears only as $c^2$, the cross-section at height $z = c$ and the cross-section at height $z = -c$ are **identical in size and shape** (symmetric with respect to the $xy$-plane $z = 0$).
3. **Variation of Size from $c = 0$ to $|c| \to 4$:**
   - **At $c = 0$:** The scaling factor $\sqrt{1 - c^2/16} = 1$ is at its **maximum**, giving the largest ellipse with semiaxes $a(0) = 3$ and $b(0) = 2$.
   - **As $|c|$ increases from $0$ toward $4$:** The quantity $1 - \frac{c^2}{16}$ decreases monotonically toward $0$, so the ellipses **shrink continuously** in size.
   - **Boundary behavior at $c = \pm 4$:** When $c = \pm 4$, $1 - \frac{16}{16} = 0$, so $\frac{x^2}{9} + \frac{y^2}{4} = 0 \implies x = 0, y = 0$. The ellipses degenerate into the two single **pole points** $(0, 0, 4)$ and $(0, 0, -4)$.
   - **Outside ($|c| > 4$):** $1 - \frac{c^2}{16} < 0$, so the cross-section is empty (the plane $z = c$ misses the ellipsoid completely).

## Verification and Consistency Checks

Let us compute and verify a specific horizontal cross-section for an intermediate value of $c$, say $c = 2$ (where $|2| < 4$):
1. **Cross-Section Equation at $z = 2$:**
   $$\frac{x^2}{9} + \frac{y^2}{4} = 1 - \frac{2^2}{16} = 1 - \frac{4}{16} = \frac{3}{4}.$$
   Dividing by $\frac{3}{4}$ gives:
   $$\frac{x^2}{9 \cdot \frac{3}{4}} + \frac{y^2}{4 \cdot \frac{3}{4}} = 1 \implies \frac{x^2}{27/4} + \frac{y^2}{3} = 1.$$
   Here $a(2) = \frac{3\sqrt{3}}{2} \approx 2.598 < 3$ and $b(2) = \sqrt{3} \approx 1.732 < 2$, confirming the ellipse is smaller than at $z = 0$ while maintaining the ratio $\frac{a(2)}{b(2)} = \frac{3\sqrt{3}/2}{\sqrt{3}} = \frac{3}{2}$.
2. **Substitute a Vertex of the $z = 2$ Cross-Section Back into the Original Ellipsoid Equation:**
   Take the point $(0, \sqrt{3}, 2)$ on the $z = 2$ cross-section:
   $$\frac{0^2}{9} + \frac{(\sqrt{3})^2}{4} + \frac{2^2}{16} = 0 + \frac{3}{4} + \frac{4}{16} = \frac{3}{4} + \frac{1}{4} = 1. \quad \checkmark$$
