# Problem 1: Motion — from Position to Velocity

## Problem Statement

The position of a point is described by
$$
s(t)=t^3-6t^2+9t+2,\qquad t\ge0.
$$

1. Determine the velocity and acceleration.
2. Find the times at which the point stops.
3. Determine on which intervals the point moves in the positive direction of the axis and on which intervals it moves in the negative direction.

## Theoretical Background and Concepts

In one-dimensional kinematics, the motion of a point particle along a coordinate axis is described by its **position function** $s(t)$ for $t \ge 0$. Differential calculus provides the instantaneous rates of change that characterize the motion:

1. **Instantaneous Velocity**: Velocity is the first derivative of position with respect to time:
   $$
   v(t) = s'(t) = \frac{ds}{dt} = \lim_{\Delta t \to 0} \frac{s(t+\Delta t) - s(t)}{\Delta t}.
   $$
   - The **magnitude** $|v(t)|$ is the instantaneous speed of the particle.
   - The **sign** of $v(t)$ determines the direction of motion along the coordinate axis:
     - $v(t) > 0$: the position $s(t)$ is strictly increasing, meaning the point moves in the **positive direction** of the axis.
     - $v(t) < 0$: the position $s(t)$ is strictly decreasing, meaning the point moves in the **negative direction** of the axis.
     - $v(t) = 0$: the point is instantaneously at rest (**stops**); if $v(t)$ changes sign across this instant, the particle reverses its direction of motion (a turning point).

2. **Instantaneous Acceleration**: Acceleration is the rate of change of velocity with respect to time, i.e., the first derivative of velocity and the second derivative of position:
   $$
   a(t) = v'(t) = s''(t) = \frac{d^2s}{dt^2}.
   $$

## Detailed Step-by-Step Solution

### Part 1: Determining the Velocity and Acceleration

We are given the position function on the time domain $t \in [0, \infty)$:
$$
s(t) = t^3 - 6t^2 + 9t + 2, \qquad t \ge 0.
$$

**Step 1a: Differentiate $s(t)$ to find the velocity $v(t)$.**
Applying the power rule $\frac{d}{dt}(t^n) = nt^{n-1}$ and the linearity of differentiation term by term:
$$
\begin{aligned}
v(t) = s'(t) &= \frac{d}{dt}\left(t^3 - 6t^2 + 9t + 2\right) \\
&= 3t^2 - 6(2t) + 9(1) + 0 \\
&= 3t^2 - 12t + 9.
\end{aligned}
$$
We can also factor out $3$ to reveal the structure of the velocity function:
$$
v(t) = 3(t^2 - 4t + 3) = 3(t - 1)(t - 3).
$$

**Step 1b: Differentiate $v(t)$ to find the acceleration $a(t)$.**
Differentiating $v(t) = 3t^2 - 12t + 9$ with respect to $t$:
$$
\begin{aligned}
a(t) = v'(t) = s''(t) &= \frac{d}{dt}\left(3t^2 - 12t + 9\right) \\
&= 3(2t) - 12(1) + 0 \\
&= 6t - 12 = 6(t - 2).
\end{aligned}
$$

---

### Part 2: Finding the Times at Which the Point Stops

The point stops (is instantaneously at rest) whenever its instantaneous velocity equals zero:
$$
v(t) = 0, \qquad t \ge 0.
$$
Using the factored form of $v(t)$ from Part 1:
$$
3(t - 1)(t - 3) = 0.
$$
Dividing both sides by $3$ gives:
$$
(t - 1)(t - 3) = 0 \implies t = 1 \quad \text{or} \quad t = 3.
$$
Both values $t = 1$ and $t = 3$ lie within the physical domain $t \ge 0$. Therefore, the point stops at two instants:
$$
t_1 = 1 \quad \text{and} \quad t_2 = 3.
$$

At these stopping times, the positions and accelerations of the point are:
- At $t = 1$:
  $$
  s(1) = 1^3 - 6(1)^2 + 9(1) + 2 = 1 - 6 + 9 + 2 = 6, \qquad a(1) = 6(1) - 12 = -6.
  $$
