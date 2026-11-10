# Problem 04 Solution

## Problem Statement
Without expanding the determinant, compute

$$
\det
\begin{pmatrix}
2 & 4 & 1 \\
0 & -3 & 5 \\
0 & 0 & 7 \\
\end{pmatrix}.
$$

State the rule for an arbitrary triangular matrix and explain it using this example.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Determinant of a Triangular Matrix: The determinant of an upper triangular, lower triangular, or diagonal matrix is equal to the product of its diagonal elements: $\det T = \prod_{i=1}^n t_{ii}$.
- Structural Explanation via Laplace Expansion: Expanding along the first column shows that all off-diagonal products vanish, reducing the determinant to the product of diagonal entries.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
Let the given matrix be denoted by $A$:

$$
A =
\begin{pmatrix}
2 & 4 & 1 \\
0 & -3 & 5 \\
0 & 0 & 7 \\
\end{pmatrix}.
$$

A square matrix is called **upper triangular** when all entries strictly below the main diagonal are zero ($a_{ij} = 0$ for all $i > j$). Here, $a_{21} = 0$, $a_{31} = 0$, and $a_{32} = 0$. Hence, matrix $A$ is an upper triangular matrix.

**Rule for an Arbitrary Triangular Matrix:**
For any $n \times n$ triangular matrix $T = (t_{ij})$ (whether upper triangular, lower triangular, or diagonal), its determinant is the product of all entries on its main diagonal:

$$
\det T = \prod_{i=1}^n t_{ii} = t_{11} \cdot t_{22} \cdots t_{nn}
$$

2. **Intermediate Calculations:**
We identify the main diagonal entries of matrix $A$:
- First diagonal entry: $a_{11} = 2$
- Second diagonal entry: $a_{22} = -3$
- Third diagonal entry: $a_{33} = 7$

Setting up the direct product of diagonal entries:

$$
\det A = a_{11} \cdot a_{22} \cdot a_{33} = (2) \cdot (-3) \cdot (7)
$$

**Explanation Using Laplace Expansion on this Example:**
To explain why this rule holds, we perform Laplace cofactor expansion along the first column of $A$:

$$
\det A = a_{11} C_{11} + a_{21} C_{21} + a_{31} C_{31}
$$

Since $a_{21} = 0$ and $a_{31} = 0$:

$$
\det A = 2 \cdot (-1)^{1+1} \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \\ \end{pmatrix} - 0 \cdot C_{21} + 0 \cdot C_{31} = 2 \cdot \det\begin{pmatrix} -3 & 5 \\ 0 & 7 \\ \end{pmatrix}
$$

The resulting $2 \times 2$ matrix is also upper triangular. Expanding it along its first column:

$$
\det\begin{pmatrix} -3 & 5 \\ 0 & 7 \\ \end{pmatrix} = (-3)(7) - (5)(0) = (-3)(7) - 0 = (-3)(7)
$$

Substituting this back gives:

$$
\det A = 2 \cdot [(-3) \cdot 7] = (2) \cdot (-3) \cdot (7)
$$

Because all entries below the diagonal in each column are zero, every expansion step isolates the diagonal entry multiplied by the determinant of the smaller triangular block, leaving only the product of all main diagonal elements.

3. **Arithmetic Evaluation:**
We compute the arithmetic product of the diagonal elements:

$$
\begin{aligned}
(2) \cdot (-3) &= -6 \\
(-6) \cdot 7 &= -42
\end{aligned}
$$

Thus:

$$
\det A = -42
$$

## Final Answer

$$
\det(A) = -42
$$
