# Problem 3: Ellipse

## Problem Statement

For
$$\frac{x^2}{25}+\frac{y^2}{9}=1,$$
find the semiaxis lengths, the intercepts with the coordinate axes, and make a sketch. Explain along which axis the ellipse is more stretched and how this is visible in the equation.

## Theoretical Background and Concepts

An **ellipse** centered at the origin $(0,0)$ with axes of symmetry aligned with the coordinate axes has the **canonical equation**:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1,$$
where $a > 0$ and $b > 0$ are positive real constants called the **semiaxis lengths**:
- $a$ is the **horizontal semiaxis** (half the width of the ellipse along the $x$-axis). Since $\frac{y^2}{b^2} \ge 0$, the equation implies $\frac{x^2}{a^2} \le 1$, so $-a \le x \le a$.
- $b$ is the **vertical semiaxis** (half the height of the ellipse along the $y$-axis). Since $\frac{x^2}{a^2} \ge 0$, the equation implies $\frac{y^2}{b^2} \le 1$, so $-b \le y \le b$.

The longer of the two segments $[-a, a]$ (of length $2a$) and $[-b, b]$ (of length $2b$) is called the **major axis**, and the shorter is called the **minor axis**:
- If $a > b$, the ellipse is **horizontally elongated** (stretched along the $x$-axis), with foci at $(\pm c, 0)$ where $c = \sqrt{a^2 - b^2}$.
- If $b > a$, the ellipse is **vertically elongated** (stretched along the $y$-axis), with foci at $(0, \pm c)$ where $c = \sqrt{b^2 - a^2}$.
- If $a = b$, the ellipse has equal horizontal and vertical scales and becomes a **circle** of radius $r = a = b$.

From a scaling perspective, making the variable substitution $u = \frac{x}{a}$ and $v = \frac{y}{b}$ transforms the unit circle $u^2 + v^2 = 1$ into $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ by stretching the plane by a factor of $a$ horizontally and a factor of $b$ vertically.

## Detailed Step-by-Step Solution

### Step 1: Find the Semiaxis Lengths
We compare the given equation
$$\frac{x^2}{25} + \frac{y^2}{9} = 1$$
with the canonical equation of an ellipse:
$$\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1.$$
Matching the denominators under $x^2$ and $y^2$:
$$a^2 = 25 \implies a = \sqrt{25} = 5 \quad (\text{since } a > 0),$$
$$b^2 = 9 \implies b = \sqrt{9} = 3 \quad (\text{since } b > 0).$$
Therefore:
- **Horizontal semiaxis length (semi-major axis):** $a = 5$ (full horizontal width $2a = 10$).
- **Vertical semiaxis length (semi-minor axis):** $b = 3$ (full vertical height $2b = 6$).

### Step 2: Find the Intercepts with the Coordinate Axes
1. **Intercepts with the $x$-axis ($Ox$):**
   Points on the $x$-axis have $y = 0$. Substituting $y = 0$ into the equation gives:
   $$\frac{x^2}{25} + \frac{0^2}{9} = 1 \implies \frac{x^2}{25} = 1 \implies x^2 = 25 \implies x = \pm 5.$$
   Thus, the **$x$-intercepts (major vertices)** are:
   $$A_1 = (-5, 0) \quad \text{and} \quad A_2 = (5, 0).$$

2. **Intercepts with the $y$-axis ($Oy$):**
   Points on the $y$-axis have $x = 0$. Substituting $x = 0$ into the equation gives:
   $$\frac{0^2}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 \implies y^2 = 9 \implies y = \pm 3.$$
   Thus, the **$y$-intercepts (minor vertices / co-vertices)** are:
   $$B_1 = (0, -3) \quad \text{and} \quad B_2 = (0, 3).$$

### Step 3: Explain Along Which Axis the Ellipse Is More Stretched
The ellipse is **more stretched along the $x$-axis (horizontal axis)**.

