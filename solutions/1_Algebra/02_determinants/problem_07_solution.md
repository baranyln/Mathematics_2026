# Problem 07 Solution

## Problem Statement
Suppose that for a $3\times3$ matrix, $\det A=-4$. Compute

$$
\det(2A),\qquad \det(A^T),\qquad \det(A^2),\qquad \det(-A).
$$

Justify each answer using the appropriate property.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Determinant Properties:
  - Scalar Multiplication: For an $n \times n$ matrix $A$ and scalar $c$, $\det(cA) = c^n \det(A)$.
  - Transposition: The determinant of the transpose equals the determinant of the original matrix, $\det(A^T) = \det(A)$.
  - Power / Product Rule: The determinant of a product is the product of determinants, $\det(AB) = \det(A)\det(B)$, which implies $\det(A^k) = (\det A)^k$.
  - Matrix Negation: Since $-A = (-1)A$, the scalar rule gives $\det(-A) = (-1)^n \det(A)$.
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **Method Selection & Matrix Setup:**
We are given an $n \times n$ matrix with dimension $n = 3$, and its determinant:

$$
\det A = -4.
$$

We apply fundamental determinant algebraic properties for $3 \times 3$ matrices to evaluate each requested determinant without needing the explicit entries of $A$.

2. **Intermediate Calculations:**
- **Evaluation of $\det(2A)$:**
Multiplying a matrix by a scalar $c$ scales each of its $n$ rows by $c$. By multilinearity of the determinant:

$$
\det(cA) = c^n \det(A)
$$

With $c = 2$ and $n = 3$:

$$
\det(2A) = 2^3 \det(A)
$$

- **Evaluation of $\det(A^T)$:**
Transposition interchanges rows and columns without changing the permutation structure in the Leibniz expansion of the determinant:

$$
\det(A^T) = \det(A)
$$

- **Evaluation of $\det(A^2)$:**
By the multiplicative property of determinants, $\det(MN) = \det(M)\det(N)$. For $M = N = A$:

$$
\det(A^2) = \det(A \cdot A) = \det(A) \cdot \det(A) = (\det A)^2
$$

- **Evaluation of $\det(-A)$:**
Negation corresponds to scalar multiplication with $c = -1$:

$$
\det(-A) = (-1)^n \det(A)
$$

With $n = 3$:

$$
\det(-A) = (-1)^3 \det(A)
$$

3. **Arithmetic Evaluation:**
We compute each value:

$$
\begin{aligned}
\det(2A) &= 2^3 \cdot (-4) = 8 \cdot (-4) = -32 \\
\det(A^T) &= -4 \\
\det(A^2) &= (-4)^2 = 16 \\
\det(-A) &= (-1)^3 \cdot (-4) = (-1) \cdot (-4) = 4
\end{aligned}
$$

## Final Answer

$$
\det(2A) = -32, \qquad \det(A^T) = -4, \qquad \det(A^2) = 16, \qquad \det(-A) = 4
$$
