# 🧩 Rubik’s Cube Solver Project

A comprehensive C++ Rubik’s Cube solving framework featuring multiple cube representations, advanced solving algorithms (DFS, BFS, IDDFS, and Korf’s IDA*), and pattern database heuristics. This project showcases the practical application of object-oriented programming (OOP), templates, inheritance, operator overloading, and bit-level optimizations.

---

## Features

### 🧱 Cube Representations

- **3D Array**: `cube[face][row][col]` – intuitive representation for easy visualization.
- **1D Array**: Linearized array of 54 colors – simple and memory-efficient.
- **Bitboard**: 6 × 64-bit integers, each encoding a face using 8-bit per sticker for compact storage and fast operations.

### 🧠 Solvers Implemented

- **DFS (Depth-First Search)** – Recursive solver with a maximum depth limit.
- **BFS (Breadth-First Search)** – Level-order solver that guarantees the shortest solution.
- **IDDFS (Iterative Deepening DFS)** – Combines the advantages of DFS and BFS through iterative depth expansion.
- **IDA\*** – Korf’s optimal Rubik’s Cube solver powered by pattern database heuristics.

### 📦 Pattern Database Support

- **Corner Pattern Database**:
  - 8! × 3⁷ = 88,179,840 total corner configurations.
  - Stored using a **Nibble Array** (4-bit heuristic value per state).
  - Indexed through a **Permutation Indexer** for efficient state lookup.

---

## 🔧 OOP & C++ Concepts Used

- **Abstract Base Class**: `RubiksCube` with pure virtual functions for:
  - All 18 cube moves (F, F’, F2, …)
  - `print()`, `randomShuffle()`, `isSolved()`
- **Derived Classes**: Implement different cube representations (1D, 3D, and Bitboard).
- **Operator Overloading**:
  - `==` for equality comparison.
  - `=` for deep copy to avoid shallow copy issues.
- **Virtual Functions**: Enable polymorphic cube manipulation.
- **Templates**: Allow generic solvers to work with any cube representation.
- **Inheritance**:
  - Solvers and pattern database classes extend generic base classes.
  - Pattern database implementations inherit from a common abstract base.

---

## 🧠 Cube Model Overview

### ✅ Supported Moves

```text
F, F', F2, U, U', U2, L, L', L2, D, D', D2, R, R', R2, B, B', B2
````
