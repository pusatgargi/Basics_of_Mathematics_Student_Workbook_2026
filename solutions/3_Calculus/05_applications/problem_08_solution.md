# Problem 8: Number of Requests Handled by a Server

## Problem Statement

The rate at which requests arrive at a server during the first 5 minutes is described by the function
$$
r(t)=100+20t\quad [\text{requests/min}],\qquad 0\le t\le5.
$$

1. Compute the total number of requests that arrived during this time.
2. Compute the average rate of incoming requests over this interval.
3. Compare the average rate with the values $r(0)$ and $r(5)$.

## Theoretical Background and Concepts

1. **Accumulation of a Varying Rate via Definite Integration**:
   When a discrete or continuous quantity $Q(t)$ (such as data packets, bytes transferred, or server requests) arrives at a time-varying instantaneous rate $r(t) = Q'(t)$, the total amount accumulated over the time interval $[a, b]$ is given by the definite integral of the rate function:
   $$
   Q_{\text{total}} = Q(b) - Q(a) = \int_a^b r(t)\,dt.
   $$
   In computer systems analysis, although individual requests are discrete events, when arrival rates are high (hundreds of requests per minute), a continuous fluid-flow rate model $r(t)$ accurately describes the cumulative load.

2. **Average Rate Over an Interval**:
   The average arrival rate $r_{\text{avg}}$ on $[a, b]$ is the constant arrival rate that would produce the exact same total number of requests over the duration $b - a$:
   $$
   r_{\text{avg}} = \frac{Q_{\text{total}}}{b - a} = \frac{1}{b - a}\int_a^b r(t)\,dt.
   $$

3. **Property of Linear (Affine) Rate Functions**:
   For any affine function $r(t) = \alpha + \beta t$ on $[a, b]$, the graph is a straight line segment, so the integral average value equals the arithmetic mean of the endpoint values and equals the value at the midpoint $t_{\text{mid}} = \frac{a+b}{2}$:
   $$
   r_{\text{avg}} = \frac{r(a) + r(b)}{2} = r\left(\frac{a+b}{2}\right).
   $$

## Detailed Step-by-Step Solution

### Part 1: Total Number of Requests Arriving During the First 5 Minutes

The instantaneous arrival rate is $r(t) = 100 + 20t\ [\text{requests/min}]$ on $[0, 5]$. Integrating $r(t)$ from $t = 0$ to $t = 5$ gives the total number of requests $N_{\text{total}}$:
$$
\begin{aligned}
N_{\text{total}} &= \int_0^5 r(t)\,dt = \int_0^5 (100 + 20t)\,dt \\
&= \left[100t + 20 \cdot \frac{t^2}{2}\right]_0^5 \\
&= \left[100t + 10t^2\right]_0^5 \\
&= \left(100(5) + 10(5)^2\right) - \left(100(0) + 10(0)^2\right) \\
&= (500 + 250) - 0 \\
&= 750\text{ requests}.
\end{aligned}
$$
Thus, a total of **$750$ requests** arrived at the server during the first $5$ minutes.

---

### Part 2: Average Rate of Incoming Requests Over $[0, 5]$

Using the definition of the average value of a function on $[0, 5]$:
$$
\begin{aligned}
r_{\text{avg}} &= \frac{1}{5 - 0}\int_0^5 r(t)\,dt \\
&= \frac{N_{\text{total}}}{5} \\
&= \frac{750\text{ requests}}{5\text{ min}} \\
&= 150\text{ requests/min}.
\end{aligned}
$$
The average rate of incoming requests over the $5$-minute interval is **$150\text{ requests/min}$**.

---

### Part 3: Comparison of the Average Rate with $r(0)$ and $r(5)$

Evaluating the arrival rate at the endpoints $t = 0$ and $t = 5$:
- Initial rate at $t = 0$:
  $$
  r(0) = 100 + 20(0) = 100\text{ requests/min}.
  $$
- Final rate at $t = 5$:
  $$
  r(5) = 100 + 20(5) = 100 + 100 = 200\text{ requests/min}.
  $$

**Comparison and Interpretation**:
1. **Strict Ordering**: The average rate lies strictly between the initial and final rates:
   $$
   r(0) = 100 < r_{\text{avg}} = 150 < r(5) = 200 \quad [\text{requests/min}].
   $$
2. **Exact Midpoint / Arithmetic Mean Relation**:
   Notice that the arithmetic mean of the endpoint rates is:
   $$
   \frac{r(0) + r(5)}{2} = \frac{100 + 200}{2} = 150\text{ requests/min} = r_{\text{avg}},
   $$
   and at the midpoint of the time interval, $t = 2.5\text{ min}$, the rate is $r(2.5) = 100 + 20(2.5) = 150\text{ requests/min} = r_{\text{avg}}$.
   This exact equality between the integral average and the arithmetic mean of the endpoints holds because $r(t) = 100 + 20t$ increases **linearly** (at a constant acceleration of $20\text{ requests/min}^2$), so the lower arrival rates during the first half $[0, 2.5]$ are symmetrically compensated by the higher arrival rates during the second half $[2.5, 5]$.

## Verification and Consistency Checks

1. **Unit Analysis**:
   - In Part 1: $[r(t)] \cdot [dt] = [\text{requests/min}] \cdot [\text{min}] = [\text{requests}]$.
   - In Part 2: $\frac{[\text{requests}]}{[\text{min}]} = [\text{requests/min}]$.

2. **Trapezoidal Area Check**:
   Geometrically, the region under $r(t) = 100 + 20t$ on $[0, 5]$ is a trapezoid of width $5\text{ min}$ and parallel heights $r(0) = 100$ and $r(5) = 200$. Its area is:
   $$
   \text{Area} = \frac{100 + 200}{2} \times 5 = 150 \times 5 = 750\text{ requests},
   $$
   confirming both $N_{\text{total}} = 750$ and $r_{\text{avg}} = 150\text{ requests/min}$.

3. **Minute-by-Minute Breakdown Check**:
   On each $1$-minute interval $[k-1, k]$ for $k = 1, 2, 3, 4, 5$, the number of requests is $\int_{k-1}^k (100+20t)\,dt = 110, 130, 150, 170, 190$. Their sum is:
   $$
   110 + 130 + 150 + 170 + 190 = 750\text{ requests}.
   $$
