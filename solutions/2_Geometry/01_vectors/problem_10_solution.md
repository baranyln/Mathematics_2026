# Problem 10 Solution

## Problem Statement
The points $A=(0,0,0)$, $B=(2,1,0)$, and $C=(1,3,2)$ form a triangle. Construct $\overrightarrow{AB}$ and $\overrightarrow{AC}$, compute the area of the parallelogram using the cross product, and then find the area of the triangle. Explain the factor $\frac{1}{2}$.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Displacement Vectors from a Common Vertex: For three points $A, B, C$ in $\mathbb{R}^3$, the edge vectors from vertex $A$ are:

$$
\overrightarrow{AB} = B - A, \qquad \overrightarrow{AC} = C - A
$$

- Parallelogram Area via Cross Product: The area of the parallelogram spanned by two vectors $p$ and $q$ is:

$$
S_{\mathrm{parallelogram}} = \|p \times q\|
$$

- Triangle Area: The triangle formed by the two vectors shares one half of the area of the parallelogram:

$$
S_{\mathrm{triangle}} = \frac{1}{2} \|p \times q\|
$$

- Cross Product Formula: For $p = (p_1, p_2, p_3)$ and $q = (q_1, q_2, q_3)$:

$$
p \times q = (p_2 q_3 - p_3 q_2, \; p_3 q_1 - p_1 q_3, \; p_1 q_2 - p_2 q_1)
$$

- Formatting Standards: Display math with `$$` on separate lines, no `\text` macros, and all arithmetic products stated in full.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given three points in $\mathbb{R}^3$:

$$
A = (0, 0, 0), \qquad B = (2, 1, 0), \qquad C = (1, 3, 2)
$$

We will construct the two edge vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ emanating from vertex $A$, compute their cross product, determine the cross product's magnitude as the parallelogram area, halve it for the triangle area, and explain the geometric justification for the factor $\frac{1}{2}$.

2. **Intermediate Calculations:**
- **Step 1: Construct displacement vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$:**
Subtract the coordinates of $A$ from $B$:

$$
\begin{aligned}
\overrightarrow{AB} &= B - A \\
                   &= (2 - 0, 1 - 0, 0 - 0) \\
                   &= (2, 1, 0)
\end{aligned}
$$

Subtract the coordinates of $A$ from $C$:

$$
\begin{aligned}
\overrightarrow{AC} &= C - A \\
                   &= (1 - 0, 3 - 0, 2 - 0) \\
                   &= (1, 3, 2)
\end{aligned}
$$

- **Step 2: Compute the cross product $\overrightarrow{AB} \times \overrightarrow{AC}$:**
Let $p = \overrightarrow{AB} = (2, 1, 0)$ and $q = \overrightarrow{AC} = (1, 3, 2)$. Apply the component formulas:

$$
\begin{aligned}
(p \times q)_1 &= p_2 q_3 - p_3 q_2 = (1)(2) - (0)(3) = 2 - 0 = 2 \\
(p \times q)_2 &= p_3 q_1 - p_1 q_3 = (0)(1) - (2)(2) = 0 - 4 = -4 \\
(p \times q)_3 &= p_1 q_2 - p_2 q_1 = (2)(3) - (1)(1) = 6 - 1 = 5
\end{aligned}
$$

Assembling all three components:

$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

- **Step 3: Compute the magnitude of the cross product:**
Apply the Euclidean norm formula to $(2, -4, 5)$:

$$
\begin{aligned}
\|\overrightarrow{AB} \times \overrightarrow{AC}\| &= \sqrt{2^2 + (-4)^2 + 5^2} \\
                                                   &= \sqrt{4 + 16 + 25} \\
                                                   &= \sqrt{45} \\
                                                   &= \sqrt{9 \cdot 5} \\
                                                   &= 3\sqrt{5}
\end{aligned}
$$

- **Step 4: Compute the parallelogram and triangle areas:**
The area of the parallelogram spanned by $\overrightarrow{AB}$ and $\overrightarrow{AC}$:

$$
S_{\mathrm{parallelogram}} = \|\overrightarrow{AB} \times \overrightarrow{AC}\| = 3\sqrt{5}
$$

The area of triangle $ABC$:

$$
S_{\mathrm{triangle}} = \frac{1}{2} \|\overrightarrow{AB} \times \overrightarrow{AC}\| = \frac{3\sqrt{5}}{2}
$$

3. **Evaluation & Geometric Justification of the Factor $\frac{1}{2}$:**
- **Geometric Explanation:**
The two vectors $\overrightarrow{AB}$ and $\overrightarrow{AC}$ define a parallelogram in $\mathbb{R}^3$. This parallelogram has $A$ as one corner, with $\overrightarrow{AB}$ and $\overrightarrow{AC}$ as its two adjacent sides. The main diagonal of this parallelogram connects $A$ to the opposite corner, dividing the parallelogram into two congruent triangles of equal area. Triangle $ABC$ corresponds to exactly one of these two halves. Therefore, the triangle area is exactly one half of the parallelogram area, yielding the factor $\frac{1}{2}$.

## Final Answer

$$
\overrightarrow{AB} = (2, 1, 0), \qquad \overrightarrow{AC} = (1, 3, 2)
$$

$$
\overrightarrow{AB} \times \overrightarrow{AC} = (2, -4, 5)
$$

$$
S_{\mathrm{parallelogram}} = 3\sqrt{5}
$$

$$
S_{\mathrm{triangle}} = \frac{3\sqrt{5}}{2}
$$
