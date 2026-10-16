# Problem 6: Average Value of a Function

## Problem Statement

Compute the average value of the function
$$
f(x)=x^2
$$
on the interval $[0,3]$.

Find a point $c\in[0,3]$ for which $f(c)$ is equal to this average value, and interpret the result geometrically.

## Theoretical Background and Concepts

1. **Average (Mean) Value of a Continuous Function**:
   For a finite set of $n$ numbers $y_1, y_2, \dots, y_n$, the arithmetic mean is $\frac{1}{n}\sum_{i=1}^n y_i$. Generalizing this concept to a continuous function $f : [a, b] \to \mathbb{R}$ by sampling $n$ equally spaced points with step $\Delta x = \frac{b-a}{n}$ gives:
   $$
   \frac{1}{n}\sum_{i=1}^n f(x_i) = \frac{1}{b-a}\sum_{i=1}^n f(x_i)\,\Delta x \xrightarrow{n \to \infty} \frac{1}{b-a}\int_a^b f(x)\,dx.
   $$
   Accordingly, the **average value** $f_{\text{avg}}$ of $f$ on $[a, b]$ is defined as:
   $$
   f_{\text{avg}} = \frac{1}{b - a}\int_a^b f(x)\,dx.
   $$

2. **Mean Value Theorem for Integrals**:
   If $f$ is continuous on the closed interval $[a, b]$, there exists at least one point $c \in [a, b]$ (in fact, $c \in (a, b)$) such that $f$ attains its average value at $c$:
   $$
   f(c) = f_{\text{avg}} = \frac{1}{b - a}\int_a^b f(x)\,dx \iff \int_a^b f(x)\,dx = f(c)(b - a).
   $$

3. **Geometric Interpretation**:
   For a non-negative function $f(x) \ge 0$, the identity $\int_a^b f(x)\,dx = f_{\text{avg}} \cdot (b - a)$ means that the area under the curve $y = f(x)$ over $[a, b]$ is equal to the area of a **rectangle** with base $[a, b]$ (width $b - a$) and constant height $h = f_{\text{avg}} = f(c)$.

## Detailed Step-by-Step Solution

### Step 1: Computing the Average Value of $f(x) = x^2$ on $[0, 3]$

Applying the average value formula on the interval $[a, b] = [0, 3]$ (where the interval length is $b - a = 3 - 0 = 3$):
$$
f_{\text{avg}} = \frac{1}{3 - 0}\int_0^3 x^2\,dx = \frac{1}{3}\int_0^3 x^2\,dx.
$$
Using the power rule $\int x^2\,dx = \frac{x^3}{3} + C$ and the Fundamental Theorem of Calculus:
$$
\begin{aligned}
f_{\text{avg}} &= \frac{1}{3}\left[\frac{x^3}{3}\right]_0^3 \\
&= \frac{1}{3}\left(\frac{3^3}{3} - \frac{0^3}{3}\right) \\
&= \frac{1}{3}\left(\frac{27}{3} - 0\right) \\
&= \frac{1}{3} \cdot 9 = 3.
\end{aligned}
$$
Thus, the average value of $f(x) = x^2$ on $[0, 3]$ is:
$$
f_{\text{avg}} = 3.
$$

---

### Step 2: Finding the Point $c \in [0, 3]$ Where $f(c) = f_{\text{avg}}$

We require a point $c \in [0, 3]$ such that:
$$
f(c) = 3 \iff c^2 = 3.
$$
Taking square roots gives the algebraic solutions:
$$
c = \sqrt{3} \quad \text{or} \quad c = -\sqrt{3}.
$$
Since the problem specifies $c \in [0, 3]$ and $-\sqrt{3} < 0 \notin [0, 3]$, while $0 < \sqrt{3} \approx 1.7321 < 3$, the unique point in the interval is:
$$
c = \sqrt{3} \approx 1.7321.
$$

---

### Step 3: Geometric Interpretation

1. **Equal-Area Rectangle Principle**:
   The definite integral $\int_0^3 x^2\,dx = 9$ represents the area of the region under the parabola $y = x^2$ above the interval $[0, 3]$. The rectangle with the same base $[0, 3]$ (width $3$) and height equal to the average value $f(c) = f(\sqrt{3}) = 3$ has area:
   $$
   \text{Area}_{\text{rect}} = \text{width} \times \text{height} = (3 - 0) \times f(\sqrt{3}) = 3 \times 3 = 9.
   $$
   Thus, $f_{\text{avg}} = 3$ is the exact constant height at which a flat horizontal line $y = 3$ encloses the same area over $[0, 3]$ as the curved parabola $y = x^2$.

2. **Balancing of Areas Above and Below the Level $y = 3$**:
   The horizontal line $y = 3$ intersects the parabola $y = x^2$ at the point $(c, f(c)) = (\sqrt{3}, 3)$.
   - On $[0, \sqrt{3}]$, the curve $y = x^2$ lies **below** the line $y = 3$, leaving a deficit area of $\int_0^{\sqrt{3}} (3 - x^2)\,dx = \left[3x - \frac{x^3}{3}\right]_0^{\sqrt{3}} = 3\sqrt{3} - \sqrt{3} = 2\sqrt{3}$.
   - On $[\sqrt{3}, 3]$, the curve $y = x^2$ lies **above** the line $y = 3$, creating a surplus area of $\int_{\sqrt{3}}^3 (x^2 - 3)\,dx = \left[\frac{x^3}{3} - 3x\right]_{\sqrt{3}}^3 = (9 - 9) - (\sqrt{3} - 3\sqrt{3}) = 2\sqrt{3}$.
   If the region under $y = x^2$ were made of water in a container of width $3$, it would settle to a flat level of height $y = 3$, with the peak above $y = 3$ on $[\sqrt{3}, 3]$ exactly filling the trough below $y = 3$ on $[0, \sqrt{3}]$.

## Verification and Consistency Checks

1. **Bounds on the Average Value**:
   Since $f(x) = x^2$ is strictly increasing on $[0, 3]$, its minimum on $[0, 3]$ is $f(0) = 0$ and its maximum is $f(3) = 9$. The average value must satisfy:
   $$
   0 = \min_{x\in[0,3]} f(x) < f_{\text{avg}} < \max_{x\in[0,3]} f(x) = 9,
   $$
   which holds for $f_{\text{avg}} = 3$.

2. **Convexity Comparison with the Midpoint**:
   Because $f(x) = x^2$ is strictly convex ($f''(x) = 2 > 0$), Jensen's inequality implies that the average value on $[0, 3]$ exceeds the value at the midpoint $x_{\text{mid}} = 1.5$:
   $$
   f(1.5) = 2.25 < f_{\text{avg}} = 3 < \frac{f(0) + f(3)}{2} = 4.5,
   $$
   and consequently the mean-value point $c = \sqrt{3} \approx 1.7321$ lies to the right of the midpoint $1.5$.
