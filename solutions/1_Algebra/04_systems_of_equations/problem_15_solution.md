# Problem 15 Solution

## Problem Statement
For each of the following systems, perform only as much elimination as necessary to recognize its type:

**System 1**

$$
\begin{cases}
x+y=2, \\
x-y=0,
\end{cases}
$$

**System 2**

$$
\begin{cases}
x+y=2, \\
2x+2y=4,
\end{cases}
$$

**System 3**

$$
\begin{cases}
x+y=2, \\
2x+2y=5.
\end{cases}
$$

For each, justify the classification: one solution, infinitely many solutions, or no solution.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Structural Classification of Linear Systems (Rouché-Capelli Theorem):
  - **One Solution:** $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = n$ (every column has a pivot, no free variables).
  - **Infinitely Many Solutions:** $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) < n$ (consistent, with at least one free variable).
  - **No Solution:** $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$ (a row of the form $\begin{pmatrix} 0 & 0 & \dots & 0 & \mid & c \end{pmatrix}$ with $c \neq 0$, producing a contradiction).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
We formulate the augmented matrix $[A \mid b]$ for each of the three systems:

- **System 1:**

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
1 & -1 & \mid & 0 \\
\end{pmatrix}.
$$

- **System 2:**

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
2 & 2 & \mid & 4 \\
\end{pmatrix}.
$$

- **System 3:**

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
2 & 2 & \mid & 5 \\
\end{pmatrix}.
$$

In each system, the number of unknowns is $n = 2$.

2. **Intermediate Steps:**
We perform minimal elimination on each augmented matrix:

**Elimination for System 1:**
We eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - R_1$:

$$
\begin{aligned}
r_{21} &= 1 - 1 = 0 \\
r_{22} &= -1 - 1 = -2 \\
r_{23} &= 0 - 2 = -2
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & -2 & \mid & -2 \\
\end{pmatrix}.
$$

**Elimination for System 2:**
We eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 0 \\
r_{22} &= 2 - 2(1) = 0 \\
r_{23} &= 4 - 2(2) = 0
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Elimination for System 3:**
We eliminate entry $(2,1)$ using operation $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 0 \\
r_{22} &= 2 - 2(1) = 0 \\
r_{23} &= 5 - 2(2) = 1
\end{aligned}
$$

The augmented matrix in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 0 & \mid & 1 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Consistency Check:**
**Classification and Justification for System 1:**
- **Rank analysis:** The coefficient matrix has 2 non-zero rows, and the augmented matrix has 2 non-zero rows:

$$
\mathrm{rank}(A) = 2, \qquad \mathrm{rank}([A \mid b]) = 2.
$$

- Since $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = n = 2$, there are no free variables and no contradictions.
- Solving via back-substitution:
  - From Row 2: $-2y = -2 \implies y = 1$.
  - From Row 1: $x + 1 = 2 \implies x = 1$.
- **Classification:** **Exactly one solution** ($(x, y) = (1, 1)$).

**Classification and Justification for System 2:**
- **Rank analysis:** The second row is entirely zero ($0 = 0$).

$$
\mathrm{rank}(A) = 1, \qquad \mathrm{rank}([A \mid b]) = 1.
$$

- Since $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = 1 < n = 2$, the system is consistent, and the number of free variables is $n - r = 2 - 1 = 1$.
- Setting $y = t$ ($t \in \mathbb{R}$):

$$
x = 2 - t, \qquad y = t, \qquad t \in \mathbb{R}.
$$

- **Classification:** **Infinitely many solutions**.

**Classification and Justification for System 3:**
- **Rank analysis:** The second row corresponds to the equation $0x + 0y = 1 \implies 0 = 1$.

$$
\mathrm{rank}(A) = 1, \qquad \mathrm{rank}([A \mid b]) = 2.
$$

- Since $\mathrm{rank}(A) < \mathrm{rank}([A \mid b])$, the contradiction proves that no solution exists.
- **Classification:** **No solution** (inconsistent).

## Final Answer

- **System 1:** **Exactly one solution**

$$
x = 1, \quad y = 1
$$

Justification: $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = 2 = n$.

- **System 2:** **Infinitely many solutions**

$$
\begin{pmatrix}
x \\
y \\
\end{pmatrix} =
\begin{pmatrix}
2 - t \\
t \\
\end{pmatrix}, \qquad t \in \mathbb{R}
$$

Justification: $\mathrm{rank}(A) = \mathrm{rank}([A \mid b]) = 1 < n$.

- **System 3:** **No solution**

Justification: $\mathrm{rank}(A) = 1 < 2 = \mathrm{rank}([A \mid b])$ (produces the contradiction $0 = 1$).
