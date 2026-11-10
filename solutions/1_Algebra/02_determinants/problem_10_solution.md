# Problem 10 Solution

## Problem Statement
Without carrying out a full determinant calculation, explain why

$$
\det
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5 \\
\end{pmatrix}=0.
$$

Identify a specific dependence between the rows and connect it with noninvertibility of the matrix.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Linear Dependence and Determinants: If one row of a square matrix is a scalar multiple of another row (or if the set of rows is linearly dependent), the determinant of the matrix is zero.
- Row Operation Invariance: Adding a scalar multiple of one row to another ($R_i \leftarrow R_i + c R_j$) preserves the determinant. Producing a row of zeros confirms that the determinant is zero.
- Invertibility and Full Rank: A matrix $A \in \mathbb{R}^{n \times n}$ is invertible if and only if its rows form a linearly independent set ($\mathrm{rank}(A) = n$), which holds if and only if $\det A \neq 0$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
Let the given matrix be denoted by $A$:

$$
A =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 5 \\
\end{pmatrix}.
$$

We denote the row vectors of matrix $A$ in $\mathbb{R}^3$ as:

$$
R_1 =
\begin{pmatrix}
1 & 2 & 3 \\
\end{pmatrix}
$$

$$
R_2 =
\begin{pmatrix}
2 & 4 & 6 \\
\end{pmatrix}
$$

$$
R_3 =
\begin{pmatrix}
0 & 1 & 5 \\
\end{pmatrix}.
$$

We examine the relationships between these rows to identify a linear dependence without evaluating the full Leibniz or Sarrus expansion.

2. **Intermediate Calculations:**
We compare Row 1 and Row 2 component by component:

$$
\begin{aligned}
r_{21} &= 2 = 2 \cdot 1 = 2 \cdot r_{11} \\
r_{22} &= 4 = 2 \cdot 2 = 2 \cdot r_{12} \\
r_{23} &= 6 = 2 \cdot 3 = 2 \cdot r_{13}
\end{aligned}
$$

Thus, Row 2 is an exact scalar multiple of Row 1:

$$
R_2 = 2 R_1
$$

Equivalently, this relation can be written as:

$$
R_2 - 2 R_1 =
\begin{pmatrix}
0 & 0 & 0 \\
\end{pmatrix}.
$$

Applying the row operation $R_2 \leftarrow R_2 - 2R_1$, which preserves the determinant, yields:

$$
\det A = \det
\begin{pmatrix}
1 & 2 & 3 \\
0 & 0 & 0 \\
0 & 1 & 5 \\
\end{pmatrix}.
$$

Expanding along the second row:

$$
\det A = 0 \cdot C_{21} + 0 \cdot C_{22} + 0 \cdot C_{23} = 0
$$

3. **Arithmetic Evaluation & Connection to Non-Invertibility:**
The calculation shows:

$$
\det(A) = 0
$$

**Connection to Non-Invertibility:**
- A square matrix $A \in \mathbb{R}^{3 \times 3}$ is invertible if and only if its rows form a linearly independent set, meaning that the matrix has full row rank:

$$
\mathrm{rank}(A) = 3
$$

- Because Row 2 is a scalar multiple of Row 1 ($R_2 = 2R_1$), the row vectors $\{R_1, R_2, R_3\}$ are linearly dependent. The dimension of the span of these rows is strictly less than 3:

$$
\mathrm{rank}(A) \le 2 < 3
$$

- By the Rank-Nullity Theorem, the dimension of the nullspace (kernel) of $A$ satisfies:

$$
\mathrm{dim}(\ker A) = 3 - \mathrm{rank}(A) \ge 1 > 0
$$

- The existence of non-zero vectors in the nullspace means that the linear mapping $x \mapsto Ax$ is not injective, so no two-sided inverse matrix $A^{-1}$ exists. This non-invertibility is equivalent to having a determinant equal to zero.

## Final Answer

$$
\det(A) = 0
$$
