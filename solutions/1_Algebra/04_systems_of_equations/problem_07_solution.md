# Problem 07 Solution

## Problem Statement
Do not solve all of the following systems completely. For each situation, choose the method that best uses its structure and justify your choice:

1. one system with a triangular coefficient matrix

$$
\begin{cases}
2x-y=3, \\
4y=8;
\end{cases}
$$

2. three systems $Ax=b_i$ with the same invertible matrix $A$, when $A^{-1}$ is already known;
3. one $3\times3$ system for which the inverse matrix is not given and the goal is only to find one solution vector.

For case 1, carry out the chosen method completely. For cases 2 and 3, describe the plan and indicate which part of the computation would be reusable or unnecessary. Do not judge a method by its name alone — refer to the number of right-hand sides and the structure of the matrix.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Structural Method Selection:
  - Triangular Systems: If the matrix is already in triangular form, eliminate all row reduction steps and apply direct back-substitution.
  - Multiple Systems with Fixed $A$ and Known $A^{-1}$: Use matrix-vector multiplication $x_i = A^{-1}b_i$ to reuse the precomputed inverse without re-solving the system.
  - Single System with Unknown Inverse: Use Gaussian elimination directly on $[A \mid b]$, as finding $A^{-1}$ incurs unnecessary computational overhead (requiring $3 \times$ more operations).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We analyze the algebraic structure for each of the three situations:

- **Situation 1:** The system is given by:

$$
\begin{cases}
2x - y = 3, \\
4y = 8.
\end{cases}
$$

In matrix form, the augmented matrix is:

$$
\begin{pmatrix}
2 & -1 & \mid & 3 \\
0 & 4 & \mid & 8 \\
\end{pmatrix}.
$$

The coefficient matrix is already in upper triangular form because the entry below the main diagonal is zero ($a_{21} = 0$).

- **Situation 2:** We have 3 systems $Ax = b_1$, $Ax = b_2$, $Ax = b_3$ sharing the same invertible coefficient matrix $A \in \mathbb{R}^{n \times n}$, and the inverse matrix $A^{-1}$ is already given.

- **Situation 3:** We have a single system $Ax = b$ with $A \in \mathbb{R}^{3 \times 3}$, $A^{-1}$ is not given, and we require only the solution vector for the single vector $b$.

2. **Intermediate Steps:**
**Analysis and Execution for Situation 1:**
- **Chosen Method:** **Direct Back-Substitution**.
- **Justification:** Because the coefficient matrix is already upper triangular, Gaussian elimination is completely redundant. The second equation contains only variable $y$ and is already isolated.
- **Complete Computation:**
  - From Equation 2:

$$
4y = 8 \implies y = \frac{8}{4} = 2.
$$

  - Substitute $y = 2$ into Equation 1:

$$
2x - (2) = 3 \implies 2x = 3 + 2 = 5 \implies x = \frac{5}{2}.
$$

  - Verification: $2\left(\frac{5}{2}\right) - 2 = 5 - 2 = 3$, and $4(2) = 8$. Both hold.

**Analysis and Execution Plan for Situation 2:**
- **Chosen Method:** **Matrix-Vector Multiplication using the Inverse: $x_i = A^{-1}b_i$**.
- **Justification:** Since $A^{-1}$ is precomputed and provided, calculating each solution vector requires only one matrix-vector multiplication:

$$
x_1 = A^{-1}b_1, \qquad x_2 = A^{-1}b_2, \qquad x_3 = A^{-1}b_3.
$$

- **Reusable Part:** The matrix $A^{-1}$ is reused across all three calculations.
- **Unnecessary Computation:** Performing Gaussian elimination on three separate augmented matrices $[A \mid b_1]$, $[A \mid b_2]$, and $[A \mid b_3]$ would needlessly repeat the row reduction of $A$ three times.

**Analysis and Execution Plan for Situation 3:**
- **Chosen Method:** **Gaussian Elimination on the Augmented Matrix $[A \mid b]$**.
- **Justification:** For a single system with one right-hand side, Gaussian elimination requires approximately $\frac{2}{3}n^3$ operations ($\approx 18$ operations for $n = 3$), followed by back-substitution ($\approx 9$ operations). In contrast, computing the full inverse $A^{-1}$ requires solving for 3 separate unit basis vectors (costing $2n^3 \approx 54$ operations), plus an additional matrix-vector product $A^{-1}b$ ($n^2 = 9$ operations).
- **Reusable / Unnecessary Part:** Finding the 9 individual entries of $A^{-1}$ is completely unnecessary because there are no future right-hand sides to reuse it on. Gaussian elimination produces the solution directly with minimum effort.

3. **Variable Evaluation & Consistency Check:**
Summary of decisions:
- Situation 1 yields the exact unique solution: $x = \frac{5}{2}, y = 2$.
- Situation 2 achieves optimal efficiency by computing $x_i = A^{-1}b_i$ for $i \in \{1, 2, 3\}$.
- Situation 3 achieves optimal efficiency by reducing $[A \mid b]$ without finding $A^{-1}$.

## Final Answer

- **Case 1 (Triangular):** Method chosen is Direct Back-Substitution:

$$
x = \frac{5}{2}, \quad y = 2
$$

- **Case 2 (Known $A^{-1}$, multiple $b_i$):** Method chosen is Matrix Multiplication:

$$
x_i = A^{-1}b_i \quad (i = 1, 2, 3)
$$

The matrix $A^{-1}$ is reusable; re-running elimination is unnecessary.

- **Case 3 (Single system, $A^{-1}$ unknown):** Method chosen is Gaussian Elimination on $[A \mid b]$:
Computing $A^{-1}$ is unnecessary overhead for a single right-hand side vector.
