# Problem 03 Solution

## Problem Statement
For $v=(3,4)$ find a unit vector $e$ with the same direction and orientation. Check that $\|e\|=1$, reconstruct $v$ in the form $v=\|v\|e$, and explain what changes during normalization and what remains unchanged.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Vector Length (Euclidean Norm in $\mathbb{R}^2$): For $v = (v_1, v_2)$, the length is:

$$
\|v\| = \sqrt{v_1^2 + v_2^2}
$$

- Vector Normalization: A unit vector $e$ pointing in the exact same direction and orientation as a non-zero vector $v$ is obtained by multiplying $v$ by the reciprocal of its norm:

$$
e = \frac{v}{\|v\|} = \left(\frac{v_1}{\|v\|}, \frac{v_2}{\|v\|}\right)
$$

- Unit Length Verification: By linearity of the norm, $\|e\| = \left\|\frac{v}{\|v\|}\right\| = \frac{1}{\|v\|}\|v\| = 1$.
- Vector Reconstruction: Any non-zero vector can be factored into its magnitude and its unit direction vector:

$$
v = \|v\| e
$$

- Formatting Standards: All display mathematics blocks are enclosed in `$$` with blank lines before and after. No `\text` macros are used (using Markdown text or `\mathrm`).

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given the two-dimensional vector:

$$
v = (3, 4)
$$

To normalize $v$, we first calculate its Euclidean magnitude $\|v\|$, construct the unit vector $e = \frac{1}{\|v\|}v$, verify that $\|e\| = 1$, confirm the reconstruction $v = \|v\|e$, and analyze the geometric effects of normalization.

2. **Intermediate Calculations:**
- **Step 1: Compute the length of $v$:**
Apply the norm formula:

$$
\begin{aligned}
\|v\| &= \sqrt{3^2 + 4^2} \\
      &= \sqrt{9 + 16} \\
      &= \sqrt{25} \\
      &= 5
\end{aligned}
$$

- **Step 2: Construct the unit vector $e$:**
Divide each component of $v$ by the norm $\|v\| = 5$:

$$
\begin{aligned}
e &= \frac{v}{\|v\|} \\
  &= \frac{1}{5}(3, 4) \\
  &= \left(\frac{3}{5}, \frac{4}{5}\right)
\end{aligned}
$$

- **Step 3: Verify that $\|e\| = 1$:**
Compute the norm of $e$ using component-wise arithmetic:

$$
\begin{aligned}
\|e\| &= \sqrt{\left(\frac{3}{5}\right)^2 + \left(\frac{4}{5}\right)^2} \\
      &= \sqrt{\frac{9}{25} + \frac{16}{25}} \\
      &= \sqrt{\frac{9 + 16}{25}} \\
      &= \sqrt{\frac{25}{25}} \\
      &= \sqrt{1} \\
      &= 1
\end{aligned}
$$

- **Step 4: Reconstruct $v$ from $\|v\|e$:**
Multiply the unit vector $e$ by the scalar magnitude $\|v\| = 5$:

$$
\begin{aligned}
\|v\| e &= 5 \left(\frac{3}{5}, \frac{4}{5}\right) \\
        &= \left(5 \cdot \frac{3}{5}, 5 \cdot \frac{4}{5}\right) \\
        &= (3, 4) \\
        &= v
\end{aligned}
$$

The identity $v = \|v\|e$ is verified.

3. **Evaluation & Geometric Explanation:**
- **What changes during normalization:**
The length (magnitude) of the vector changes. The initial length was $\|v\| = 5$, and after dividing by $5$, the new length is exactly $\|e\| = 1$. The vector is rescaled to a standard unit size.
- **What remains unchanged:**
  1. **Direction (Line of action):** The slope of the line passing through the vector remains unchanged:

$$
m = \frac{v_2}{v_1} = \frac{4}{3}, \qquad m_e = \frac{4/5}{3/5} = \frac{4}{3}
$$

  2. **Orientation (Sense):** Because the scaling factor $\frac{1}{\|v\|} = \frac{1}{5}$ is strictly positive ($> 0$), the vector points in the exact same direction along that line (towards the first quadrant in $\mathbb{R}^2$).

Normalization isolates the pure directional information of the vector by decoupling it from its magnitude.

## Final Answer

$$
e = \left(\frac{3}{5}, \frac{4}{5}\right)
$$

$$
\|e\| = 1
$$

$$
v = 5 \left(\frac{3}{5}, \frac{4}{5}\right) = (3, 4)
$$
