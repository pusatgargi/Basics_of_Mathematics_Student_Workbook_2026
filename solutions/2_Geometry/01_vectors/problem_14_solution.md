# Problem 14: Closest Point on a Line

## Problem Statement

Given a point $P=(4,1)$ and a line through the origin with direction $v=(1,2)$. Using projection, find the closest point on the line, the distance from $P$ to the line, and verify that the appropriate vector is perpendicular to the direction of the line.

## Theoretical Background and Concepts

1. **Parametric Description of a Line Through the Origin:** A line $\ell$ passing through the origin $O = (0, 0)$ with non-zero direction vector $v = (v_1, v_2)$ consists of all points $X = t v = (t v_1, t v_2)$ for $t \in \mathbb{R}$.

2. **Closest Point via Orthogonal Projection:** Given an external point $P$ with position vector $p = \overrightarrow{OP}$, for any point $X$ on the line $\ell$ and the foot $Q$ of the perpendicular dropped from $P$ onto $\ell$, the triangle $\triangle PQX$ has a right angle at $Q$. By the Pythagorean theorem,
   $$\|\overrightarrow{XP}\|^2 = \|\overrightarrow{XQ}\|^2 + \|\overrightarrow{QP}\|^2 \ge \|\overrightarrow{QP}\|^2,$$
   with equality if and only if $X = Q$. Therefore, the **closest point** $Q$ on the line $\ell$ to $P$ is the orthogonal projection of $P$ onto $\ell$, whose position vector is:
   $$\overrightarrow{OQ} = \operatorname{proj}_v \overrightarrow{OP} = \left(\frac{\overrightarrow{OP} \cdot v}{v \cdot v}\right) v.$$

3. **Distance from a Point to a Line:** The shortest distance $d(P, \ell)$ from $P$ to the line $\ell$ is the length of the perpendicular connecting vector $\overrightarrow{QP} = P - Q = \overrightarrow{OP} - \operatorname{proj}_v \overrightarrow{OP}$:
   $$d(P, \ell) = \|\overrightarrow{QP}\| = \|P - Q\|.$$

## Detailed Step-by-Step Solution

We are given the point $P = (4, 1)$ (with position vector $p = \overrightarrow{OP} = (4, 1)$) and the line $\ell$ through the origin $O = (0, 0)$ with direction vector $v = (1, 2)$.

### Step 1: Find the Closest Point $Q$ on the Line Using Projection

The position vector $\overrightarrow{OQ}$ of the closest point $Q$ on the line $\ell$ is the orthogonal projection of $p = \overrightarrow{OP} = (4, 1)$ onto $v = (1, 2)$:
$$\overrightarrow{OQ} = \operatorname{proj}_v p = \left(\frac{p \cdot v}{v \cdot v}\right) v.$$

First, we compute the dot product $p \cdot v = p_1 v_1 + p_2 v_2$:
$$\begin{aligned}
p \cdot v &= (4)(1) + (1)(2) \\
          &= 4 + 2 \\
          &= 6.
\end{aligned}$$

Second, we compute $v \cdot v = \|v\|^2 = v_1^2 + v_2^2$:
$$\begin{aligned}
v \cdot v &= 1^2 + 2^2 \\
          &= 1 + 4 \\
          &= 5.
\end{aligned}$$

Substituting $p \cdot v = 6$ and $v \cdot v = 5$ into the projection formula:
$$\begin{aligned}
\overrightarrow{OQ} &= \frac{6}{5}(1, 2) \\
                    &= \left(\frac{6}{5} \cdot 1,\; \frac{6}{5} \cdot 2\right) \\
                    &= \left(\frac{6}{5},\; \frac{12}{5}\right) = (1.2,\; 2.4).
\end{aligned}$$
Therefore, the **closest point on the line** to $P$ is:
$$Q = \left(\frac{6}{5},\; \frac{12}{5}\right) = (1.2,\; 2.4).$$

### Step 2: Find the Distance from $P$ to the Line

To find the distance from $P$ to the line $\ell$, we first construct the perpendicular displacement vector $\overrightarrow{QP} = P - Q$ from the closest point $Q = \left(\frac{6}{5}, \frac{12}{5}\right)$ to $P = (4, 1) = \left(\frac{20}{5}, \frac{5}{5}\right)$:
$$\begin{aligned}
\overrightarrow{QP} = P - Q &= (4, 1) - \left(\frac{6}{5},\; \frac{12}{5}\right) \\
                            &= \left(\frac{20}{5} - \frac{6}{5},\; \frac{5}{5} - \frac{12}{5}\right) \\
                            &= \left(\frac{14}{5},\; -\frac{7}{5}\right) = (2.8,\; -1.4).
