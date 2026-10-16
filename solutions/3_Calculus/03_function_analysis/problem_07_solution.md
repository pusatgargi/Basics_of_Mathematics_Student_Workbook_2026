# Problem 7: A Trigonometric Function

## Problem Statement

On $[0,2\pi]$, find the intervals of monotonicity and the extrema of
$$f(x)=\sin x+\cos x.$$
Include the endpoints of the interval and compare the function values at the critical points and at the endpoints.

## Theoretical Background and Concepts

Analyzing a smooth periodic function on a **closed and bounded (compact) interval** $[a, b]$ brings together local derivative tools and global existence theorems:

1. **Weierstrass Extreme Value Theorem**: Since $f(x) = \sin x + \cos x$ is continuous on the closed, bounded interval $[0, 2\pi]$, it is guaranteed to attain both a **global (absolute) maximum** and a **global (absolute) minimum** on $[0, 2\pi]$.
2. **Candidates for Extrema on a Closed Interval**:
   - **Interior Critical Points**: Points $c \in (a, b)$ where $f'(c) = 0$. At these points, the First Derivative Test determines whether $c$ is a local maximum ($f'$ changes from $+$ to $-$) or a local minimum ($f'$ changes from $-$ to $+$).
   - **Boundary Endpoints**: The endpoints $x = a$ and $x = b$ must be evaluated and compared directly with the values at the interior critical points. Moreover, relative to the restricted domain $[a, b]$, an endpoint is a one-sided (boundary) local minimum or maximum if the function increases or decreases away from it.
3. **Auxiliary Angle (Harmonic Addition) Identity**:
   Any linear combination $A\sin x + B\cos x$ can be written as a single shifted sinusoid. Specifically, factoring out $\sqrt{1^2 + 1^2} = \sqrt{2}$:
   $$\sin x + \cos x = \sqrt{2}\left(\frac{1}{\sqrt{2}}\sin x + \frac{1}{\sqrt{2}}\cos x\right) = \sqrt{2}\left(\sin x \cos\frac{\pi}{4} + \cos x \sin\frac{\pi}{4}\right) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right).$$
   This representation provides an immediate geometric check on the amplitude $\sqrt{2}$ and phase shift $-\frac{\pi}{4}$.

## Detailed Step-by-Step Solution

### Step 1: Domain and First Derivative

We consider $f(x) = \sin x + \cos x$ on the closed interval
$$D = [0, 2\pi].$$
Differentiating $f(x)$ with respect to $x$:
$$f'(x) = \cos x - \sin x.$$
Using the auxiliary angle identity $\cos\frac{\pi}{4} = \sin\frac{\pi}{4} = \frac{\sqrt{2}}{2}$, we can also write $f'(x)$ in factored/trigonometric-product form:
$$f'(x) = \sqrt{2}\left(\cos x \cos\frac{\pi}{4} - \sin x \sin\frac{\pi}{4}\right) = \sqrt{2}\cos\left(x + \frac{\pi}{4}\right) = -\sqrt{2}\sin\left(x - \frac{\pi}{4}\right).$$

### Step 2: Critical Points in $[0, 2\pi]$

Setting $f'(x) = 0$:
$$\cos x - \sin x = 0 \iff \sin x = \cos x.$$
Note that $\cos x$ cannot be $0$ at a solution (since $\cos x = 0 \implies \sin x = \pm 1 \neq 0$). Dividing both sides by $\cos x$ gives:
$$\tan x = 1.$$
Since $\tan x$ has period $\pi$ and $\tan\left(\frac{\pi}{4}\right) = 1$, the general solution is $x = \frac{\pi}{4} + k\pi$ ($k \in \mathbb{Z}$). Within the interval $[0, 2\pi]$, there are exactly two critical points:
$$x_1 = \frac{\pi}{4} \quad (k = 0, \text{ Quadrant I}) \qquad \text{and} \qquad x_2 = \frac{5\pi}{4} \quad (k = 1, \text{ Quadrant III}).$$

