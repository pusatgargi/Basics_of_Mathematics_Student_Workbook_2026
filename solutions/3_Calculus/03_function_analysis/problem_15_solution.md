# Problem 15: Find the Error in the Monotonicity Analysis

## Problem Statement

For the function
$$f(x)=x^3-3x$$
the derivative was correctly computed as
$$f'(x)=3(x-1)(x+1).$$

However, a student wrote the following conclusion:

> The derivative is positive between its zeros and negative outside them. Therefore, the function is decreasing on $(-\infty,-1)\cup(1,\infty)$, increasing on $(-1,1)$, has a local minimum at $x=-1$, and a local maximum at $x=1$.

1. Without differentiating again, explain why merely identifying the zeros of the derivative does not justify the stated sign chart, and find the error in the student's reasoning.
2. Construct the correct sign chart for $f'(x)$.
3. Give the correct intervals of monotonicity and the character of the extrema.
4. In each of the three intervals, choose one simple test point and show that the sign of the derivative confirms your classification.

## Theoretical Background and Concepts

Constructing a valid monotonicity analysis from a factored derivative $f'(x)$ requires understanding what determines the sign of a polynomial across the intervals separated by its roots:

1. **Role of Zeros vs. Leading Coefficient / Factor Signs**:
   - The real roots $x_1 < x_2 < \dots < x_k$ of a continuous derivative $f'(x)$ identify **only the partition points** where $f'(x) = 0$ and where the sign of $f'(x)$ *can* change.
   - By themselves, the roots $x = -1$ and $x = 1$ do **not** determine whether $f'(x)$ is positive or negative on a given interval: for example, $p(x) = +3(x - 1)(x + 1)$ and $q(x) = -3(x - 1)(x + 1)$ have the **exact same zeros** ($x = -1$ and $x = 1$), yet they have **opposite signs** on every interval!
2. **Sign of a Quadratic $f'(x) = A(x - x_1)(x - x_2)$ ($x_1 < x_2$)**:
   - The sign pattern is controlled by the **leading coefficient $A \neq 0$** (or equivalently by evaluating the signs of the individual factors $(x - x_1)$ and $(x - x_2)$ on each interval):
     - If **$A > 0$** (parabola opens **upward**, $\cup$): $f'(x) > 0$ **outside** the roots on $(-\infty, x_1) \cup (x_2, \infty)$, and $f'(x) < 0$ **between** the roots on $(x_1, x_2)$.
     - If **$A < 0$** (parabola opens **downward**, $\cap$): $f'(x) < 0$ **outside** the roots on $(-\infty, x_1) \cup (x_2, \infty)$, and $f'(x) > 0$ **between** the roots on $(x_1, x_2)$.
3. **Propagation of a Sign-Chart Error**:
   If the signs of $f'(x)$ are inverted on every interval, then every increasing interval is misclassified as decreasing, every decreasing interval is misclassified as increasing, every local maximum ($+$ to $-$) is misclassified as a local minimum ($-$ to $+$), and vice versa.

## Detailed Step-by-Step Solution

### Part 1: Why Identifying Zeros Is Insufficient and Diagnosing the Student's Error

