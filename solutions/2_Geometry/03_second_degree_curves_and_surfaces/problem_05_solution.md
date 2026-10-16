# Problem 5: Hyperbola and Asymptotes

## Problem Statement

For
$$\frac{x^2}{16}-\frac{y^2}{9}=1,$$
find the intercepts with the $x$-axis, the asymptotes, and make a sketch. Explain why the asymptotes describe the behavior of the curve far from the center.

## Theoretical Background and Concepts

A **hyperbola** centered at the origin $(0,0)$ with its transverse axis along the $x$-axis has the **canonical equation**:
$$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1 \quad (a > 0, \; b > 0).$$

Its primary geometric features are:
1. **Center:** The origin $(0,0)$, which is the center of symmetry of the curve.
2. **Transverse Axis and Vertices:** Solving for $x^2$ gives $\frac{x^2}{a^2} = 1 + \frac{y^2}{b^2} \ge 1$, so $|x| \ge a$. The curve exists only for $x \le -a$ (left branch) and $x \ge a$ (right branch). It intersects the $x$-axis at the two **vertices** $(-a, 0)$ and $(a, 0)$, and it does not intersect the $y$-axis at all.
3. **Semi-axes and Reference Rectangle:** The parameter $a$ is the **semi-transverse axis**, and $b$ is the **semi-conjugate axis**. The rectangle $[-a, a] \times [-b, b]$ with corners $(\pm a, \pm b)$ is called the **central reference rectangle**.
4. **Asymptotes:** The diagonals of the central reference rectangle are the two straight lines passing through the origin:
   $$y = \frac{b}{a}x \quad \text{and} \quad y = -\frac{b}{a}x.$$
   Algebraically, replacing the constant $1$ on the right-hand side of the canonical equation with $0$ gives the combined equation of the asymptotes:
   $$\frac{x^2}{a^2} - \frac{y^2}{b^2} = 0 \iff \left(\frac{x}{a} - \frac{y}{b}\right)\left(\frac{x}{a} + \frac{y}{b}\right) = 0 \iff y = \pm \frac{b}{a}x.$$

## Detailed Step-by-Step Solution

### Step 1: Identify the Parameters $a$ and $b$
Comparing the given equation
$$\frac{x^2}{16} - \frac{y^2}{9} = 1$$
with the canonical form $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$:
$$a^2 = 16 \implies a = \sqrt{16} = 4 \quad (a > 0),$$
$$b^2 = 9 \implies b = \sqrt{9} = 3 \quad (b > 0).$$
The center of the hyperbola is $(0,0)$, the semi-transverse axis is $a = 4$, and the semi-conjugate axis is $b = 3$.

### Step 2: Find the Intercepts with the $x$-Axis
To find the intercepts with the $x$-axis ($Ox$), we set $y = 0$ in the equation of the hyperbola:
$$\frac{x^2}{16} - \frac{0^2}{9} = 1 \implies \frac{x^2}{16} = 1 \implies x^2 = 16 \implies x = \pm 4.$$
Thus, the **$x$-intercepts (vertices)** of the hyperbola are:
$$V_1 = (-4, 0) \quad \text{and} \quad V_2 = (4, 0).$$
*(Note: Setting $x = 0$ gives $-\frac{y^2}{9} = 1 \implies y^2 = -9$, confirming there are no $y$-intercepts.)*

### Step 3: Find the Equations of the Asymptotes
For a hyperbola in canonical form $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$, the asymptotes are given by setting the right-hand side to $0$:
$$\frac{x^2}{16} - \frac{y^2}{9} = 0 \implies \frac{y^2}{9} = \frac{x^2}{16} \implies y^2 = \frac{9}{16}x^2.$$
Taking the square root of both sides yields:
$$y = \pm \frac{b}{a}x = \pm \frac{3}{4}x.$$
Thus, the two **asymptotes** are the straight lines:
$$y = \frac{3}{4}x \quad \text{and} \quad y = -\frac{3}{4}x.$$

### Step 4: Explain Why the Asymptotes Describe the Behavior Far from the Center
Let us solve the hyperbola equation $\frac{x^2}{16} - \frac{y^2}{9} = 1$ explicitly for $y$ in terms of $x$ (for $|x| \ge 4$):
$$\frac{y^2}{9} = \frac{x^2}{16} - 1 = \frac{x^2}{16}\left(1 - \frac{16}{x^2}\right) \implies y^2 = \frac{9}{16}x^2\left(1 - \frac{16}{x^2}\right).$$
Taking the square root gives:
$$y = \pm \frac{3}{4}|x|\sqrt{1 - \frac{16}{x^2}}, \quad \text{or equivalently} \quad y = \pm \frac{3}{4}x\sqrt{1 - \frac{16}{x^2}}.$$

