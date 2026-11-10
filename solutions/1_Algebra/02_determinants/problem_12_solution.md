# Problem 12 Solution

## Problem Statement
For

$$
A(t)=
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & t \\
0 & 1 & 1 \\
\end{pmatrix}
$$

find the values of $t$ for which the matrix is not invertible.

Before computing the determinant, perform the operation

$$
R_2\leftarrow R_2-2R_1
$$

and use the resulting structure. At the end, explain what special thing happens to the rows for the value of the parameter you found.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Row Operation Invariance: Adding a scalar multiple of one row to another ($R_2 \leftarrow R_2 - 2R_1$) preserves the determinant: $\det B(t) = \det A(t)$.
- Laplace Cofactor Expansion: Expanding along a column containing multiple zeros simplifies the determinant calculation to a single $2 \times 2$ block.
- Non-Invertibility Criterion: A square matrix is not invertible if and only if its determinant is zero.
- Linear Dependence of Rows: The parameter value causing singularity reveals a proportional relationship between rows.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The matrix depending on the parameter $t$ is given by:

$$
A(t) =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & t \\
0 & 1 & 1 \\
\end{pmatrix}.
$$

We apply the elementary row operation $R_2 \leftarrow R_2 - 2R_1$ to create zeros in Row 2, and then use the resulting structure to evaluate the determinant.

2. **Intermediate Calculations:**
**Step 1: Perform the operation $R_2 \leftarrow R_2 - 2R_1$**
Adding $(-2)$ times Row 1 to Row 2 leaves the determinant unchanged.
We compute the entries of the new Row 2:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 2 - 2 = 0 \\
r_{22} &= 4 - 2(2) = 4 - 4 = 0 \\
r_{23} &= t - 2(3) = t - 6
\end{aligned}
$$

The transformed matrix is:

$$
B(t) =
\begin{pmatrix}
1 & 2 & 3 \\
0 & 0 & t - 6 \\
0 & 1 & 1 \\
\end{pmatrix}, \qquad \det(A(t)) = \det(B(t)).
$$

**Step 2: Laplace Expansion of $\det B(t)$ along Column 1**
Notice that Column 1 of $B(t)$ has entries $b_{11} = 1$, $b_{21} = 0$, and $b_{31} = 0$.
Expanding along Column 1:

$$
\det B(t) = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 0 & t - 6 \\ 1 & 1 \\ \end{pmatrix} - 0 \cdot C_{21} + 0 \cdot C_{31}
$$

Evaluating the $2 \times 2$ determinant:

$$
\det\begin{pmatrix} 0 & t - 6 \\ 1 & 1 \\ \end{pmatrix} = (0)(1) - (t - 6)(1) = 0 - (t - 6) = 6 - t
$$

Therefore:

$$
\det A(t) = \det B(t) = 6 - t
$$

3. **Arithmetic Evaluation & Row Dependence Analysis:**
Setting the determinant equal to zero to determine when the matrix is not invertible:

$$
6 - t = 0 \iff t = 6
$$

**Explanation of What Happens to the Rows for $t = 6$:**
Substituting $t = 6$ into the original matrix gives:

$$
A(6) =
\begin{pmatrix}
1 & 2 & 3 \\
2 & 4 & 6 \\
0 & 1 & 1 \\
\end{pmatrix}.
$$

We examine Row 1 and Row 2:
- Row 1: $R_1 = \begin{pmatrix} 1 & 2 & 3 \end{pmatrix}$
- Row 2: $R_2 = \begin{pmatrix} 2 & 4 & 6 \end{pmatrix}$

Notice that:

$$
R_2 = 2 \cdot R_1
$$

Thus, for $t = 6$, Row 2 is an exact scalar multiple of Row 1.
When we apply the row operation $R_2 \leftarrow R_2 - 2R_1$, the second row becomes entirely zero:

$$
R_2 - 2R_1 = \begin{pmatrix} 0 & 0 & 0 \end{pmatrix}
$$

Because the rows $\{R_1, R_2, R_3\}$ are linearly dependent, the matrix has rank at most $2 < 3$, which confirms that $A(6)$ is singular and non-invertible.

## Final Answer

$$
\det(A(t)) = 6 - t
$$

The matrix $A(t)$ is not invertible when $t = 6$.
