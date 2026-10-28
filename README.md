# Data Structures & Algorithms (DSA) in C: Matrix Foundations

A step-by-step learning journey focused on mastering matrices, dynamic input handling, determinant calculations, terminal UIs, and matrix exponentiation in C.

---

## 📂 Repository Structure

```text
.
├── matrices/
│   ├── 01_2x2_basic.c          # Hardcoded 2x2 matrix allocation and traversal
│   ├── 02_2x2_stdin.c          # Dynamic 2x2 input via stdin
│   ├── 03_2x2_determinant.c    # 2x2 Determinant calculation
│   ├── 04_3x3_4x4_basics.c     # 3x3 and 4x4 matrix print loops
│   ├── 05_3x3_4x4_stdin.c      # Dynamic 3x3 and 4x4 input
│   ├── 06_matrix_tui.c         # Interactive Terminal UI for determinants
│   ├── 07_matrix_operations.c # Multi-matrix arithmetic & matrix multiplication
│   └── 08_fibonacci_matrix.c   # N-th Fibonacci via Matrix Exponentiation
├── graphs/ graphs/ [Upcoming] Adjacency matrices & graph algorithms
└── README.md
```

---

## 🎯 Step-by-Step Learning Roadmap

Use this progress checklist to guide your self-implemented solution code in C:

- [ ] **Objective 1: Static $2 \times 2$ Matrix**
  - Allocate a $2 \times 2$ integer array (`int matrix[2][2]`).
  - Use nested `for` loops to print out all entries in standard grid layout.

- [ ] **Objective 2: Interactive $2 \times 2$ Input**
  - Accept $2 \times 2$ matrix elements dynamically from the user via standard input (`scanf`).
  - Print the user's matrix back to the console to verify input.

- [ ] **Objective 3: $2 \times 2$ Determinant**
  - Read $2 \times 2$ entries from `stdin`.
  - Calculate and output the determinant using the formula: 
    $$\det(A) = ad - bc$$

- [ ] **Objective 4: Scaled Sizes ($3 \times 3$ & $4 \times 4$)**
  - Declare hardcoded $3 \times 3$ and $4 \times 4$ matrices.
  - Write modular loops/functions to print all entries cleanly formatted.

- [ ] **Objective 5: Dynamic Input for $3 \times 3$ & $4 \times 4$**
  - Prompt the user to enter entries row-by-row for $3 \times 3$ and $4 \times 4$ grids.
  - Display the populated matrices.

- [ ] **Objective 6: Interactive Terminal UI**
  - Build a CLI menu allowing users to choose matrix dimensions ($2 \times 2$, $3 \times 3$, or $4 \times 4$).
  - Prompt for row/column input based on selection.
  - Calculate and display the determinant (using Laplace expansion or cofactors for higher orders).

- [ ] **Objective 7: Multi-Matrix Operations**
  - Expand the UI to create a secondary matrix.
  - Implement matrix addition, subtraction, and matrix multiplication ($A \times B$).

- [ ] **Objective 8: $N^{\text{th}}$ Fibonacci via Matrix Exponentiation**
  - Implement $O(\log n)$ matrix exponentiation using the transformation matrix:
    $$\begin{pmatrix} 1 & 1 \\ 1 & 0 \end{pmatrix}^n = \begin{pmatrix} F_{n+1} & F_n \\ F_n & F_{n-1} \end{pmatrix}$$
  - Compute the $n^{\text{th}}$ Fibonacci number for large values of $n$.

---

## 🛠️ Compilation & Execution

Build your C programs locally using `gcc` or `clang`:

```bash
# Compile Objective 1
gcc -Wall -Wextra -std=c11 matrices/01_2x2_basic.c -o 01_2x2_basic

# Run binary
./01_2x2_basic
```