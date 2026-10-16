# Problem 7: Classifying a Second-Degree Equation

## Problem Statement

Determine the type of object described by:
1. $4x^2+9y^2=36$,
2. $x^2-y^2=1$,
3. $x^2-4y=0$,
4. $x^2+y^2+1=0$.

In the last case, explain why there are no real points.

## Theoretical Background and Concepts

A second-degree algebraic equation in two real variables $(x, y) \in \mathbb{R}^2$ without an $xy$ cross-term has the form:
$$Ax^2 + By^2 + Cx + Dy + E = 0.$$
By isolating the quadratic terms or completing the square, we can classify the geometric set of real solutions $(x, y) \in \mathbb{R}^2$:

1. **Ellipse (or Circle):** Both $A$ and $B$ are non-zero and have the **same sign** ($AB > 0$). When written as $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$, a sum of two positive squares equals $1$. If $a \neq b$, it is an **ellipse**; if $a = b$, it is a **circle**.
2. **Hyperbola:** Both $A$ and $B$ are non-zero and have **opposite signs** ($AB < 0$). When written as $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$ (or $\frac{y^2}{b^2} - \frac{x^2}{a^2} = 1$), a difference of two squares equals $1$. When $a = b$, it is called a **rectangular (or equilateral) hyperbola** because its asymptotes $y = \pm x$ are perpendicular.
3. **Parabola:** Exactly **one** of $A$ or $B$ is zero ($AB = 0$, with $A$ and $B$ not both zero), and the other variable appears linearly ($x^2 = 2py$ or $y^2 = 2px$).
4. **Degenerate or Empty Cases:** Not every second-degree equation produces a standard non-degenerate curve in $\mathbb{R}^2$:
   - If a sum of squares equals zero, $x^2 + y^2 = 0$, the solution set degenerates to a **single point** $(0,0)$.
   - If a difference of squares equals zero, $x^2 - y^2 = 0$, the solution set factors into a **pair of intersecting lines** $y = \pm x$.
   - If a sum of squares equals a negative number, $x^2 + y^2 = -k$ with $k > 0$, the solution set in $\mathbb{R}^2$ is the **empty set** $\varnothing$ (sometimes called an *imaginary circle* or *empty locus* over the reals).

## Detailed Step-by-Step Solution

---

### Equation 1: $4x^2 + 9y^2 = 36$

#### Step 1: Reduce to Canonical Form
Both $x^2$ and $y^2$ appear with positive coefficients ($4 > 0$ and $9 > 0$), and the right-hand side is positive ($36 > 0$). To put the equation into canonical form, divide both sides by $36$:
$$\frac{4x^2}{36} + \frac{9y^2}{36} = \frac{36}{36}$$
$$\frac{x^2}{9} + \frac{y^2}{4} = 1.$$

#### Step 2: Classify the Object and State Its Features
This has the canonical form $\frac{x^2}{a^2} + \frac{y^2}{b^2} = 1$ with:
$$a^2 = 9 \implies a = 3, \qquad b^2 = 4 \implies b = 2.$$
Because both squared terms are positive, the right-hand side is $1$, and the semiaxes are unequal ($a = 3 \neq b = 2$), the object is an **ellipse**:
- **Type:** **Ellipse** centered at the origin $(0,0)$.
- **Semiaxes:** Horizontal semi-major axis $a = 3$ (vertices at $(\pm 3, 0)$); vertical semi-minor axis $b = 2$ (co-vertices at $(0, \pm 2)$).

---

### Equation 2: $x^2 - y^2 = 1$

#### Step 1: Compare with Canonical Form
The equation can be written explicitly with denominators $a^2 = 1$ and $b^2 = 1$ as:
$$\frac{x^2}{1^2} - \frac{y^2}{1^2} = 1.$$

#### Step 2: Classify the Object and State Its Features
Both $x^2$ and $y^2$ are present, but they have **opposite signs** ($+x^2$ and $-y^2$), and their difference equals $+1$. This matches the canonical equation of a **hyperbola** $\frac{x^2}{a^2} - \frac{y^2}{b^2} = 1$:
- **Type:** **Hyperbola** (specifically, an **equilateral / rectangular hyperbola** since $a = b = 1$).
- **Center and Orientation:** Centered at $(0,0)$, opening left and right along the $x$-axis.
- **Vertices:** $(-1, 0)$ and $(1, 0)$.
- **Asymptotes:** $y = \pm \frac{b}{a}x = \pm x$ (perpendicular lines at $45^\circ$ to the axes).

---

### Equation 3: $x^2 - 4y = 0$

#### Step 1: Isolate the Quadratic Term
Adding $4y$ to both sides puts the equation into canonical form:
$$x^2 = 4y \quad \left(\text{or equivalently } y = \frac{1}{4}x^2\right).$$