\end{aligned}$$

The distance $d(P, \ell)$ from $P$ to the line is the Euclidean length of $\overrightarrow{QP}$:
$$\begin{aligned}
d(P, \ell) = \|\overrightarrow{QP}\| &= \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} \\
                                     &= \sqrt{\frac{196}{25} + \frac{49}{25}} \\
                                     &= \sqrt{\frac{245}{25}} \\
                                     &= \frac{\sqrt{49 \cdot 5}}{5} \\
                                     &= \frac{7\sqrt{5}}{5} \approx 3.1305.
\end{aligned}$$

### Step 3: Verify That the Appropriate Vector Is Perpendicular to the Direction of the Line

The appropriate vector whose perpendicularity characterizes the shortest distance is the displacement vector $\overrightarrow{QP} = P - Q = \left(\frac{14}{5}, -\frac{7}{5}\right)$ connecting the foot $Q$ on the line to the external point $P$ (or equivalently $\overrightarrow{PQ} = -\overrightarrow{QP}$).

We compute the dot product of $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right)$ with the line's direction vector $v = (1, 2)$:
$$\begin{aligned}
\overrightarrow{QP} \cdot v &= \left(\frac{14}{5}\right)(1) + \left(-\frac{7}{5}\right)(2) \\
                            &= \frac{14}{5} - \frac{14}{5} \\
                            &= 0.
\end{aligned}$$
Since $\overrightarrow{QP} \cdot v = 0$, the vector $\overrightarrow{QP}$ from the closest point $Q$ to $P$ is strictly perpendicular to the direction vector $v$ of the line.

```
      y ^
      3 |        / line l (direction v = (1,2))
    2.4 |      * Q = (6/5, 12/5)
      2 |     * \  v = (1,2)
        |    /    \  QP = (14/5, -7/5)
      1 |   /       * P = (4, 1)
        |  /
      0 +--+----+----+----+----+----> x
        0  1    2    3    4    5
```

## Verification and Consistency Checks

1. **Pythagorean Theorem Check on Right Triangle $\triangle OQP$:** Since $\overrightarrow{OQ} \perp \overrightarrow{QP}$ and $\overrightarrow{OQ} + \overrightarrow{QP} = \overrightarrow{OP}$, we must have $\|\overrightarrow{OQ}\|^2 + \|\overrightarrow{QP}\|^2 = \|\overrightarrow{OP}\|^2$:
   - $\|\overrightarrow{OQ}\|^2 = \left(\frac{6}{5}\right)^2 + \left(\frac{12}{5}\right)^2 = \frac{36 + 144}{25} = \frac{180}{25}.$
   - $\|\overrightarrow{QP}\|^2 = \left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2 = \frac{196 + 49}{25} = \frac{245}{25}.$
   - $\|\overrightarrow{OP}\|^2 = 4^2 + 1^2 = 16 + 1 = 17.$
   Summing the two squared legs:
   $$\|\overrightarrow{OQ}\|^2 + \|\overrightarrow{QP}\|^2 = \frac{180}{25} + \frac{245}{25} = \frac{425}{25} = 17 = \|\overrightarrow{OP}\|^2. \quad \checkmark$$

2. **Independent Quadratic Minimization Check:** Any point on the line $\ell$ has coordinates $X(t) = (t, 2t)$ for $t \in \mathbb{R}$. The squared distance from $P = (4, 1)$ to $X(t)$ is the quadratic function:
   $$\begin{aligned}
   f(t) = \|P - X(t)\|^2 &= (4 - t)^2 + (1 - 2t)^2 \\
                         &= (16 - 8t + t^2) + (1 - 4t + 4t^2) \\
                         &= 5t^2 - 12t + 17.
   \end{aligned}$$
   Completing the square (or setting $f'(t) = 10t - 12 = 0$) gives the unique minimum at $t = \frac{12}{10} = \frac{6}{5}$, which yields the closest point $X\left(\frac{6}{5}\right) = \left(\frac{6}{5}, \frac{12}{5}\right) = Q$ and minimum distance $\sqrt{f\left(\frac{6}{5}\right)} = \sqrt{5\left(\frac{36}{25}\right) - 12\left(\frac{6}{5}\right) + 17} = \sqrt{\frac{49}{5}} = \frac{7\sqrt{5}}{5}$. $\checkmark$
