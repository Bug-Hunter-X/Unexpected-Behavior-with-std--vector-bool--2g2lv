# Unexpected Behavior with std::vector<bool>

This repository demonstrates a potential issue with the `std::vector<bool>` specialization in C++.  The `std::vector<bool>` is specialized to optimize memory usage, but this specialization can lead to unexpected behavior compared to other vector types when accessing elements using the `operator[]`.

## Problem

The typical way of accessing vector elements through `operator[]` can produce surprising results when dealing with `std::vector<bool>`.  The underlying implementation optimizes memory usage, potentially changing how elements are accessed and affecting expected behavior, especially with common vector operations.

## Solution

To avoid the unexpected behavior, the recommended approach is to avoid direct `operator[]` access and utilize methods like `at()` instead. This approach helps to ensure consistent behavior and prevents potential issues related to the specialization of `std::vector<bool>`. This approach is generally safer and more predictable.

## How to reproduce and solve the issue

1. Clone this repository.
2. Compile and run the `bug.cpp` file using a C++ compiler to see the unexpected behavior. 
3. Then, examine `bugSolution.cpp` for a corrected version using `at()` method.