**How this is visible directly in the equation:**
1. **Comparison of Denominators:** In the canonical form $\frac{x^2}{25} + \frac{y^2}{9} = 1$, the denominator under $x^2$ is $25$, which is strictly larger than the denominator $9$ under $y^2$ ($25 > 9$, so $a = 5 > b = 3$).
2. **Range of Permissible Values:** Because both $\frac{x^2}{25} \ge 0$ and $\frac{y^2}{9} \ge 0$ must sum to $1$, we have:
   $$\frac{x^2}{25} \le 1 \implies |x| \le 5, \qquad \frac{y^2}{9} \le 1 \implies |y| \le 3.$$
   For the fraction $\frac{x^2}{25}$ to reach $1$, $x$ can grow up to $\pm 5$, whereas $y$ can only grow up to $\pm 3$ before $\frac{y^2}{9}$ reaches $1$.
3. **Geometric Scaling Interpretation:** Starting from the unit circle $u^2 + v^2 = 1$, where $u = x/5$ and $v = y/3$, we have $x = 5u$ and $y = 3v$. The unit circle is stretched by a factor of $5$ along the $x$-axis and only by a factor of $3$ along the $y$-axis.

### Step 4: Sketch of the Ellipse and Geometric Description
- **Center:** $(0,0)$.
- **Vertices:** $(-5,0)$ and $(5,0)$ on the horizontal major axis; $(0,-3)$ and $(0,3)$ on the vertical minor axis.
- **Foci:** Since $c = \sqrt{a^2 - b^2} = \sqrt{25 - 9} = \sqrt{16} = 4$, the two foci lie on the $x$-axis at $F_1 = (-4, 0)$ and $F_2 = (4, 0)$.
- **Bounding Box:** The ellipse is inscribed smoothly inside the rectangle $[-5, 5] \times [-3, 3]$.

```text
                        y
                        ^
                        |
                      3 + (0,3)
               . - ~ ~ ~ ~ ~ ~ - .
          . '           |           ' .
       .                |                .
  ----+---+-------------+-------------+---+-----> x
    -5   -4             |0            4   5
  (-5,0)  F1            |             F2  (5,0)
       .                |                .
          ' .           |           . '
               ' - . _ _ _ _ _ . - '
                     -3 + (0,-3)
                        |
```

## Verification and Consistency Checks

1. **Intercept Substitution Check:**
   - Substitute $(\pm 5, 0)$: $\frac{(\pm 5)^2}{25} + \frac{0^2}{9} = \frac{25}{25} + 0 = 1$. $\checkmark$
   - Substitute $(0, \pm 3)$: $\frac{0^2}{25} + \frac{(\pm 3)^2}{9} = 0 + \frac{9}{9} = 1$. $\checkmark$

2. **Non-Intercept Point Check (at the Focus Coordinate $x = 4$):**
   Let us find the $y$-coordinates on the ellipse directly above and below the focus $F_2(4, 0)$:
   $$\frac{4^2}{25} + \frac{y^2}{9} = 1 \implies \frac{16}{25} + \frac{y^2}{9} = 1 \implies \frac{y^2}{9} = 1 - \frac{16}{25} = \frac{9}{25} \implies y^2 = \frac{81}{25} \implies y = \pm \frac{9}{5} = \pm 1.8.$$
   Substituting $(4, 1.8)$ back into the original equation:
   $$\frac{4^2}{25} + \frac{(9/5)^2}{9} = \frac{16}{25} + \frac{81/25}{9} = \frac{16}{25} + \frac{9}{25} = \frac{25}{25} = 1. \quad \checkmark$$

3. **Focal Distance Property Check:**
   For any point $P$ on the ellipse, the sum of distances to the two foci $F_1(-4,0)$ and $F_2(4,0)$ must equal $2a = 10$. Testing $B_2(0,3)$:
   $$|B_2 F_1| + |B_2 F_2| = \sqrt{(0 - (-4))^2 + (3 - 0)^2} + \sqrt{(0 - 4)^2 + (3 - 0)^2} = \sqrt{16 + 9} + \sqrt{16 + 9} = 5 + 5 = 10 = 2a. \quad \checkmark$$
