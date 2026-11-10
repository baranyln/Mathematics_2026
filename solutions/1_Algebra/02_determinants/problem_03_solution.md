# Problem 03 Solution

## Problem Statement
For

$$
A=
\begin{pmatrix}
1 & 2 & 0 \\
0 & 3 & 1 \\
2 & 1 & 1 \\
\end{pmatrix}
$$

compute $\det A$. Then form a matrix $B$ by swapping the first and second rows of $A$.

First predict $\det B$ using a determinant property, and then verify your prediction by calculation.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Row Swap Property: Swapping two rows of a square matrix ($R_i \leftrightarrow R_j$) negates its determinant: $\det(B) = -\det(A)$.
- Laplace Expansion: Expanding along a row containing a zero entry isolates non-zero terms efficiently.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
The given matrix has size $3 \times 3$:

$$
A =
\begin{pmatrix}
1 & 2 & 0 \\
0 & 3 & 1 \\
2 & 1 & 1 \\
\end{pmatrix}.
$$

We first compute $\det A$ using Laplace expansion along Row 1, taking advantage of the entry $a_{13} = 0$:

$$
\det A = a_{11} C_{11} + a_{12} C_{12} + a_{13} C_{13}
$$

where $C_{ij} = (-1)^{i+j} M_{ij}$.

2. **Intermediate Calculations:**
We set up the expansion along Row 1 of matrix $A$:

$$
\det A = 1 \cdot (-1)^{1+1} \det\begin{pmatrix} 3 & 1 \\ 1 & 1 \\ \end{pmatrix} + 2 \cdot (-1)^{1+2} \det\begin{pmatrix} 0 & 1 \\ 2 & 1 \\ \end{pmatrix} + 0 \cdot (-1)^{1+3} \det\begin{pmatrix} 0 & 3 \\ 2 & 1 \\ \end{pmatrix}
$$

Evaluating each $2 \times 2$ sub-determinant:

$$
\begin{aligned}
\det\begin{pmatrix} 3 & 1 \\ 1 & 1 \\ \end{pmatrix} &= (3)(1) - (1)(1) = 3 - 1 = 2 \\
\det\begin{pmatrix} 0 & 1 \\ 2 & 1 \\ \end{pmatrix} &= (0)(1) - (1)(2) = 0 - 2 = -2 \\
\det\begin{pmatrix} 0 & 3 \\ 2 & 1 \\ \end{pmatrix} &= (0)(1) - (3)(2) = 0 - 6 = -6
\end{aligned}
$$

Forming matrix $B$ by swapping Row 1 and Row 2 of $A$ ($R_1 \leftrightarrow R_2$):

$$
B =
\begin{pmatrix}
0 & 3 & 1 \\
1 & 2 & 0 \\
2 & 1 & 1 \\
\end{pmatrix}.
$$

**Prediction using Determinant Property:**
Interchanging any two rows of a square matrix multiplies its determinant by $-1$. Therefore:

$$
\det B = -\det A
$$

Setting up direct Laplace expansion along Row 1 of matrix $B$:

$$
\det B = 0 \cdot (-1)^{1+1} \det\begin{pmatrix} 2 & 0 \\ 1 & 1 \\ \end{pmatrix} + 3 \cdot (-1)^{1+2} \det\begin{pmatrix} 1 & 0 \\ 2 & 1 \\ \end{pmatrix} + 1 \cdot (-1)^{1+3} \det\begin{pmatrix} 1 & 2 \\ 2 & 1 \\ \end{pmatrix}
$$

Evaluating the sub-determinants for matrix $B$:

$$
\begin{aligned}
\det\begin{pmatrix} 2 & 0 \\ 1 & 1 \\ \end{pmatrix} &= (2)(1) - (0)(1) = 2 - 0 = 2 \\
\det\begin{pmatrix} 1 & 0 \\ 2 & 1 \\ \end{pmatrix} &= (1)(1) - (0)(2) = 1 - 0 = 1 \\
\det\begin{pmatrix} 1 & 2 \\ 2 & 1 \\ \end{pmatrix} &= (1)(1) - (2)(2) = 1 - 4 = -3
\end{aligned}
$$

3. **Arithmetic Evaluation:**
We evaluate $\det A$:

$$
\begin{aligned}
\det A &= 1 \cdot (+1) \cdot (2) + 2 \cdot (-1) \cdot (-2) + 0 \\
       &= 2 - (-4) \\
       &= 2 + 4 \\
       &= 6
\end{aligned}
$$

Based on the row swap property, the prediction for $\det B$ is:

$$
\det B = -\det A = -6
$$

Now we evaluate $\det B$ directly from its sub-determinants:

$$
\begin{aligned}
\det B &= 0 \cdot (+1) \cdot (2) + 3 \cdot (-1) \cdot (1) + 1 \cdot (+1) \cdot (-3) \\
       &= 0 - 3(1) + 1(-3) \\
       &= -3 - 3 \\
       &= -6
\end{aligned}
$$

The direct calculation yields $-6$, which confirms the prediction $\det B = -\det A = -6$.

## Final Answer

$$
\det(A) = 6, \qquad \det(B) = -6
$$
