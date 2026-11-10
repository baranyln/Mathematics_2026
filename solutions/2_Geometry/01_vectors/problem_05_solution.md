# Problem 05 Solution

## Problem Statement
Given $u=(1,1,0)$ and $v=(1,0,1)$:

1. Use the sign of $u\cdot v$ to predict the type of angle.
2. Compute the angle.
3. Compare the result with the prediction.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Dot Product and Angle Relation: For two non-zero vectors $u$ and $v$, the dot product satisfies:

$$
u \cdot v = \|u\| \, \|v\| \cos \theta
$$

where $\theta \in [0, \pi]$ is the angle between the vectors.
- Qualitative Angle Prediction by Sign: Since norms $\|u\| > 0$ and $\|v\| > 0$ are strictly positive:
  - $u \cdot v > 0 \implies \cos \theta > 0 \implies \theta \in [0, \pi/2)$ (acute angle).
  - $u \cdot v = 0 \implies \cos \theta = 0 \implies \theta = \pi/2$ (right angle / perpendicular).
  - $u \cdot v < 0 \implies \cos \theta < 0 \implies \theta \in (\pi/2, \pi]$ (obtuse angle).
- Exact Angle Formula:

$$
\cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|} \implies \theta = \arccos\left(\frac{u \cdot v}{\|u\| \, \|v\|}\right)
$$

- Formatting Standards: Display mathematics delimited by `$$` on separate lines, no `\text` macros, and all arithmetic steps shown explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in $\mathbb{R}^3$:

$$
u = (1, 1, 0), \qquad v = (1, 0, 1)
$$

First, we calculate the dot product $u \cdot v$ and determine its algebraic sign to classify whether $\theta$ is acute, right, or obtuse. Second, we compute the magnitudes $\|u\|$ and $\|v\|$ to evaluate $\cos \theta$ and determine the exact angle $\theta$ in radians and degrees. Third, we compare the quantitative value with the initial prediction.

2. **Intermediate Calculations:**
- **Step 1: Compute $u \cdot v$ and predict angle type:**
Evaluate the component-wise dot product:

$$
\begin{aligned}
u \cdot v &= (1)(1) + (1)(0) + (0)(1) \\
          &= 1 + 0 + 0 \\
          &= 1
\end{aligned}
$$

Since $u \cdot v = 1 > 0$, the cosine of the angle must be positive:

$$
\cos \theta = \frac{u \cdot v}{\|u\| \, \|v\|} > 0
$$

Because $\theta \in [0, \pi]$, $\cos \theta > 0$ implies:

$$
0 \le \theta < \frac{\pi}{2} \quad (0^\circ \le \theta < 90^\circ)
$$

Thus, we predict that the angle is **acute**.

- **Step 2: Compute the magnitudes $\|u\|$ and $\|v\|$:**
For $u = (1, 1, 0)$:

$$
\begin{aligned}
\|u\| &= \sqrt{1^2 + 1^2 + 0^2} \\
      &= \sqrt{1 + 1 + 0} \\
      &= \sqrt{2}
\end{aligned}
$$

For $v = (1, 0, 1)$:

$$
\begin{aligned}
\|v\| &= \sqrt{1^2 + 0^2 + 1^2} \\
      &= \sqrt{1 + 0 + 1} \\
      &= \sqrt{2}
\end{aligned}
$$

- **Step 3: Compute $\cos \theta$ and exact angle $\theta$:**
Substitute the values into the cosine formula:

$$
\begin{aligned}
\cos \theta &= \frac{u \cdot v}{\|u\| \, \|v\|} \\
            &= \frac{1}{\sqrt{2} \cdot \sqrt{2}} \\
            &= \frac{1}{2}
\end{aligned}
$$

Now find $\theta = \arccos(1/2)$:

$$
\theta = \frac{\pi}{3} = 60^\circ
$$

3. **Evaluation & Comparison:**
- **Comparison with Prediction:**
The exact calculation yields $\theta = \frac{\pi}{3} = 60^\circ$.
Since $0^\circ < 60^\circ < 90^\circ$, the angle is strictly acute, which perfectly validates the qualitative prediction made solely from the positive sign of $u \cdot v = 1$.

## Final Answer

$$
u \cdot v = 1 > 0 \implies \theta \mathrm{\ is\ acute}
$$

$$
\cos \theta = \frac{1}{2}
$$

$$
\theta = \frac{\pi}{3} = 60^\circ
$$
