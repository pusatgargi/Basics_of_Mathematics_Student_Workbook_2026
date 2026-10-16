# Problem 5: Angle Between Vectors

## Problem Statement

Given $u=(1,1,0)$ and $v=(1,0,1)$:

1. Use the sign of $u\cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

## Theoretical Background and Concepts

1. **Dot Product and Angle Formula:** For any two non-zero vectors $u, v \in \mathbb{R}^3$, the dot product is related to their lengths and the angle $\theta \in [0, \pi]$ (or $[0^\circ, 180^\circ]$) between them by
   $$u \cdot v = \|u\|\,\|v\|\cos\theta \iff \cos\theta = \frac{u \cdot v}{\|u\|\,\|v\|}.$$

2. **Qualitative Angle Classification from the Sign of $u \cdot v$:** Because the lengths $\|u\|$ and $\|v\|$ of non-zero vectors are strictly positive ($\|u\| > 0$ and $\|v\| > 0$), the sign of $\cos\theta$ is identical to the sign of the dot product $u \cdot v$:
   - If $u \cdot v > 0$, then $\cos\theta > 0$, so $0 \le \theta < \frac{\pi}{2}$ ($0^\circ \le \theta < 90^\circ$): the angle is **acute** (the vectors point generally in a similar half-space).
   - If $u \cdot v = 0$, then $\cos\theta = 0$, so $\theta = \frac{\pi}{2}$ ($90^\circ$): the angle is a **right angle** (the vectors are perpendicular).
   - If $u \cdot v < 0$, then $\cos\theta < 0$, so $\frac{\pi}{2} < \theta \le \pi$ ($90^\circ < \theta \le 180^\circ$): the angle is **obtuse** (the vectors point generally in opposite half-spaces).

## Detailed Step-by-Step Solution

We are given the vectors
$$u = (1, 1, 0) \qquad \text{and} \qquad v = (1, 0, 1).$$

### Part 1: Use the Sign of $u \cdot v$ to Predict the Type of Angle

We first compute the dot product $u \cdot v$ using the component formula
$$u \cdot v = u_1 v_1 + u_2 v_2 + u_3 v_3.$$
Substituting the components of $u = (1, 1, 0)$ and $v = (1, 0, 1)$:
$$\begin{aligned}
u \cdot v &= (1)(1) + (1)(0) + (0)(1) \\
          &= 1 + 0 + 0 \\
          &= 1.
\end{aligned}$$
**Prediction:** Since $u \cdot v = 1 > 0$, we have $\cos\theta > 0$. On the interval $[0^\circ, 180^\circ]$, the cosine function is positive strictly for angles less than $90^\circ$. Therefore, we predict that the angle $\theta$ between $u$ and $v$ is **acute** ($0^\circ < \theta < 90^\circ$, or $0 < \theta < \frac{\pi}{2}$).

### Part 2: Compute the Angle

To find the exact angle $\theta$, we apply the cosine formula
$$\cos\theta = \frac{u \cdot v}{\|u\|\,\|v\|}.$$

First, we compute the length of $u = (1, 1, 0)$ using $\|u\| = \sqrt{u_1^2 + u_2^2 + u_3^2}$:
$$\begin{aligned}
\|u\| &= \sqrt{1^2 + 1^2 + 0^2} \\
      &= \sqrt{1 + 1 + 0} \\
      &= \sqrt{2}.
\end{aligned}$$

Second, we compute the length of $v = (1, 0, 1)$ using $\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}$:
$$\begin{aligned}
\|v\| &= \sqrt{1^2 + 0^2 + 1^2} \\
      &= \sqrt{1 + 0 + 1} \\
      &= \sqrt{2}.
\end{aligned}$$

Now substitute $u \cdot v = 1$, $\|u\| = \sqrt{2}$, and $\|v\| = \sqrt{2}$ into the formula for $\cos\theta$:
$$\begin{aligned}
\cos\theta &= \frac{1}{\sqrt{2} \cdot \sqrt{2}} \\
           &= \frac{1}{2}.
\end{aligned}$$
Taking the inverse cosine on the principal range $\theta \in [0, \pi]$:
$$\theta = \arccos\left(\frac{1}{2}\right) = \frac{\pi}{3}\text{ radians} = 60^\circ.$$

### Part 3: Compare the Result with the Prediction

In Part 1, based purely on the positive sign of $u \cdot v = 1 > 0$, we predicted that $\theta$ must be an **acute angle** ($0^\circ < \theta < 90^\circ$). In Part 2, the exact calculation yielded $\theta = 60^\circ$ ($\frac{\pi}{3}$ radians). Because $0^\circ < 60^\circ < 90^\circ$, the exact result is completely consistent with our qualitative prediction.

## Verification and Consistency Checks

1. **Equilateral Triangle Geometric Verification:** Consider the triangle in $\mathbb{R}^3$ formed by the origin $O = (0, 0, 0)$ and the tips of the two vectors at $A = (1, 1, 0)$ and $B = (1, 0, 1)$. The three side vectors of $\triangle OAB$ are $u = \overrightarrow{OA}$, $v = \overrightarrow{OB}$, and the third side $u - v = \overrightarrow{BA}$:
   $$u - v = (1 - 1,\; 1 - 0,\; 0 - 1) = (0, 1, -1).$$
   Computing the length of this third side gives:
   $$\|u - v\| = \sqrt{0^2 + 1^2 + (-1)^2} = \sqrt{0 + 1 + 1} = \sqrt{2}.$$
   Since all three sides of $\triangle OAB$ have the exact same length,
   $$\|u\| = \|v\| = \|u - v\| = \sqrt{2},$$
   the triangle $\triangle OAB$ is **equilateral**! Every interior angle of an equilateral triangle is $60^\circ$ ($\frac{\pi}{3}$ radians), which geometrically proves that the angle between $u$ and $v$ is $60^\circ$. $\checkmark$

```
             B = (1, 0, 1)
                 /\
                /  \
      ||v|| =  /    \  ||u - v|| = sqrt(2)
      sqrt(2) /      \
             / 60 deg \
            O -------- A = (1, 1, 0)
            ||u|| = sqrt(2)
```

2. **Cauchy-Schwarz Inequality Check:** The dot product must satisfy $|u \cdot v| \le \|u\|\,\|v\|$. Here $|u \cdot v| = 1$ and $\|u\|\,\|v\| = \sqrt{2}\cdot\sqrt{2} = 2$, and $1 \le 2$ holds as required. $\checkmark$