Now consider what happens when a point $(x, y)$ on the hyperbola moves **far from the center** $(0,0)$, meaning $|x| \to \infty$:
1. **Ratio Comparison (Relative Behavior):**
   As $|x| \to \infty$, the fraction $\frac{16}{x^2} \to 0$. Consequently, the square-root factor approaches $1$:
   $$\lim_{|x| \to \infty} \sqrt{1 - \frac{16}{x^2}} = \sqrt{1 - 0} = 1, \quad \text{so} \quad \frac{y_{\text{hyperbola}}}{y_{\text{asymptote}}} = \sqrt{1 - \frac{16}{x^2}} \xrightarrow{|x| \to \infty} 1.$$
   Intuitively, in the equation $\frac{x^2}{16} - \frac{y^2}{9} = 1$, when $x^2$ and $y^2$ are millions or billions, the constant $1$ on the right-hand side is negligible compared to $\frac{x^2}{16}$ and $\frac{y^2}{9}$, so $\frac{x^2}{16} - \frac{y^2}{9} \approx 0$.

2. **Exact Vertical Distance Vanishes (Absolute Convergence):**
   Even stronger, the vertical distance between the hyperbola and its asymptote in the first quadrant ($x \ge 4, y \ge 0$) goes to **zero** as $x \to +\infty$. Using the conjugate identity $A - B = \frac{A^2 - B^2}{A + B}$:
   $$y_{\text{asymptote}} - y_{\text{hyperbola}} = \frac{3}{4}x - \frac{3}{4}\sqrt{x^2 - 16} = \frac{3}{4}\left(x - \sqrt{x^2 - 16}\right) = \frac{3}{4} \cdot \frac{x^2 - (x^2 - 16)}{x + \sqrt{x^2 - 16}} = \frac{12}{x + \sqrt{x^2 - 16}}.$$
   As $x \to +\infty$, the denominator $x + \sqrt{x^2 - 16} \to +\infty$, so:
   $$\lim_{x \to +\infty} \left(\frac{3}{4}x - \frac{3}{4}\sqrt{x^2 - 16}\right) = 0.$$
   Moreover, since $\sqrt{x^2 - 16} < x$, we always have $|y_{\text{hyperbola}}| < |y_{\text{asymptote}}|$, meaning the branches of the hyperbola stay strictly inside the sector bounded by the asymptotes while getting arbitrarily close to them as $|x| \to \infty$.

### Step 5: Coordinate Sketch and Geometric Description
- **Center:** $(0,0)$.
- **Reference Rectangle:** Bounded by $x = \pm 4$ and $y = \pm 3$, with corners at $(\pm 4, \pm 3)$.
- **Asymptotes:** The diagonals $y = \frac{3}{4}x$ and $y = -\frac{3}{4}x$ passing through $(0,0)$ and the four corners $(\pm 4, \pm 3)$ of the reference rectangle.
- **Vertices and Branches:** Left branch has vertex $(-4,0)$ and opens leftward for $x \le -4$; right branch has vertex $(4,0)$ and opens rightward for $x \ge 4$.
- **Foci:** $c = \sqrt{a^2 + b^2} = \sqrt{16 + 9} = 5$, so the foci are at $(-5,0)$ and $(5,0)$.

```text
       \             y             /
        \            ^            /  y = (3/4)x
    .    \           |           /    .
     .    \        3 +---.---.  /    .
      .    \     .---|---.   | /    .
       .    \    |   |   |   |/    .
  ------+----*---+---+---+---*----+------> x
       -4 (-4,0) |   |0  |  (4,0) 4
       .    /    |   |   |   |\    .
      .    /     '---|---'   | \    .
     .    /       -3 +---'---'  \    .
    .    /           |           \    .
        /            |            \  y = -(3/4)x
       /                           \
```

## Verification and Consistency Checks

1. **Check the $x$-Intercepts:**
   Substitute $V_1(-4,0)$ and $V_2(4,0)$ into $\frac{x^2}{16} - \frac{y^2}{9} = 1$:
   $$\frac{(\pm 4)^2}{16} - \frac{0^2}{9} = \frac{16}{16} - 0 = 1. \quad \checkmark$$

2. **Check a Point on the Hyperbola and Compare with the Asymptote:**
   Set $x = 5$ (the $x$-coordinate of the right focus):
   $$\frac{5^2}{16} - \frac{y^2}{9} = 1 \implies \frac{25}{16} - 1 = \frac{y^2}{9} \implies \frac{y^2}{9} = \frac{9}{16} \implies y^2 = \frac{81}{16} \implies y = \pm \frac{9}{4} = \pm 2.25.$$
   - Substituting $(5, 2.25)$ back into the original equation:
     $$\frac{25}{16} - \frac{(9/4)^2}{9} = \frac{25}{16} - \frac{81/16}{9} = \frac{25}{16} - \frac{9}{16} = \frac{16}{16} = 1. \quad \checkmark$$
   - Compare with the asymptote value at $x = 5$: $y_{\text{asymptote}} = \frac{3}{4}(5) = 3.75 > 2.25$.
   - Farther out, at $x = 20$: $y_{\text{hyperbola}} = \frac{3}{4}\sqrt{20^2 - 16} = \frac{3}{4}\sqrt{384} \approx 14.697$, while $y_{\text{asymptote}} = \frac{3}{4}(20) = 15$. The gap shrinks from $1.50$ at $x=5$ to just $0.303$ at $x=20$, illustrating convergence to the asymptote.
