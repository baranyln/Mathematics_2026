# Problem 14 Solution

## Problem Statement
Given a point $P=(4,1)$ and a line through the origin with direction $v=(1,2)$. Using projection, find the closest point on the line, the distance from $P$ to the line, and verify that the appropriate vector is perpendicular to the direction of the line.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Closest Point on a Line via Projection: For a line through the origin with direction vector $v$ and an external point $P$, the closest point $Q$ on the line to $P$ is obtained by orthogonally projecting the position vector of $P$ onto the line:

$$
Q = \mathrm{proj}_v\,P = \frac{P \cdot v}{v \cdot v} v
$$

- Distance from Point to Line: The shortest (perpendicular) distance from $P$ to the line equals the length of the rejection vector:

$$
d = \|P - Q\| = \left\|P - \mathrm{proj}_v\,P\right\|
$$

- Perpendicularity Verification: The vector from $Q$ to $P$ must be orthogonal to the direction $v$:

$$
(P - Q) \cdot v = 0
$$

- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products stated explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given a point and a line through the origin in $\mathbb{R}^2$:

$$
P = (4, 1), \qquad v = (1, 2)
$$

Treating $P$ also as a position vector from the origin, we project it onto the line direction $v$ to find the foot of the perpendicular $Q = \mathrm{proj}_v\,P$. The vector $\overrightarrow{QP} = P - Q$ gives the perpendicular displacement, whose length is the minimum distance. We then verify $\overrightarrow{QP} \cdot v = 0$.

2. **Intermediate Calculations:**
- **Step 1: Compute the scalar dot products $P \cdot v$ and $v \cdot v$:**
For $P \cdot v$:

$$
\begin{aligned}
P \cdot v &= (4)(1) + (1)(2) \\
          &= 4 + 2 \\
          &= 6
\end{aligned}
$$

For $v \cdot v = \|v\|^2$:

$$
\begin{aligned}
v \cdot v &= (1)(1) + (2)(2) \\
          &= 1 + 4 \\
          &= 5
\end{aligned}
$$

- **Step 2: Compute the closest point $Q = \mathrm{proj}_v\,P$:**
Multiply the direction vector $v$ by the projection scalar $\frac{P \cdot v}{v \cdot v} = \frac{6}{5}$:

$$
\begin{aligned}
Q &= \frac{P \cdot v}{v \cdot v} v \\
  &= \frac{6}{5} (1, 2) \\
  &= \left(\frac{6}{5} \cdot 1, \frac{6}{5} \cdot 2\right) \\
  &= \left(\frac{6}{5}, \frac{12}{5}\right)
\end{aligned}
$$

- **Step 3: Compute the vector $\overrightarrow{QP} = P - Q$:**
Subtract the coordinates of $Q$ from $P$:

$$
\begin{aligned}
\overrightarrow{QP} &= P - Q \\
                   &= (4, 1) - \left(\frac{6}{5}, \frac{12}{5}\right) \\
                   &= \left(4 - \frac{6}{5}, 1 - \frac{12}{5}\right) \\
                   &= \left(\frac{20}{5} - \frac{6}{5}, \frac{5}{5} - \frac{12}{5}\right) \\
                   &= \left(\frac{14}{5}, -\frac{7}{5}\right)
\end{aligned}
$$

- **Step 4: Compute the distance $d = \|\overrightarrow{QP}\|$:**
Apply the Euclidean norm:

$$
\begin{aligned}
d &= \|\overrightarrow{QP}\| \\
  &= \sqrt{\left(\frac{14}{5}\right)^2 + \left(-\frac{7}{5}\right)^2} \\
  &= \sqrt{\frac{196}{25} + \frac{49}{25}} \\
  &= \sqrt{\frac{196 + 49}{25}} \\
  &= \sqrt{\frac{245}{25}} \\
  &= \frac{\sqrt{245}}{\sqrt{25}} \\
  &= \frac{\sqrt{245}}{5}
\end{aligned}
$$

Simplify $\sqrt{245}$:

$$
\sqrt{245} = \sqrt{49 \cdot 5} = 7\sqrt{5}
$$

Therefore:

$$
d = \frac{7\sqrt{5}}{5}
$$

- **Step 5: Verify $\overrightarrow{QP} \cdot v = 0$:**
Compute the dot product of $\overrightarrow{QP} = \left(\frac{14}{5}, -\frac{7}{5}\right)$ and $v = (1, 2)$:

$$
\begin{aligned}
\overrightarrow{QP} \cdot v &= \frac{14}{5} \cdot 1 + \left(-\frac{7}{5}\right) \cdot 2 \\
                            &= \frac{14}{5} - \frac{14}{5} \\
                            &= 0
\end{aligned}
$$

3. **Evaluation:**
- The perpendicularity condition $\overrightarrow{QP} \cdot v = 0$ is exactly satisfied, confirming that the vector from $Q$ to $P$ is orthogonal to the line direction $v$. This geometrically means that $Q$ is indeed the foot of the perpendicular dropped from $P$ onto the line, and hence the closest point on the line to $P$.
- Among all points on the line (which have the form $t(1, 2)$ for $t \in \mathbb{R}$), the distance from that point to $P$ is minimized precisely when $t = \frac{6}{5}$, yielding $Q = \left(\frac{6}{5}, \frac{12}{5}\right)$.

## Final Answer

$$
Q = \left(\frac{6}{5}, \frac{12}{5}\right)
$$

$$
d = \frac{7\sqrt{5}}{5}
$$

$$
\overrightarrow{QP} \cdot v = \frac{14}{5} - \frac{14}{5} = 0
$$
