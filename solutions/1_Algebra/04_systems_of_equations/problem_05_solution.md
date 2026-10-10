# Problem 5: Row Echelon Form and Number of Solutions

## Detailed Step-by-Step Solution
The last row is zero, so it imposes no new condition. There are pivots in the $x$ and $y$ columns but none in the $z$ column; hence $z$ is free.

From the second row, $y+2z=1$. Set $z=t$, so $y=1-2t$. The first row gives
$x+2y-z=3$, hence $x=1+5t$.

$$
(x,y,z)=(1+5t,\,1-2t,\,t),\qquad t\in\mathbb R.
$$

## Verification
Substitution into both nonzero rows gives $3$ and $1$, respectively, for every $t$.