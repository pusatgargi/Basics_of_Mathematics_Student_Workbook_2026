# Problem 11: A Parameter and the Number of Extrema

## Problem Statement

For
$$f_a(x)=x^3-3ax$$
depending on $a$, determine the number of critical points and their character. Separate the parameter cases and justify why the structure of the graph changes.

## Theoretical Background and Concepts

Analyzing a **one-parameter family of functions** $f_a(x)$ teaches how qualitative features of a graph (such as the number and character of critical points) can undergo a sudden structural change—called a **bifurcation**—as the parameter $a \in \mathbb{R}$ varies:

1. **Invariant Properties Across the Family**:
   - **Domain**: $D_{f_a} = \mathbb{R}$ for every $a \in \mathbb{R}$.
   - **Odd Symmetry**: $f_a(-x) = (-x)^3 - 3a(-x) = -(x^3 - 3ax) = -f_a(x)$, so every member of the family is an odd function whose graph is point-symmetric about the origin $(0, 0)$.
   - **End Behavior**: $\lim_{x \to -\infty} f_a(x) = -\infty$ and $\lim_{x \to +\infty} f_a(x) = +\infty$ for every $a \in \mathbb{R}$.
   - **Second Derivative and Inflection Point**: $f_a''(x) = 6x$ is completely independent of $a$: every $f_a$ is strictly concave on $(-\infty, 0)$, strictly convex on $(0, \infty)$, and has a unique inflection point at $(0, 0)$.
2. **Parameter-Dependent Critical Points**:
   - The first derivative $f_a'(x) = 3x^2 - 3a = 3(x^2 - a)$ is a quadratic polynomial whose discriminant is $\Delta = 0^2 - 4(3)(-3a) = 36a$.
   - Depending on the sign of $a$ ($a < 0$, $a = 0$, or $a > 0$), the equation $x^2 = a$ has **zero, one (double), or two simple** real roots.
   - Importantly, by the First Derivative Test, a critical point yields a local extremum **if and only if $f_a'(x)$ changes sign** across it.

## Detailed Step-by-Step Solution

### Step 1: First Derivative and Critical Point Equation

For any real parameter $a \in \mathbb{R}$, differentiating $f_a(x) = x^3 - 3ax$ with respect to $x$ gives:
$$f_a'(x) = 3x^2 - 3a = 3(x^2 - a).$$
A point $x \in \mathbb{R}$ is a critical point of $f_a$ if and only if:
$$f_a'(x) = 0 \iff 3(x^2 - a) = 0 \iff x^2 = a.$$
Because $x^2 \ge 0$ for all $x \in \mathbb{R}$, the number and nature of the solutions to $x^2 = a$ depend on whether $a < 0$, $a = 0$, or $a > 0$.

---

### Step 2: Analysis of the Three Parameter Cases

#### Case 1: $a < 0$

- **Number of Critical Points**: Since $x^2 \ge 0 > a$, the equation $x^2 = a$ has **no real solutions**. Thus, $f_a$ has **$0$ critical points**.
- **Sign of $f_a'(x)$ and Monotonicity**: Because $a < 0$, we have $-a > 0$, so for every $x \in \mathbb{R}$:
  $$f_a'(x) = 3(x^2 - a) \ge -3a > 0.$$
  Hence, $f_a$ is **strictly increasing on all of $\mathbb{R}$** and has **no local extrema**. At the inflection point $(0, 0)$, the tangent line $y = -3ax$ has a strictly positive slope $-3a > 0$.

#### Case 2: $a = 0$

- **Number of Critical Points**: When $a = 0$, the function simplifies to $f_0(x) = x^3$, and its derivative is:
  $$f_0'(x) = 3x^2.$$
  Solving $3x^2 = 0$ gives $x = 0$ (a root of multiplicity $2$). Thus, $f_0$ has **1 critical point**, namely $x = 0$.