#### Step 2: Classify the Object and State Its Features
Here, only one variable is squared ($x^2$), while the second variable ($y$) appears only to the first power ($4y$). This matches the canonical equation of a vertical **parabola** $x^2 = 2py = 4fy$:
- **Type:** **Parabola**.
- **Vertex:** $(0,0)$.
- **Axis of Symmetry:** The vertical $y$-axis ($x = 0$).
- **Opening Direction:** Opens **upward** (in the positive $y$-direction, since $y = \frac{x^2}{4} \ge 0$ for all $x \in \mathbb{R}$).
- **Focus and Directrix:** $4f = 4 \implies f = 1$, so the focus is at $(0, 1)$ and the directrix is $y = -1$.

---

### Equation 4: $x^2 + y^2 + 1 = 0$

#### Step 1: Rearrange the Equation
Subtracting $1$ from both sides yields:
$$x^2 + y^2 = -1.$$

#### Step 2: Classify the Object and Explain Why There Are No Real Points
- **Type:** **Empty set** $\varnothing$ in the real plane $\mathbb{R}^2$ (no real geometric points; often called an *imaginary circle*).
- **Explanation of Why There Are No Real Points:**
  1. **Algebraic Order Property of Real Squares:** For any real number $u \in \mathbb{R}$, its square is always non-negative: $u^2 \ge 0$ (because the product of two positive numbers is positive, the product of two negative numbers is positive, and $0^2 = 0$).
  2. **Non-Negativity of a Sum of Squares:** Consequently, for any pair of real coordinates $(x, y) \in \mathbb{R}^2$, we have:
     $$x^2 \ge 0 \quad \text{and} \quad y^2 \ge 0 \implies x^2 + y^2 \ge 0.$$
  3. **Strict Positivity of the Left-Hand Side:** Adding $1$ to both sides of $x^2 + y^2 \ge 0$ shows that for **every** point $(x, y) \in \mathbb{R}^2$:
     $$x^2 + y^2 + 1 \ge 0 + 1 = 1 > 0.$$
     Since the left-hand side $x^2 + y^2 + 1$ has a minimum possible value of $1$ (achieved at $(x, y) = (0,0)$), it can **never** equal $0$. Equivalently, in $x^2 + y^2 = -1$, a non-negative quantity ($x^2 + y^2 \ge 0$) cannot equal a negative number ($-1 < 0$). Therefore, no real pair $(x, y) \in \mathbb{R}^2$ satisfies the equation.

---

### Summary Classification Table

| # | Original Equation | Canonical Form | Classification | Key Geometric Features |
| :--- | :--- | :--- | :--- | :--- |
| **1** | $4x^2 + 9y^2 = 36$ | $\frac{x^2}{9} + \frac{y^2}{4} = 1$ | **Ellipse** | Center $(0,0)$, semiaxes $a=3, b=2$ |
| **2** | $x^2 - y^2 = 1$ | $\frac{x^2}{1} - \frac{y^2}{1} = 1$ | **Hyperbola** (rectangular) | Center $(0,0)$, vertices $(\pm 1, 0)$, asymptotes $y=\pm x$ |
| **3** | $x^2 - 4y = 0$ | $x^2 = 4y$ | **Parabola** | Vertex $(0,0)$, opens upward along $y$-axis |
| **4** | $x^2 + y^2 + 1 = 0$ | $x^2 + y^2 = -1$ | **Empty Set** $\varnothing$ in $\mathbb{R}^2$ | No real points since $x^2+y^2 \ge 0 > -1$ |

## Verification and Consistency Checks

Let us test specific real points on Equations 1–3 and verify the strict positivity bound on Equation 4:

1. **Equation 1 ($4x^2 + 9y^2 = 36$):**
   - At $(3, 0)$: $4(3)^2 + 9(0)^2 = 4(9) + 0 = 36$. $\checkmark$
   - At $(0, 2)$: $4(0)^2 + 9(2)^2 = 0 + 9(4) = 36$. $\checkmark$
2. **Equation 2 ($x^2 - y^2 = 1$):**
   - At $(\pm 1, 0)$: $(\pm 1)^2 - 0^2 = 1$. $\checkmark$
   - At $(\sqrt{2}, 1)$: $(\sqrt{2})^2 - 1^2 = 2 - 1 = 1$. $\checkmark$
3. **Equation 3 ($x^2 - 4y = 0$):**
   - At $(0, 0)$: $0^2 - 4(0) = 0$. $\checkmark$
   - At $(\pm 2, 1)$: $(\pm 2)^2 - 4(1) = 4 - 4 = 0$. $\checkmark$
4. **Equation 4 ($x^2 + y^2 + 1 = 0$):**
   - At $(0, 0)$: $0^2 + 0^2 + 1 = 1 \neq 0$.
   - At $(\pm 1, \pm 1)$: $(\pm 1)^2 + (\pm 1)^2 + 1 = 1 + 1 + 1 = 3 \neq 0$.
   In all cases, $x^2 + y^2 + 1 \ge 1 > 0$, confirming the solution set in $\mathbb{R}^2$ is empty.