### Step 3: Sign Chart of $f'(x)$ and Intervals of Monotonicity

The two interior critical points $x_1 = \frac{\pi}{4}$ and $x_2 = \frac{5\pi}{4}$ divide $[0, 2\pi]$ into three subintervals: $\left[0, \frac{\pi}{4}\right)$, $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$, and $\left(\frac{5\pi}{4}, 2\pi\right]$.
Using $f'(x) = \cos x - \sin x = -\sqrt{2}\sin\left(x - \frac{\pi}{4}\right)$:
- For $x \in \left[0, \frac{\pi}{4}\right)$: $x - \frac{\pi}{4} \in \left[-\frac{\pi}{4}, 0\right) \implies \sin\left(x - \frac{\pi}{4}\right) < 0 \implies f'(x) > 0$ (equivalently, $\cos x > \sin x$).
- For $x \in \left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$: $x - \frac{\pi}{4} \in (0, \pi) \implies \sin\left(x - \frac{\pi}{4}\right) > 0 \implies f'(x) < 0$ (equivalently, $\cos x < \sin x$).
- For $x \in \left(\frac{5\pi}{4}, 2\pi\right]$: $x - \frac{\pi}{4} \in \left(\pi, \frac{7\pi}{4}\right] \implies \sin\left(x - \frac{\pi}{4}\right) < 0 \implies f'(x) > 0$ (equivalently, $\cos x > \sin x$).

We summarize the sign of $f'(x)$ and the behavior of $f(x)$ on $[0, 2\pi]$:

| Point / Interval | $x = 0$ | $\left(0, \frac{\pi}{4}\right)$ | $x = \frac{\pi}{4}$ | $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$ | $x = \frac{5\pi}{4}$ | $\left(\frac{5\pi}{4}, 2\pi\right)$ | $x = 2\pi$ |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sign of $f'(x)$ | $+1$ | $+$ | $0$ | $-$ | $0$ | $+$ | $+1$ |
| Value / Behavior of $f(x)$ | $1$ | $\nearrow$ | **$\sqrt{2}$ (Max)** | $\searrow$ | **$-\sqrt{2}$ (Min)** | $\nearrow$ | $1$ |

**Intervals of Monotonicity on $[0, 2\pi]$**:
- $f$ is **strictly increasing** on $\left[0, \frac{\pi}{4}\right]$ and on $\left[\frac{5\pi}{4}, 2\pi\right]$.
- $f$ is **strictly decreasing** on $\left[\frac{\pi}{4}, \frac{5\pi}{4}\right]$.

### Step 4: Comparison of Function Values at Critical Points and Endpoints

We compute $f(x) = \sin x + \cos x$ at the two interior critical points and the two boundary endpoints:

1. **Left Endpoint ($x = 0$)**:
   $$f(0) = \sin 0 + \cos 0 = 0 + 1 = 1.$$
2. **First Critical Point ($x = \frac{\pi}{4}$)**:
   $$f\left(\frac{\pi}{4}\right) = \sin\frac{\pi}{4} + \cos\frac{\pi}{4} = \frac{\sqrt{2}}{2} + \frac{\sqrt{2}}{2} = \sqrt{2} \approx 1.4142.$$
3. **Second Critical Point ($x = \frac{5\pi}{4}$)**:
   $$f\left(\frac{5\pi}{4}\right) = \sin\frac{5\pi}{4} + \cos\frac{5\pi}{4} = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} \approx -1.4142.$$
4. **Right Endpoint ($x = 2\pi$)**:
   $$f(2\pi) = \sin(2\pi) + \cos(2\pi) = 0 + 1 = 1.$$