- **Sign of $f_0'(x)$ and Character of $x = 0$**:
  For all $x \neq 0$, we have $f_0'(x) = 3x^2 > 0$.

  | Interval / Point | $(-\infty, 0)$ | $x = 0$ | $(0, \infty)$ |
  | :---: | :---: | :---: | :---: |
  | Sign of $f_0'(x) = 3x^2$ | $+$ | $0$ | $+$ |
  | Behavior of $f_0(x) = x^3$ | $\nearrow$ (strictly increasing) | **Horizontal Inflection Point** $f_0(0) = 0$ | $\nearrow$ (strictly increasing) |

  Because $f_0'(x)$ **does not change sign** at $x = 0$, the critical point $x = 0$ is **not a local extremum**; it is a **stationary (horizontal) inflection point** (saddle point of the graph). The function $f_0(x) = x^3$ is **strictly increasing on all of $\mathbb{R}$** and has **$0$ local extrema**.

#### Case 3: $a > 0$

- **Number of Critical Points**: When $a > 0$, the equation $x^2 = a$ has two distinct real roots, which let us factor $f_a'(x)$ completely:
  $$f_a'(x) = 3(x^2 - a) = 3\left(x + \sqrt{a}\right)\left(x - \sqrt{a}\right).$$
  Thus, $f_a$ has **2 critical points**:
  $$x_1 = -\sqrt{a} \qquad \text{and} \qquad x_2 = \sqrt{a}.$$
- **Sign Chart of $f_a'(x)$ and Character of the Critical Points**:
  Since $f_a'(x)$ is an upward-opening quadratic with simple roots at $-\sqrt{a} < \sqrt{a}$:
  - On $\left(-\infty, -\sqrt{a}\right)$: both factors are negative, so $f_a'(x) > 0$ ($f_a$ is **strictly increasing**).
  - On $\left(-\sqrt{a}, \sqrt{a}\right)$: $x + \sqrt{a} > 0$ and $x - \sqrt{a} < 0$, so $f_a'(x) < 0$ ($f_a$ is **strictly decreasing**).
  - On $\left(\sqrt{a}, \infty\right)$: both factors are positive, so $f_a'(x) > 0$ ($f_a$ is **strictly increasing**).

  | Interval / Point | $\left(-\infty, -\sqrt{a}\right)$ | $x = -\sqrt{a}$ | $\left(-\sqrt{a}, \sqrt{a}\right)$ | $x = \sqrt{a}$ | $\left(\sqrt{a}, \infty\right)$ |
  | :---: | :---: | :---: | :---: | :---: | :---: |
  | Sign of $f_a'(x)$ | $+$ | $0$ | $-$ | $0$ | $+$ |
  | Behavior of $f_a(x)$ | $\nearrow$ | **Local Max** $2a\sqrt{a}$ | $\searrow$ | **Local Min** $-2a\sqrt{a}$ | $\nearrow$ |

  - At $x_1 = -\sqrt{a}$: $f_a'(x)$ changes sign from $+$ to $-$ (and $f_a''(-\sqrt{a}) = -6\sqrt{a} < 0$), so $f_a$ has a **strict local maximum** with value:
    $$f_a\left(-\sqrt{a}\right) = \left(-\sqrt{a}\right)^3 - 3a\left(-\sqrt{a}\right) = -a\sqrt{a} + 3a\sqrt{a} = 2a\sqrt{a} = 2a^{3/2} > 0.$$
  - At $x_2 = \sqrt{a}$: $f_a'(x)$ changes sign from $-$ to $+$ (and $f_a''(\sqrt{a}) = 6\sqrt{a} > 0$), so $f_a$ has a **strict local minimum** with value:
    $$f_a\left(\sqrt{a}\right) = \left(\sqrt{a}\right)^3 - 3a\left(\sqrt{a}\right) = a\sqrt{a} - 3a\sqrt{a} = -2a\sqrt{a} = -2a^{3/2} < 0.$$

---

### Step 3: Why the Structure of the Graph Changes

