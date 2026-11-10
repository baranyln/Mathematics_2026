# Problem 08 Solution

## Problem Statement
Check whether $w=(5,1)$ can be written as

$$
w=au+bv,
$$

where $u=(1,1)$ and $v=(2,-1)$. If so, find $a,b$, reconstruct $w$ from them, and explain the geometric meaning of the existence of such coefficients.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Linear Combination in $\mathbb{R}^2$: Expressing a target vector $w = (w_1, w_2)$ as a linear combination of vectors $u = (u_1, u_2)$ and $v = (v_1, v_2)$ corresponds to finding scalar coefficients $a, b \in \mathbb{R}$ satisfying:

$$
a \begin{pmatrix} u_1 \\ u_2 \end{pmatrix} + b \begin{pmatrix} v_1 \\ v_2 \end{pmatrix} = \begin{pmatrix} w_1 \\ w_2 \end{pmatrix}
$$

- System of Linear Equations: This vector equation is equivalent to a $2 \times 2$ linear system:

$$
\begin{cases}
u_1 a + v_1 b = w_1, \\
u_2 a + v_2 b = w_2.
\end{cases}
$$

(As specified in Section 5 of `hints.md`, each row of `cases` is placed on its own source line).
- Vector Reconstruction: Substitute the computed scalars back into $au + bv$ to verify arithmetic correctness.
- Geometric Meaning: Non-collinear vectors in $\mathbb{R}^2$ form a basis for the plane, and $(a, b)$ are the coordinates of $w$ with respect to that basis.
- Formatting Standards: Display math delimited with `$$` on independent lines, no `\text` macros, and all algebraic steps written out in full.

## Detailed Step-by-Step Solution
1. **Vector Setup & Formula Selection:**
We are given the vectors:

$$
u = (1, 1), \qquad v = (2, -1), \qquad w = (5, 1)
$$

We set up the vector equation $au + bv = w$, expand it into a system of two scalar linear equations in the unknowns $a$ and $b$, solve the system, perform explicit vector reconstruction to verify $w$, and interpret the geometric significance.

2. **Intermediate Calculations:**
- **Step 1: Set up the linear system:**
Write the vector equation component-wise:

$$
a(1, 1) + b(2, -1) = (5, 1)
$$

$$
(a, a) + (2b, -b) = (5, 1)
$$

$$
(a + 2b, a - b) = (5, 1)
$$

Equating corresponding components yields the system:

$$
\begin{cases}
a + 2b = 5, \\
a - b = 1.
\end{cases}
$$

- **Step 2: Solve the system for $a$ and $b$:**
From the second equation, express $a$ in terms of $b$:

$$
a = 1 + b
$$

Substitute this expression into the first equation:

$$
\begin{aligned}
(1 + b) + 2b &= 5 \\
1 + 3b &= 5 \\
3b &= 5 - 1 \\
3b &= 4 \\
b &= \frac{4}{3}
\end{aligned}
$$

Now substitute $b = \frac{4}{3}$ back to find $a$:

$$
\begin{aligned}
a &= 1 + \frac{4}{3} \\
  &= \frac{3}{3} + \frac{4}{3} \\
  &= \frac{7}{3}
\end{aligned}
$$

Thus, the unique solution is $a = \frac{7}{3}$ and $b = \frac{4}{3}$.

- **Step 3: Reconstruct $w$ from $a$ and $b$:**
Substitute the values of $a$ and $b$ back into the linear combination $au + bv$:

$$
\begin{aligned}
au + bv &= \frac{7}{3}(1, 1) + \frac{4}{3}(2, -1) \\
        &= \left(\frac{7}{3} \cdot 1, \frac{7}{3} \cdot 1\right) + \left(\frac{4}{3} \cdot 2, \frac{4}{3} \cdot (-1)\right) \\
        &= \left(\frac{7}{3}, \frac{7}{3}\right) + \left(\frac{8}{3}, -\frac{4}{3}\right) \\
        &= \left(\frac{7}{3} + \frac{8}{3}, \frac{7}{3} - \frac{4}{3}\right) \\
        &= \left(\frac{15}{3}, \frac{3}{3}\right) \\
        &= (5, 1) \\
        &= w
\end{aligned}
$$

The reconstruction confirms that $w = \frac{7}{3}u + \frac{4}{3}v$.

3. **Evaluation & Geometric Explanation:**
- **Geometric Meaning of the Coefficients:**
1. **Basis of the Plane:** The vectors $u = (1, 1)$ and $v = (2, -1)$ are linearly independent because they are not scalar multiples of each other (the slope of $u$ is $1$, while the slope of $v$ is $-1/2$). In a 2-dimensional space ($\mathbb{R}^2$), any two linearly independent vectors form a **basis**.
2. **Coordinate Decomposition:** Because $\{u, v\}$ forms a basis, every vector in $\mathbb{R}^2$ can be uniquely represented as a linear combination of $u$ and $v$. The scalars $a = \frac{7}{3}$ and $b = \frac{4}{3}$ are the coordinates of vector $w$ in this oblique (non-orthogonal) coordinate frame.
3. **Parallelogram Rule:** Geometrically, $w$ is the main diagonal of a parallelogram whose sides are formed by scaling vector $u$ by a factor of $\frac{7}{3}$ and vector $v$ by a factor of $\frac{4}{3}$.

## Final Answer

$$
a = \frac{7}{3}, \qquad b = \frac{4}{3}
$$

$$
w = \frac{7}{3}u + \frac{4}{3}v = \frac{7}{3}(1, 1) + \frac{4}{3}(2, -1) = (5, 1)
$$
