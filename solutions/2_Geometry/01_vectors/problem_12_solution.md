# Problem 12 Solution

## Problem Statement
Given $A=(1,0,2)$, $B=(2,1,0)$, and $C=(0,3,1)$. Construct two vectors lying in the plane, find a vector perpendicular to both, and check the perpendicularity using dot products.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Plane Edge Vectors: Two distinct directions in a plane through points $A, B, C$ are obtained from displacement vectors rooted at a common vertex:

$$
\overrightarrow{AB} = B - A, \qquad \overrightarrow{AC} = C - A
$$

- Normal Vector via Cross Product: A vector perpendicular (normal) to the plane spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$ is:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC}
$$

- Cross Product Formula:

$$
p \times q = (p_2 q_3 - p_3 q_2, \; p_3 q_1 - p_1 q_3, \; p_1 q_2 - p_2 q_1)
$$

- Orthogonality Verification:

$$
n \cdot \overrightarrow{AB} = 0, \qquad n \cdot \overrightarrow{AC} = 0
$$

- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products stated explicitly.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given three points in $\mathbb{R}^3$:

$$
A = (1, 0, 2), \qquad B = (2, 1, 0), \qquad C = (0, 3, 1)
$$

We will construct the two edge vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ lying in the plane through $A, B, C$, compute their cross product to obtain the normal vector $n$, and verify perpendicularity of $n$ to both edge vectors via dot products.

2. **Intermediate Calculations:**
- **Step 1: Construct displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$:**
Subtract the coordinates of $A$ from $B$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                   &= (2 - 1, 1 - 0, 0 - 2) \\
                   &= (1, 1, -2)
\end{aligned}
$$

Subtract the coordinates of $A$ from $C$:

$$
\begin{aligned}
\overrightarrow{AC} &= C - A \\
                   &= (0 - 1, 3 - 0, 1 - 2) \\
                   &= (-1, 3, -1)
\end{aligned}
$$

- **Step 2: Compute the cross product $n = \overrightarrow{AB} \times \overrightarrow{AC}$:**
Let $p = \overrightarrow{AB} = (1, 1, -2)$ and $q = \overrightarrow{AC} = (-1, 3, -1)$. Apply the component formulas:

$$
\begin{aligned}
n_1 &= p_2 q_3 - p_3 q_2 = (1)(-1) - (-2)(3) = -1 + 6 = 5 \\
n_2 &= p_3 q_1 - p_1 q_3 = (-2)(-1) - (1)(-1) = 2 + 1 = 3 \\
n_3 &= p_1 q_2 - p_2 q_1 = (1)(3) - (1)(-1) = 3 + 1 = 4
\end{aligned}
$$

Assembling the components:

$$
n = \overrightarrow{AB} \times \overrightarrow{AC} = (5, 3, 4)
$$

- **Step 3: Verify that $n \cdot \overrightarrow{AB} = 0$:**
Compute the dot product of $n = (5, 3, 4)$ with $\overrightarrow{AB} = (1, 1, -2)$:

$$
\begin{aligned}
n \cdot \overrightarrow{AB} &= (5)(1) + (3)(1) + (4)(-2) \\
                            &= 5 + 3 - 8 \\
                            &= 0
\end{aligned}
$$

- **Step 4: Verify that $n \cdot \overrightarrow{AC} = 0$:**
Compute the dot product of $n = (5, 3, 4)$ with $\overrightarrow{AC} = (-1, 3, -1)$:

$$
\begin{aligned}
n \cdot \overrightarrow{AC} &= (5)(-1) + (3)(3) + (4)(-1) \\
                            &= -5 + 9 - 4 \\
                            &= 0
\end{aligned}
$$

3. **Evaluation:**
- Both dot products are exactly zero, confirming that $n = (5, 3, 4)$ is perpendicular to both vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ lying in the plane.
- The vector $n = (5, 3, 4)$ is therefore a normal vector to the plane passing through the three points $A, B, C$.
- In the equation of the plane $n_1(x - x_A) + n_2(y - y_A) + n_3(z - z_A) = 0$, substituting the normal vector and vertex $A = (1, 0, 2)$ yields: $5(x-1) + 3(y-0) + 4(z-2) = 0$, or equivalently $5x + 3y + 4z = 13$.

## Final Answer

$$
\overrightarrow{AB} = (1, 1, -2), \qquad \overrightarrow{AC} = (-1, 3, -1)
$$

$$
n = \overrightarrow{AB} \times \overrightarrow{AC} = (5, 3, 4)
$$

$$
n \cdot \overrightarrow{AB} = 0, \qquad n \cdot \overrightarrow{AC} = 0
$$