1. **Geometric Shift of the Derivative Parabola**:
   The derivative $f_a'(x) = 3x^2 - 3a$ is a parabola opening upward with vertex at $(0, -3a)$:
   - For $a < 0$, the vertex $(0, -3a)$ lies strictly **above** the $x$-axis, so $f_a'(x) > 0$ everywhere and $f_a$ increases monotonically without ever pausing.
   - At $a = 0$, the vertex touches the $x$-axis tangentially at $(0, 0)$ without crossing below it, so $f_0'(x)$ vanishes at a single instant ($x = 0$) before continuing to increase.
   - For $a > 0$, the vertex $(0, -3a)$ drops **below** the $x$-axis, creating an open interval $\left(-\sqrt{a}, \sqrt{a}\right)$ where $f_a'(x) < 0$. This negative-derivative interval forces the cubic graph to fold back downward between its local maximum at $\left(-\sqrt{a}, 2a^{3/2}\right)$ and its local minimum at $\left(\sqrt{a}, -2a^{3/2}\right)$.
2. **Competition Between $x^3$ and $-3ax$**:
   For large $|x|$, the cubic term $x^3$ always dominates, forcing $f_a(x) \to \pm\infty$ as $x \to \pm\infty$. Near the origin $x = 0$, however, the linear term $-3ax$ dominates ($f_a'(0) = -3a$). When $a \le 0$, the linear term reinforces the upward trend of $x^3$; when $a > 0$, the linear term $-3ax$ pulls the graph downward near the origin ($f_a'(0) = -3a < 0$), creating the S-shaped wave with two turning points.

### Step 4: Summary Table and Comparative ASCII Sketches

| Parameter Case | Critical Points | Local Extrema | Monotonicity on $\mathbb{R}$ |
| :---: | :---: | :---: | :---: |
| $a < 0$ | $0$ | None | Strictly increasing on $\mathbb{R}$ ($f_a'(0) > 0$) |
| $a = 0$ | $1$ ($x = 0$) | None (horizontal inflection at $x = 0$) | Strictly increasing on $\mathbb{R}$ ($f_0'(0) = 0$) |
| $a > 0$ | $2$ ($x = \pm\sqrt{a}$) | Local Max at $-\sqrt{a}$, Local Min at $\sqrt{a}$ | $\nearrow$ on $(-\infty, -\sqrt{a}]$, $\searrow$ on $[-\sqrt{a}, \sqrt{a}]$, $\nearrow$ on $[\sqrt{a}, \infty)$ |

```text
   Case 1: a < 0                   Case 2: a = 0                   Case 3: a > 0
      y                               y                               y
      ^     /                         ^       /                       ^  Max        /
      |    /                          |      /                  2a^1.5+ . *        /
      |   / (slope -3a > 0)           |    .' (slope 0)               |  / \      /
  ----+--*----> x                 ----+---*---> x                 ----+-/---*----/--> x
      | /                             | .'                        -sqrt(a) 0 \  / sqrt(a)
      |/                              | /                             |/      * . . -2a^1.5
     /|                              |/                              /       Min
```

## Verification and Consistency Checks

1. **Concrete Parameter Checks**:
   - Take $a = -1 < 0$: $f_{-1}(x) = x^3 + 3x$, $f_{-1}'(x) = 3(x^2 + 1) \ge 3 > 0$. Indeed, $x_1 < x_2 \implies x_1^3 + 3x_1 < x_2^3 + 3x_2$.
   - Take $a = 0$: $f_0(x) = x^3$, $f_0'(x) = 3x^2 \ge 0$, $f_0(-1) = -1 < f_0(0) = 0 < f_0(1) = 1$, confirming no extremum at $x = 0$.
   - Take $a = 1 > 0$: $f_1(x) = x^3 - 3x$, $f_1'(x) = 3(x - 1)(x + 1)$, with local maximum $f_1(-1) = 2$ and local minimum $f_1(1) = -2$.
2. **Coalescence Limit as $a \to 0^+$**:
   As $a \to 0^+$, the two critical points $x_{1,2} = \pm\sqrt{a} \to 0$ and their extreme values $\pm 2a^{3/2} \to 0$ merge smoothly into the single horizontal inflection point $(0, 0)$ of Case 2 ($a = 0$).