- At $t = 3$:
  $$
  s(3) = 3^3 - 6(3)^2 + 9(3) + 2 = 27 - 54 + 27 + 2 = 2, \qquad a(3) = 6(3) - 12 = 6.
  $$

---

### Part 3: Intervals of Motion in the Positive and Negative Directions

To determine the direction of motion on $t \ge 0$, we analyze the sign of $v(t) = 3(t - 1)(t - 3)$ across the subintervals partitioned by the stopping times $t = 1$ and $t = 3$:

| Time Interval / Point | Sign of $(t - 1)$ | Sign of $(t - 3)$ | Sign of $v(t) = 3(t-1)(t-3)$ | Behavior of $s(t)$ / Direction of Motion |
| :--- | :---: | :---: | :---: | :--- |
| $t \in [0, 1)$ | $-$ | $-$ | $+$ | Strictly increasing — moves in the **positive direction** |
| $t = 1$ | $0$ | $-$ | $0$ | Instantaneously at rest (local maximum of position, $s(1)=6$) |
| $t \in (1, 3)$ | $+$ | $-$ | $-$ | Strictly decreasing — moves in the **negative direction** |
| $t = 3$ | $+$ | $0$ | $0$ | Instantaneously at rest (local minimum of position, $s(3)=2$) |
| $t \in (3, \infty)$ | $+$ | $+$ | $+$ | Strictly increasing — moves in the **positive direction** |

- **Motion in the positive direction of the axis ($v(t) > 0$)**:
  $$
  t \in [0, 1) \cup (3, \infty) \qquad \text{(or on the open intervals } (0, 1) \text{ and } (3, \infty)\text{)}.
  $$
- **Motion in the negative direction of the axis ($v(t) < 0$)**:
  $$
  t \in (1, 3).
  $$

## Verification and Consistency Checks

1. **Position Trajectory and Turning Point Consistency**:
   - At $t = 0$, the point starts at $s(0) = 2$ with initial velocity $v(0) = 9 > 0$.
   - Over $[0, 1]$, the point moves forward in the positive direction from $s(0) = 2$ to $s(1) = 6$ (displacement $\Delta s_1 = +4$). Since $a(1) = -6 < 0$, $t = 1$ is indeed a local maximum of $s(t)$ where motion reverses from positive to negative.
   - Over $[1, 3]$, the point moves backward in the negative direction from $s(1) = 6$ back to $s(3) = 2$ (displacement $\Delta s_2 = -4$). Since $a(3) = +6 > 0$, $t = 3$ is a local minimum of $s(t)$ where motion reverses from negative to positive.
   - For $t > 3$, the point moves forward again toward $+\infty$; for instance, at $t = 4$, $s(4) = 64 - 96 + 36 + 2 = 6 > s(3)$, and $v(4) = 3(3)(1) = 9 > 0$.

2. **Test-Point Evaluation of Velocity**:
   - At $t = 0.5 \in (0, 1)$: $v(0.5) = 3(-0.5)(-2.5) = +3.75 > 0$ (positive direction).
   - At $t = 2 \in (1, 3)$: $v(2) = 3(1)(-1) = -3 < 0$ (negative direction; also $a(2) = 0$ is the inflection point of $s(t)$ where negative velocity is most rapid).
   - At $t = 4 \in (3, \infty)$: $v(4) = 3(3)(1) = +9 > 0$ (positive direction).

3. **Integral Reconstruction Check**:
   Integrating $v(t) = 3t^2 - 12t + 9$ from $0$ to $t$ with $s(0) = 2$:
   $$
   s(0) + \int_0^t (3\tau^2 - 12\tau + 9)\,d\tau = 2 + \left[\tau^3 - 6\tau^2 + 9\tau\right]_0^t = t^3 - 6t^2 + 9t + 2 = s(t),
   $$
   confirming exact consistency between $s(t)$, $v(t)$, and $a(t)$.
