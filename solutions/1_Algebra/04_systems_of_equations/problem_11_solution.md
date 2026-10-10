# Problem 11: A Parameter in a System of Three Equations

## Detailed Step-by-Step Solution
Subtract the first equation from the second and third:

$$
(t-1)y=1,\qquad (t-1)z=2.
$$

If $t\ne1$, these give $y=\frac1{t-1}$ and $z=\frac2{t-1}$. The first equation then gives
$x=1-y-z=\frac{t-4}{t-1}$. There is exactly one solution:

$$
(x,y,z)=\left(\frac{t-4}{t-1},\,\frac1{t-1},\,\frac2{t-1}\right).
$$

If $t=1$, the second equation has the same left side as the first but a different right side ($2$ rather than $1$), so the system is inconsistent. The division by $t-1$ is exactly the step that is invalid at this value.

## Verification
For $t\ne1$, substitution gives the three right-hand sides $1,2,3$; for $t=1$, the first two equations already contradict each other.