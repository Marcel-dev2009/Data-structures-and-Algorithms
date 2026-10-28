# Data Structures & Algorithms (DSA) in C

A practical repository focused on low-level Data Structures and Algorithms implementations in C. This project emphasizes manual memory management, pointer arithmetic, and cache-friendly matrix operations.

---

## 📂 Repository Architecture

```text
.
├── matrices/
│   ├── memory_layouts.c          # Row-major vs. 1D dynamic allocation
│   ├── matrix_traversals.c       # Boundary scanning, row-wise vs. col-wise iteration
│   ├── transformations.c        # In-place transpositions and rotations
│   └── grid_dp.c                # 2D state-space traversal and dynamic programming
├── graphs/                      # [Upcoming] Adjacency matrices & graph algorithms
└── README.md
```

---

## 🧮 Matrices in C (Core Concepts)

In C, a matrix is represented in memory as contiguous blocks of memory, either allocated on the stack (e.g., `int matrix[M][N]`) or dynamically allocated on the heap.

### 1. Memory Layouts & Pointer Arithmetic
- **Row-Major Order:** C stores multidimensional arrays in row-major order. Contiguous memory locations hold elements of a row sequentially.
- **1D Flat Array Mapping:** For cache efficiency and flexible dimensions on the heap, a 2D matrix of size $M \times N$ can be mapped onto a single 1D pointer (`int *matrix`):
  $$\text{Index}(r, c) = r \times N + c$$
- **Array of Pointers:** Allocated as `int **matrix`, which allows $O(1)$ sub-scripting (`matrix[r][c]`), but may incur cache misses due to fragmented non-contiguous memory allocations.

### 2. Algorithmic Applications
- **Linear Algebra:** Foundations for transformations, system solving, and computer graphics.
- **Graph Representation:** Adjacency matrices ($V \times V$ grid) where cell `[u][v]` indicates an edge between node $u$ and node $v$.
- **Grid-Based Dynamic Programming:** Optimizing paths across state spaces using overlapping subproblems mapped to 2D coordinates.

---

## 🎯 Implementation Roadmap (To Solve)

Use this checklist to track your self-guided C implementation progress:

### Phase 1: Allocations & Basic Traversals
- [ ] Implement contiguous 1D heap allocation (`malloc`/`calloc`) for an $M \times N$ matrix.
- [ ] Write a row-major vs. column-major traversal loop and compare performance.
- [ ] Implement a boundary traversal scanner (Spiral Order) using pointer/index bounds (`top`, `bottom`, `left`, `right`).

### Phase 2: In-Place Transformations
- [ ] Transpose an $N \times N$ square matrix in-place by swapping values across the main diagonal ($[i][j] \leftrightarrow [j][i]$).
- [ ] Rotate an $N \times N$ matrix by $90^\circ$ clockwise using only $O(1)$ extra memory.

### Phase 3: Matrix Algorithms & Graphs
- [ ] Binary search on a row-wise and column-wise sorted 2D grid ($O(M + N)$ time complexity).
- [ ] Graph traversal (BFS/DFS) on an Adjacency Matrix.
- [ ] Grid pathfinding using dynamic programming (e.g., Minimum Path Sum).

---

## ⏱️ Time & Space Complexity Target Reference

| Matrix Pattern / Problem | Target Time Complexity | Target Auxiliary Space | C Implementation Notes |
| :--- | :--- | :--- | :--- |
| **Row/Col Traversal** | $O(M \times N)$ | $O(1)$ | Row-first loops leverage CPU cache prefetching |
| **In-Place Transpose** | $O(N^2)$ | $O(1)$ | Swap elements where $i < j$ |
| **$90^\circ$ Clockwise Rotation** | $O(N^2)$ | $O(1)$ | Combine transpose with row reflection |
| **Sorted Grid Search** | $O(M + N)$ | $O(1)$ | Start scanning from top-right or bottom-left corner |

---

## 🛠️ Compilation & Execution

Build and run your implementation files using `gcc` or `clang` with strict flags enabled:

```bash
# Compile individual C files with wall warnings enabled
gcc -Wall -Wextra -std=c11 matrices/memory_layouts.c -o memory_layouts

# Run binary
./memory_layouts
```