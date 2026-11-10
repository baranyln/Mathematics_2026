# Problem 14 Solution

## Problem Statement
Consider the system $Ax=b$, where

$$
A=
\begin{pmatrix}
1 & 2 \\
k & 4 \\
\end{pmatrix}.
$$

For which values of $k$ does the system have exactly one solution for every $b$? For the remaining value, give an example of a right-hand side $b$ for which the system has infinitely many solutions, and an example for which it has no solution.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Linear Systems and Determinants: A linear system $Ax = b$ with a square coefficient matrix $A$ has a unique solution for every vector $b$ if and only if $\det A \neq 0$ (Invertible Matrix Theorem).
- Singular Systems ($k = 2$): When $\det A = 0$, the system is singular and either possesses infinitely many solutions (when the augmented matrix is consistent) or no solution (when the augmented matrix contains an inconsistent row).
- Augmented Matrix Representation: Using `pmatrix` with explicit `\mid` separator and rows on separate lines, following Section 4 of `hints.md`.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We are given the coefficient matrix:

$$
A =
\begin{pmatrix}
1 & 2 \\
k & 4 \\
\end{pmatrix}
$$

for the linear system $Ax = b$, where $x = \begin{pmatrix} x_1 \\ x_2 \\ \end{pmatrix}$ and $b = \begin{pmatrix} b_1 \\ b_2 \\ \end{pmatrix}$.

To find when the system has a unique solution for every $b$, we compute $\det A$ and apply the Invertible Matrix Theorem.

2. **Intermediate Calculations:**
We compute the determinant of matrix $A$:

$$
\det A = (a_{11})(a_{22}) - (a_{12})(a_{21}) = (1)(4) - (2)(k)
$$

$$
\det A = 4 - 2k
$$

**Condition for a Unique Solution:**
The system $Ax = b$ has a unique solution for every $b \in \mathbb{R}^2$ if and only if $A$ is invertible, which requires $\det A \neq 0$:

$$
4 - 2k \neq 0 \iff 2k \neq 4 \iff k \neq 2
$$

Therefore, the system has exactly one solution for every $b$ for all $k \in \mathbb{R} \setminus \{2\}$.

**Analysis of the Singular Case ($k = 2$):**
When $k = 2$, $\det A = 4 - 2(2) = 0$, so the coefficient matrix is:

$$
A =
\begin{pmatrix}
1 & 2 \\
2 & 4 \\
\end{pmatrix}.
$$

The augmented matrix of the system $Ax = b$ is:

$$
\begin{pmatrix}
1 & 2 & \mid & b_1 \\
2 & 4 & \mid & b_2 \\
\end{pmatrix}.
$$

Applying the row operation $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 0 \\
r_{22} &= 4 - 2(2) = 0
\end{aligned}
$$

The augmented entry in Row 2 becomes $b_2 - 2b_1$.
The reduced augmented matrix is:

$$
\begin{pmatrix}
1 & 2 & \mid & b_1 \\
0 & 0 & \mid & b_2 - 2b_1 \\
\end{pmatrix}.
$$

3. **Arithmetic Evaluation & Constructing Examples for $k = 2$:**
- **Example with Infinitely Many Solutions:**
For the system to have solutions when the coefficient row vanishes, the augmented term must also vanish:

$$
b_2 - 2b_1 = 0 \iff b_2 = 2b_1
$$

Choosing $b_1 = 1$, we find $b_2 = 2(1) = 2$.
The right-hand side vector is:

$$
b =
\begin{pmatrix}
1 \\
2 \\
\end{pmatrix}.
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 \\
0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

The second equation is $0x_1 + 0x_2 = 0$, which is satisfied for all values of $x_1, x_2$.
Setting the free variable $x_2 = t$ (where $t \in \mathbb{R}$), the first equation gives:

$$
x_1 = 1 - 2t
$$

Thus, there are infinitely many solutions of the form:

$$
x =
\begin{pmatrix}
1 - 2t \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}.
$$

- **Example with No Solution (Inconsistent System):**
The system has no solution whenever $b_2 - 2b_1 \neq 0$.
Choosing $b_1 = 1$ and $b_2 = 0$:

$$
b =
\begin{pmatrix}
1 \\
0 \\
\end{pmatrix}.
$$

The augmented matrix becomes:

$$
\begin{pmatrix}
1 & 2 & \mid & 1 \\
0 & 0 & \mid & -2 \\
\end{pmatrix}.
$$

The second row represents the equation:

$$
0x_1 + 0x_2 = -2 \implies 0 = -2
$$

This contradiction shows that no solution exists.

## Final Answer

$$
\det(A) = 4 - 2k
$$

The system has exactly one solution for every $b$ if and only if $k \neq 2$. For $k = 2$, the right-hand side $b = \begin{pmatrix} 1 \\ 2 \\ \end{pmatrix}$ yields infinitely many solutions, and $b = \begin{pmatrix} 1 \\ 0 \\ \end{pmatrix}$ yields no solution.