1. **Why Merely Finding the Zeros Does Not Justify a Sign Chart**:
   Knowing that $f'(x) = 0$ at $x = -1$ and $x = 1$ tells us only that the real line $\mathbb{R}$ is divided into the three open intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$, and that $f'(x)$ maintains a constant sign on each of these three intervals (by the Intermediate Value Theorem, since $f'$ is continuous). However, **the zeros alone carry no information about whether $f'(x)$ is positive or negative on any interval**. To determine the actual signs, one must also inspect:
   - the **sign of the leading coefficient** of $f'(x)$, or
   - the **signs of each factor** $3$, $(x - 1)$, and $(x + 1)$ in each interval, or
   - a **test point** in each interval.

2. **The Exact Error in the Student's Reasoning**:
   - In $f'(x) = 3(x - 1)(x + 1) = 3x^2 - 3$, the leading coefficient is **$A = +3 > 0$**, so the graph of the quadratic $y = f'(x)$ is a parabola opening **upward**.
   - An upward-opening parabola with two distinct roots is **negative between its zeros** $(-1, 1)$ (where it dips below the $x$-axis) and **positive outside its zeros** $(-\infty, -1) \cup (1, \infty)$ (where its arms rise above the $x$-axis).
   - **The student reversed the sign rule for a quadratic with positive leading coefficient** (treating $f'(x) = 3(x - 1)(x + 1)$ as if it had a negative leading coefficient like $-3(x - 1)(x + 1)$). Because this initial sign error flipped $+$ and $-$ everywhere, every single downstream conclusion written by the student (the intervals of increase/decrease and the local minimum/maximum classification) was inverted.
   - *(Additional precision note: Even when a function decreases on two separate intervals $(-\infty, -1]$ and $[1, \infty)$, one should state that it is monotonic on each interval separately rather than on their union $(-\infty, -1) \cup (1, \infty)$.)*

---

### Part 2: Correct Sign Chart for $f'(x) = 3(x - 1)(x + 1)$

We analyze the sign of each factor of $f'(x) = 3(x + 1)(x - 1)$ across the three intervals $(-\infty, -1)$, $(-1, 1)$, and $(1, \infty)$:
- The constant factor $3$ is always positive ($+$).
- The factor $(x + 1)$ is negative ($-$) for $x < -1$, zero at $x = -1$, and positive ($+$) for $x > -1$.
- The factor $(x - 1)$ is negative ($-$) for $x < 1$, zero at $x = 1$, and positive ($+$) for $x > 1$.

Multiplying the signs of the factors in each column gives the **correct sign chart**:

| Interval / Point | $(-\infty, -1)$ | $x = -1$ | $(-1, 1)$ | $x = 1$ | $(1, \infty)$ |
| :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $3$ | $+$ | $+$ | $+$ | $+$ | $+$ |
| Sign of $(x + 1)$ | $-$ | $0$ | $+$ | $+$ | $+$ |
| Sign of $(x - 1)$ | $-$ | $-$ | $-$ | $0$ | $+$ |
| **Sign of $f'(x) = 3(x - 1)(x + 1)$** | **$+$** | **$0$** | **$-$** | **$0$** | **$+$** |
| **Behavior of $f(x) = x^3 - 3x$** | **$\nearrow$ (increasing)** | **Local Max** $f(-1) = 2$ | **$\searrow$ (decreasing)** | **Local Min** $f(1) = -2$ | **$\nearrow$ (increasing)** |

---

### Part 3: Correct Intervals of Monotonicity and Character of the Extrema

From the correct sign chart in Part 2:

1. **Intervals of Monotonicity**:
   - Since $f'(x) > 0$ on $(-\infty, -1)$ and on $(1, \infty)$, the function $f$ is **strictly increasing on $(-\infty, -1]$** and **strictly increasing on $[1, \infty)$**.
   - Since $f'(x) < 0$ on $(-1, 1)$, the function $f$ is **strictly decreasing on $[-1, 1]$**.

2. **Character and Values of the Extrema**:
   - **At $x = -1$**: As $x$ passes through $-1$ from left to right, $f'(x)$ changes sign from **positive ($+$) to negative ($-$)**. Therefore, $f$ has a **strict local maximum at $x = -1$**, with value:
     $$f(-1) = (-1)^3 - 3(-1) = -1 + 3 = 2 \implies (-1, 2).$$
   - **At $x = 1$**: As $x$ passes through $1$ from left to right, $f'(x)$ changes sign from **negative ($-$) to positive ($+$)**. Therefore, $f$ has a **strict local minimum at $x = 1$**, with value:
     $$f(1) = 1^3 - 3(1) = 1 - 3 = -2 \implies (1, -2).$$

---

### Part 4: Confirmation Using Simple Test Points in Each Interval

We select one simple integer test point in each of the three open intervals and evaluate $f'(x) = 3(x - 1)(x + 1)$ directly:

1. **Interval $(-\infty, -1)$ — Test point $x = -2$**:
   $$f'(-2) = 3(-2 - 1)(-2 + 1) = 3(-3)(-1) = +9 > 0.$$
   Since $f'(-2) > 0$ and $f'(x)$ has no zeros in $(-\infty, -1)$, we have $f'(x) > 0$ on the entire interval $(-\infty, -1)$, confirming that $f$ is **strictly increasing** on $(-\infty, -1]$.
2. **Interval $(-1, 1)$ — Test point $x = 0$**:
   $$f'(0) = 3(0 - 1)(0 + 1) = 3(-1)(1) = -3 < 0.$$
   Since $f'(0) < 0$ and $f'(x)$ has no zeros in $(-1, 1)$, we have $f'(x) < 0$ on the entire interval $(-1, 1)$, confirming that $f$ is **strictly decreasing** on $[-1, 1]$.
3. **Interval $(1, \infty)$ — Test point $x = 2$**:
   $$f'(2) = 3(2 - 1)(2 + 1) = 3(1)(3) = +9 > 0.$$
   Since $f'(2) > 0$ and $f'(x)$ has no zeros in $(1, \infty)$, we have $f'(x) > 0$ on the entire interval $(1, \infty)$, confirming that $f$ is **strictly increasing** on $[1, \infty)$.

## Verification and Consistency Checks

1. **Direct Comparison of Function Values $f(x) = x^3 - 3x$**:
   Evaluating $f(x)$ at the test points and critical points:
   - $f(-2) = (-2)^3 - 3(-2) = -8 + 6 = -2$
   - $f(-1) = (-1)^3 - 3(-1) = 2$ (local maximum)
   - $f(0) = 0^3 - 3(0) = 0$
   - $f(1) = 1^3 - 3(1) = -2$ (local minimum)
   - $f(2) = 2^3 - 3(2) = 8 - 6 = 2$

   Observe that:
   - On $(-\infty, -1]$: $f(-2) = -2 < 2 = f(-1)$ (increases from $-2$ to $+2$).
   - On $[-1, 1]$: $f(-1) = 2 > f(0) = 0 > f(1) = -2$ (decreases from $+2$ down to $-2$, immediately refuting the student's claim that $f$ increases on $(-1, 1)$!).
   - On $[1, \infty)$: $f(1) = -2 < 2 = f(2)$ (increases from $-2$ to $+2$).
2. **End-Behavior Consistency Check**:
   Because $\lim_{x \to -\infty} (x^3 - 3x) = -\infty$ and $\lim_{x \to +\infty} (x^3 - 3x) = +\infty$, any cubic with positive leading coefficient must increase for large negative $x$ and for large positive $x$. The student's claim that $f$ decreases on $(-\infty, -1)$ and $(1, \infty)$ is incompatible with the end behavior of $x^3$.
