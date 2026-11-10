# Problem 03 Solution

## Problem Statement
Solve or show that the system is inconsistent:

$$
\begin{cases}
x+2y=3, \\
2x+4y=7.
\end{cases}
$$

Show how the contradiction appears in the matrix after elimination and interpret it in terms of equations.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Criteria for Inconsistency (Rouché-Capelli Theorem): A linear system is inconsistent (possesses no solution) if and only if the rank of the coefficient matrix is strictly less than the rank of the augmented matrix: $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$.
- Identifying Contradictions in Row Echelon Form: An inconsistent system produces a row of the form $\begin{pmatrix} 0 & 0 & \dots & 0 & \mid & c \end{pmatrix}$ where $c \neq 0$, corresponding to the algebraic impossibility $0 = c$.
- Geometric Interpretation: Two linear equations in two variables that yield no solution represent two distinct parallel lines in the Euclidean plane.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We are given the system of 2 linear equations in 2 unknowns ($x, y$):

$$
\begin{cases}
x + 2y = 3, \\
2x + 4y = 7.
\end{cases}
$$

We formulate the augmented matrix $[A \mid b]$:

$$
\begin{pmatrix}
1 & 2 & \mid & 3 \\
2 & 4 & \mid & 7 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
We perform Gaussian elimination to eliminate the unknown $x$ from the second row using the elementary row operation $R_2 \leftarrow R_2 - 2R_1$.

We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 4 - 2(2) = 4 - 4 = 0 \\
r_{23} &= 7 - 2(3) = 7 - 6 = 1
\end{aligned}
$$

The augmented matrix after elimination is:

$$
\begin{pmatrix}
1 & 2 & \mid & 3 \\
0 & 0 & \mid & 1 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
**Interpretation of the Contradiction:**
Translating the second row of the reduced augmented matrix back into an algebraic equation:

$$
0x + 0y = 1
$$

Since $0x + 0y = 0$ for all real numbers $x$ and $y$, this simplifies to:

$$
0 = 1.
$$

This is a mathematical contradiction (a false statement), proving that no pair of numbers $(x, y)$ can satisfy both equations simultaneously.

**Rank Analysis (Rouché-Capelli Theorem):**
- The coefficient matrix has one non-zero row:

$$
\mathrm{rank}(A) = 1.
$$

- The augmented matrix has two non-zero rows (with a pivot in the constant column):

$$
\mathrm{rank}([A \mid b]) = 2.
$$

- Since $\mathrm{rank}(A) = 1 \neq 2 = \mathrm{rank}([A \mid b])$, the system is inconsistent.

**Geometric Interpretation in Terms of Lines:**
We express each equation in slope-intercept form ($y = mx + k$):
- First equation:

$$
x + 2y = 3 \implies 2y = -x + 3 \implies y = -\frac{1}{2}x + \frac{3}{2}
$$

- Second equation:

$$
2x + 4y = 7 \implies 4y = -2x + 7 \implies y = -\frac{1}{2}x + \frac{7}{4}
$$

Both lines have the identical slope $m = -\frac{1}{2}$, which means they are parallel.
However, their $y$-intercepts are different:

$$
\frac{3}{2} \neq \frac{7}{4}.
$$

Because the lines are parallel and distinct, they never intersect at any point in $\mathbb{R}^2$. Hence, the system has no solution.

## Final Answer

The system has no solution (it is inconsistent).
