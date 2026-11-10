# Problem 14 Solution

## Problem Statement
Compare the systems

$$
\begin{cases}
x+y=2, \\
2x-y=1, \\
3x=3
\end{cases}
$$

and

$$
\begin{cases}
x+y=2, \\
2x-y=1, \\
3x=3.1.
\end{cases}
$$

Check the consistency of each system and explain why a small change in one number can change the type of the system.

## Applied Hint (`hints.md`)
Following the repository guidelines in `hints.md`:
- Overdetermined Systems: A system with more equations than unknowns ($m > n$) is consistent if and only if all surplus equations pass through the solution set determined by the independent equations.
- Inconsistency from Perturbations: In an overdetermined system with a unique candidate solution, perturbing any constant term away from its exact consistency value creates an immediate contradiction ($0 = \epsilon \neq 0$).
- Formatting Standards: Adhere strictly to Section 3 (display mathematics separated by empty lines with `$$` on its own line), Section 4 (`pmatrix` environment for matrices with every row on its own line ending in `\\`), Section 5 (`cases` environment with rows on separate lines ending in `\\`), Section 6 (`aligned` environment for multiline derivations), and Section 7 (avoiding `\text`, using `\mathrm` or plain Markdown prose).

## Detailed Step-by-Step Solution
1. **System Setup & Matrix Formulation:**
Both systems consist of $m = 3$ equations in $n = 2$ unknowns ($x, y$).

We formulate the augmented matrix for **System 1**:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
2 & -1 & \mid & 1 \\
3 & 0 & \mid & 3 \\
\end{pmatrix}.
$$

We formulate the augmented matrix for **System 2**:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
2 & -1 & \mid & 1 \\
3 & 0 & \mid & 3.1 \\
\end{pmatrix}.
$$

2. **Intermediate Steps:**
**Gaussian Elimination on System 1:**
- Eliminate entry $(2,1)$ via $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 0 \\
r_{22} &= -1 - 2(1) = -3 \\
r_{23} &= 1 - 2(2) = -3
\end{aligned}
$$

- Eliminate entry $(3,1)$ via $R_3 \leftarrow R_3 - 3R_1$:

$$
\begin{aligned}
r_{31} &= 3 - 3(1) = 0 \\
r_{32} &= 0 - 3(1) = -3 \\
r_{33} &= 3 - 3(2) = -3
\end{aligned}
$$

The matrix becomes:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & -3 & \mid & -3 \\
0 & -3 & \mid & -3 \\
\end{pmatrix}.
$$

- Scale Row 2 via $R_2 \leftarrow -\frac{1}{3} R_2$:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 1 & \mid & 1 \\
0 & -3 & \mid & -3 \\
\end{pmatrix}.
$$

- Eliminate entry $(3,2)$ via $R_3 \leftarrow R_3 + 3R_2$:

$$
\begin{aligned}
r_{31} &= 0 + 3(0) = 0 \\
r_{32} &= -3 + 3(1) = 0 \\
r_{33} &= -3 + 3(1) = 0
\end{aligned}
$$

The augmented matrix for System 1 in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 1 & \mid & 1 \\
0 & 0 & \mid & 0 \\
\end{pmatrix}.
$$

**Gaussian Elimination on System 2:**
- Eliminate entry $(2,1)$ via $R_2 \leftarrow R_2 - 2R_1$:

$$
\begin{aligned}
r_{21} &= 2 - 2(1) = 0 \\
r_{22} &= -1 - 2(1) = -3 \\
r_{23} &= 1 - 2(2) = -3
\end{aligned}
$$

- Eliminate entry $(3,1)$ via $R_3 \leftarrow R_3 - 3R_1$:

$$
\begin{aligned}
r_{31} &= 3 - 3(1) = 0 \\
r_{32} &= 0 - 3(1) = -3 \\
r_{33} &= 3.1 - 3(2) = 3.1 - 6 = -2.9
\end{aligned}
$$

The matrix becomes:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & -3 & \mid & -3 \\
0 & -3 & \mid & -2.9 \\
\end{pmatrix}.
$$

- Scale Row 2 via $R_2 \leftarrow -\frac{1}{3} R_2$:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 1 & \mid & 1 \\
0 & -3 & \mid & -2.9 \\
\end{pmatrix}.
$$

- Eliminate entry $(3,2)$ via $R_3 \leftarrow R_3 + 3R_2$:

$$
\begin{aligned}
r_{31} &= 0 + 3(0) = 0 \\
r_{32} &= -3 + 3(1) = 0 \\
r_{33} &= -2.9 + 3(1) = -2.9 + 3 = 0.1
\end{aligned}
$$

The augmented matrix for System 2 in row echelon form is:

$$
\begin{pmatrix}
1 & 1 & \mid & 2 \\
0 & 1 & \mid & 1 \\
0 & 0 & \mid & 0.1 \\
\end{pmatrix}.
$$

3. **Variable Evaluation & Explanation:**
**Consistency of System 1:**
- In System 1, the third row is entirely zero ($0 = 0$).
- Rank comparison:

$$
\mathrm{rank}(A) = 2, \qquad \mathrm{rank}([A \mid b_1]) = 2.
$$

- Since the rank equals the number of unknowns ($n = 2$), System 1 is **consistent and has exactly one unique solution**:
  - From Row 2: $y = 1$.
  - From Row 1: $x + y = 2 \implies x + 1 = 2 \implies x = 1$.
  - Solution: $(x, y) = (1, 1)$.

**Consistency of System 2:**
- In System 2, Row 3 yields:

$$
0x + 0y = 0.1 \implies 0 = 0.1.
$$

- Rank comparison:

$$
\mathrm{rank}(A) = 2, \qquad \mathrm{rank}([A \mid b_2]) = 3.
$$

- Since $\mathrm{rank}(A) < \mathrm{rank}([A \mid b_2])$, System 2 is **inconsistent and has no solution**.

**Explanation of Why a Small Change Alters the System Type:**
In $\mathbb{R}^2$, the first two equations represent two intersecting straight lines:
- Line 1: $x + y = 2 \implies y = 2 - x$
- Line 2: $2x - y = 1 \implies y = 2x - 1$

Setting $2 - x = 2x - 1$ gives $3x = 3 \implies x = 1$, and $y = 1$.
Thus, the first two lines intersect at the single point $(1, 1)$.
The third equation $3x = c \iff x = \frac{c}{3}$ represents a vertical line.
- In System 1, $c = 3$, so the vertical line is $x = 1$. This vertical line passes directly through the intersection point $(1, 1)$. All three lines are concurrent (they intersect at one common point), so the system has a solution.
- In System 2, $c = 3.1$, so the vertical line is $x = \frac{3.1}{3} \approx 1.0333$. This line misses the intersection point $(1, 1)$ by a distance of approximately $0.0333$.
Because an overdetermined system requires all constraints to meet at the identical point, shifting one line even slightly causes the lines to form a triangular region without any common intersection point, abruptly turning the system from consistent to inconsistent.

## Final Answer

- **System 1:** Consistent with exactly one unique solution:

$$
x = 1, \quad y = 1
$$

- **System 2:** Inconsistent with **no solution** (due to the contradiction $0 = 0.1$).

A small change from $3$ to $3.1$ moves the third line off the unique intersection point $(1, 1)$ of the first two lines, destroying concurrence and rendering the system inconsistent.
