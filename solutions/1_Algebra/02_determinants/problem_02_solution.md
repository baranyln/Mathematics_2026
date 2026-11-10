# Problem 02 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
2 & 1 & 5 \\
\end{pmatrix}
$$

compute $\det A$ using Sarrus' rule. Then perform one simple check using a chosen property of the determinant.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Sarrus' Rule: For a $3 \times 3$ matrix, the determinant equals the sum of the products of the three downward diagonals minus the sum of the products of the three upward diagonals.
- Determinant Checking Property: Laplace cofactor expansion along Column 1 (which contains entry $a_{21} = 0$) provides an efficient verification method.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The given matrix has dimension $3 \times 3$:

$$
A =
\begin{pmatrix}
1 & 2 & -1 \\
0 & 3 & 4 \\
2 & 1 & 5 \\
\end{pmatrix}.
$$

We use Sarrus' rule, which repeats the first two columns to the right of the matrix:

$$
\begin{pmatrix}
1 & 2 & -1 & \mid & 1 & 2 \\
0 & 3 & 4 & \mid & 0 & 3 \\
2 & 1 & 5 & \mid & 2 & 1 \\
\end{pmatrix}.
$$

By Sarrus' rule, the determinant is given by:

$$
\det A = (D_1 + D_2 + D_3) - (U_1 + U_2 + U_3)
$$

where $D_1, D_2, D_3$ are the downward diagonal products, and $U_1, U_2, U_3$ are the upward diagonal products.

2. **Intermediate Calculations:**
We write down all six diagonal products explicitly:

Downward diagonal products:
- First downward diagonal: $D_1 = (a_{11})(a_{22})(a_{33}) = (1)(3)(5)$
- Second downward diagonal: $D_2 = (a_{12})(a_{23})(a_{31}) = (2)(4)(2)$
- Third downward diagonal: $D_3 = (a_{13})(a_{21})(a_{32}) = (-1)(0)(1)$

Upward diagonal products:
- First upward diagonal: $U_1 = (a_{31})(a_{22})(a_{13}) = (2)(3)(-1)$
- Second upward diagonal: $U_2 = (a_{32})(a_{23})(a_{11}) = (1)(4)(1)$
- Third upward diagonal: $U_3 = (a_{33})(a_{21})(a_{12}) = (5)(0)(2)$

3. **Arithmetic Evaluation:**
We compute the downward products:

$$
\begin{aligned}
D_1 &= (1)(3)(5) = 15 \\
D_2 &= (2)(4)(2) = 16 \\
D_3 &= (-1)(0)(1) = 0
\end{aligned}
$$

The sum of the downward products is:

$$
D_1 + D_2 + D_3 = 15 + 16 + 0 = 31
$$

We compute the upward products:

$$
\begin{aligned}
U_1 &= (2)(3)(-1) = -6 \\
U_2 &= (1)(4)(1) = 4 \\
U_3 &= (5)(0)(2) = 0
\end{aligned}
$$

The sum of the upward products is:

$$
U_1 + U_2 + U_3 = (-6) + 4 + 0 = -2
$$

Subtracting the upward sum from the downward sum gives:

$$
\begin{aligned}
\det A &= 31 - (-2) \\
       &= 31 + 2 \\
       &= 33
\end{aligned}
$$

**Verification Check via Laplace Expansion along Column 1:**
We expand along Column 1 using the formula $\det A = a_{11}C_{11} + a_{21}C_{21} + a_{31}C_{31}$, where $C_{ij} = (-1)^{i+j} M_{ij}$:

$$
\det A = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 3 & 4 \\ 1 & 5 \\ \end{pmatrix} + 0 \cdot C_{21} + 2 \cdot (-1)^{3+1} \det\begin{pmatrix} 2 & -1 \\ 3 & 4 \\ \end{pmatrix}
$$

Evaluating the sub-determinants:

$$
\det\begin{pmatrix} 3 & 4 \\ 1 & 5 \\ \end{pmatrix} = (3)(5) - (4)(1) = 15 - 4 = 11
$$

$$
\det\begin{pmatrix} 2 & -1 \\ 3 & 4 \\ \end{pmatrix} = (2)(4) - (-1)(3) = 8 - (-3) = 8 + 3 = 11
$$

Evaluating the expansion:

$$
\begin{aligned}
\det A &= 1 \cdot (+1) \cdot (11) + 0 + 2 \cdot (+1) \cdot (11) \\
       &= 11 + 22 \\
       &= 33
\end{aligned}
$$

Both methods yield the exact same value, verifying the result.

## Final Answer

$$
\det(A) = 33
$$