**Comparison and Classification of Extrema**:
Ordering all candidate values from smallest to largest gives:
$$f\left(\frac{5\pi}{4}\right) = -\sqrt{2} < f(0) = f(2\pi) = 1 < f\left(\frac{\pi}{4}\right) = \sqrt{2}.$$
- **At $x = \frac{\pi}{4}$**: Since $f'$ changes sign from $+$ to $-$ and $\sqrt{2}$ is the largest value on $[0, 2\pi]$, $f$ has an **interior local maximum** and the **global maximum** on $[0, 2\pi]$, equal to $\sqrt{2}$.
- **At $x = \frac{5\pi}{4}$**: Since $f'$ changes sign from $-$ to $+$ and $-\sqrt{2}$ is the smallest value on $[0, 2\pi]$, $f$ has an **interior local minimum** and the **global minimum** on $[0, 2\pi]$, equal to $-\sqrt{2}$.
- **At the endpoints $x = 0$ and $x = 2\pi$**:
  - Because $f$ increases strictly to the right of $x = 0$, $x = 0$ is a **boundary (one-sided) local minimum** on $[0, 2\pi]$ with value $f(0) = 1$ (which is higher than the global minimum $-\sqrt{2}$).
  - Because $f$ increases strictly up to $x = 2\pi$ from the left, $x = 2\pi$ is a **boundary (one-sided) local maximum** on $[0, 2\pi]$ with value $f(2\pi) = 1$ (which is lower than the global maximum $\sqrt{2}$).
  - *(Note: If $f$ is viewed on all of $\mathbb{R}$ by periodicity, $x = 0$ and $x = 2\pi$ are not local extrema because $f'(0) = f'(2\pi) = 1 > 0$.)*

## Verification and Consistency Checks

1. **Test Points in Each Subinterval**:
   - In $\left(0, \frac{\pi}{4}\right)$, pick $x = \frac{\pi}{6}$: $f'\left(\frac{\pi}{6}\right) = \frac{\sqrt{3} - 1}{2} \approx 0.366 > 0$, and $f\left(\frac{\pi}{6}\right) = \frac{1 + \sqrt{3}}{2} \approx 1.366 \in (1, \sqrt{2})$.
   - In $\left(\frac{\pi}{4}, \frac{5\pi}{4}\right)$, pick $x = \frac{3\pi}{4}$: $f'\left(\frac{3\pi}{4}\right) = -\frac{\sqrt{2}}{2} - \frac{\sqrt{2}}{2} = -\sqrt{2} < 0$, and $f\left(\frac{3\pi}{4}\right) = 0 \in (-\sqrt{2}, \sqrt{2})$.
   - In $\left(\frac{5\pi}{4}, 2\pi\right)$, pick $x = \frac{7\pi}{4}$: $f'\left(\frac{7\pi}{4}\right) = \frac{\sqrt{2}}{2} - \left(-\frac{\sqrt{2}}{2}\right) = \sqrt{2} > 0$, and $f\left(\frac{7\pi}{4}\right) = 0 \in (-\sqrt{2}, 1)$.
2. **Second Derivative Check at Critical Points**:
   $f''(x) = -\sin x - \cos x = -f(x)$. Thus $f''\left(\frac{\pi}{4}\right) = -\sqrt{2} < 0$ (confirming the local maximum at $x = \frac{\pi}{4}$) and $f''\left(\frac{5\pi}{4}\right) = \sqrt{2} > 0$ (confirming the local minimum at $x = \frac{5\pi}{4}$).
3. **Auxiliary Angle Range Check**:
   Since $f(x) = \sqrt{2}\sin\left(x + \frac{\pi}{4}\right)$ and $-1 \le \sin\theta \le 1$, we immediately have $-\sqrt{2} \le f(x) \le \sqrt{2}$, with $f(x) = \sqrt{2} \iff x + \frac{\pi}{4} = \frac{\pi}{2} \iff x = \frac{\pi}{4}$ and $f(x) = -\sqrt{2} \iff x + \frac{\pi}{4} = \frac{3\pi}{2} \iff x = \frac{5\pi}{4}$.
