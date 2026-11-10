# Problem 02 Solution

## Problem Statement
The points are $A=(1,2,3)$ and $B=(4,-2,6)$.

1. Construct $\overrightarrow{AB}$.
2. Compute its length.
3. Compute the distance between the points using the coordinate formula.
4. Explain why both calculations give the same result.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Displacement Vector: Given two points $A = (x_A, y_A, z_A)$ and $B = (x_B, y_B, z_B)$ in $\mathbb{R}^3$, the directed displacement vector from $A$ to $B$ is obtained by subtracting the initial coordinates from the terminal coordinates:

$$
\overrightarrow{AB} = B - A = (x_B - x_A, y_B - y_A, z_B - z_A)
$$

- Euclidean Norm (Vector Length): For any vector $v = (v_1, v_2, v_3) \in \mathbb{R}^3$, its length (magnitude) is:

$$
\|v\| = \sqrt{v_1^2 + v_2^2 + v_3^2}
$$

- Coordinate Distance Formula: The Euclidean distance $d(A, B)$ between points $A$ and $B$ is:

$$
d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$

- Geometric Equivalence: The distance between two points is mathematically defined as the length of the displacement vector separating them.
- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros (use `\mathrm` or prose outside math blocks), and no skipped calculation steps.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given two points in three-dimensional space $\mathbb{R}^3$:

$$
A = (1, 2, 3), \qquad B = (4, -2, 6)
$$

We will first determine the components of the displacement vector $\overrightarrow{AB}$, then compute the magnitude $\|\overrightarrow{AB}\|$, independently compute $d(A, B)$ via the coordinate distance formula, and explain their structural equivalence.

2. **Intermediate Calculations:**
- **Step 1: Construct the displacement vector $\overrightarrow{AB}$:**
Subtract the coordinates of point $A$ from the coordinates of point $B$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                   &= (4 - 1, -2 - 2, 6 - 3) \\
                   &= (3, -4, 3)
\end{aligned}
$$

- **Step 2: Compute the length of $\overrightarrow{AB}$:**
Apply the Euclidean norm definition to the vector components $(3, -4, 3)$:

$$
\begin{aligned}
\|\overrightarrow{AB}\| &= \sqrt{3^2 + (-4)^2 + 3^2} \\
                       &= \sqrt{9 + 16 + 9} \\
                       &= \sqrt{34}
\end{aligned}
$$

- **Step 3: Compute the distance $d(A, B)$ using the coordinate formula:**
Substitute the point coordinates into the standard distance formula:

$$
\begin{aligned}
d(A, B) &= \sqrt{(4 - 1)^2 + (-2 - 2)^2 + (6 - 3)^2} \\
        &= \sqrt{(3)^2 + (-4)^2 + (3)^2} \\
        &= \sqrt{9 + 16 + 9} \\
        &= \sqrt{34}
\end{aligned}
$$

3. **Evaluation & Geometric Justification:**
- **Comparison:**
Both calculations yield precisely $\sqrt{34}$.
- **Geometric Explanation:**
The coordinate distance formula computes the square root of the sum of the squared differences between corresponding coordinates along each axis:

$$
d(A, B) = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$

The components of the displacement vector $\overrightarrow{AB}$ are defined precisely as these coordinate differences:

$$
v_1 = x_B - x_A, \qquad v_2 = y_B - y_A, \qquad v_3 = z_B - z_A
$$

Computing the length of $\overrightarrow{AB}$ involves taking the square root of the sum of the squares of its components:

$$
\|\overrightarrow{AB}\| = \sqrt{v_1^2 + v_2^2 + v_3^2} = \sqrt{(x_B - x_A)^2 + (y_B - y_A)^2 + (z_B - z_A)^2}
$$

Consequently, the two formulas represent the exact same mathematical operation. Geometrically, the distance between two points in Euclidean space is defined as the length of the straight-line segment connecting them, which is the magnitude of the displacement vector $\overrightarrow{AB}$.

## Final Answer

$$
\overrightarrow{AB} = (3, -4, 3)
$$

$$
\|\overrightarrow{AB}\| = \sqrt{34}
$$

$$
d(A, B) = \sqrt{34}
$$
