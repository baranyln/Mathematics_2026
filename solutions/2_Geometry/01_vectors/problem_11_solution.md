# Problem 11 Solution

## Problem Statement
Decompose $u=(3,4)$ into components parallel and perpendicular to $v=(1,2)$. Check

$$
u=u_{\parallel}+u_{\perp},\qquad u_{\perp}\cdot v=0.
$$

Explain why these are two independent checks of correctness.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Orthogonal Decomposition of a Vector: Any vector $u$ can be uniquely decomposed with respect to a non-zero direction vector $v$ into:

$$
u = u_{\parallel} + u_{\perp}
$$

where $u_{\parallel}$ is the component of $u$ parallel to $v$ and $u_{\perp}$ is the component perpendicular to $v$.
- Parallel Component (Vector Projection):

$$
u_{\parallel} = \mathrm{proj}_v\,u = \frac{u \cdot v}{v \cdot v} v
$$

- Perpendicular Component (Residual):

$$
u_{\perp} = u - u_{\parallel}
$$

- Perpendicularity Check: The residual must satisfy $u_{\perp} \cdot v = 0$.
- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products stated in full.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two vectors in $\mathbb{R}^2$:

$$
u = (3, 4), \qquad v = (1, 2)
$$

We will compute the scalar dot products $u \cdot v$ and $v \cdot v$, evaluate the parallel component $u_{\parallel} = \mathrm{proj}_v\,u$, compute the perpendicular component $u_{\perp} = u - u_{\parallel}$, and verify both correctness conditions: the sum $u_{\parallel} + u_{\perp} = u$ and the orthogonality $u_{\perp} \cdot v = 0$.

2. **Intermediate Calculations:**
- **Step 1: Compute $u \cdot v$ and $v \cdot v$:**
For $u \cdot v$:

$$
\begin{aligned}
u \cdot v &= (3)(1) + (4)(2) \\
          &= 3 + 8 \\
          &= 11
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

- **Step 2: Compute the parallel component $u_{\parallel}$:**
Multiply $v$ by the projection scalar $\frac{u \cdot v}{v \cdot v} = \frac{11}{5}$:

$$
\begin{aligned}
u_{\parallel} &= \frac{u \cdot v}{v \cdot v} v \\
              &= \frac{11}{5} (1, 2) \\
              &= \left(\frac{11}{5} \cdot 1, \frac{11}{5} \cdot 2\right) \\
              &= \left(\frac{11}{5}, \frac{22}{5}\right)
\end{aligned}
$$

- **Step 3: Compute the perpendicular component $u_{\perp}$:**
Subtract $u_{\parallel}$ from $u$:

$$
\begin{aligned}
u_{\perp} &= u - u_{\parallel} \\
          &= (3, 4) - \left(\frac{11}{5}, \frac{22}{5}\right) \\
          &= \left(3 - \frac{11}{5}, 4 - \frac{22}{5}\right) \\
          &= \left(\frac{15}{5} - \frac{11}{5}, \frac{20}{5} - \frac{22}{5}\right) \\
          &= \left(\frac{4}{5}, -\frac{2}{5}\right)
\end{aligned}
$$

- **Step 4: Check 1 — Verify $u_{\parallel} + u_{\perp} = u$:**
Add the two components:

$$
\begin{aligned}
u_{\parallel} + u_{\perp} &= \left(\frac{11}{5}, \frac{22}{5}\right) + \left(\frac{4}{5}, -\frac{2}{5}\right) \\
                           &= \left(\frac{11}{5} + \frac{4}{5}, \frac{22}{5} - \frac{2}{5}\right) \\
                           &= \left(\frac{15}{5}, \frac{20}{5}\right) \\
                           &= (3, 4) \\
                           &= u
\end{aligned}
$$

The sum identity is verified.

- **Step 5: Check 2 — Verify $u_{\perp} \cdot v = 0$:**
Compute the dot product:

$$
\begin{aligned}
u_{\perp} \cdot v &= \left(\frac{4}{5}, -\frac{2}{5}\right) \cdot (1, 2) \\
                  &= \frac{4}{5} \cdot 1 + \left(-\frac{2}{5}\right) \cdot 2 \\
                  &= \frac{4}{5} - \frac{4}{5} \\
                  &= 0
\end{aligned}
$$

The orthogonality condition is satisfied.

3. **Evaluation & Explanation of Two Independent Checks:**
- **Check 1 (Sum Identity) — Completeness Verification:**
The condition $u_{\parallel} + u_{\perp} = u$ ensures that together the two components exactly reconstitute the original vector $u$. No part of $u$ is lost or duplicated in the decomposition. This check verifies that we have partitioned all of $u$ into exactly two parts.

- **Check 2 (Orthogonality) — Perpendicularity Verification:**
The condition $u_{\perp} \cdot v = 0$ verifies that the perpendicular component is geometrically orthogonal to the direction of decomposition $v$. This check ensures that $u_{\perp}$ genuinely represents the component of $u$ lying in the subspace perpendicular to $v$, not some arbitrary vector.

- **Why they are independent:** The sum identity alone does not guarantee orthogonality (one could add any vector to $u_{\parallel}$ and subtract the same vector from $u_{\perp}$ and preserve the sum). The orthogonality condition alone does not guarantee the decomposition is of $u$ specifically. Both checks together uniquely characterize the orthogonal decomposition.

## Final Answer

$$
u_{\parallel} = \left(\frac{11}{5}, \frac{22}{5}\right)
$$

$$
u_{\perp} = \left(\frac{4}{5}, -\frac{2}{5}\right)
$$

$$
u_{\parallel} + u_{\perp} = (3, 4) = u
$$

$$
u_{\perp} \cdot v = \frac{4}{5} - \frac{4}{5} = 0
$$
