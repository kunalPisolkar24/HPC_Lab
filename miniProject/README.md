# MPI Parallel Quicksort

This project, part of the `HPC_Lab/miniProject` repository, implements a parallel version of the Quicksort algorithm using the Message Passing Interface (MPI). It evaluates its performance against a sequential Quicksort and calculates the speedup.

## Overview

The program sorts a large array of random integers using both a standard sequential Quicksort and a parallel MPI-based Quicksort. It measures and compares the execution times to demonstrate the benefits of parallel processing for this sorting algorithm.

## Algorithm Strategy (Parallel Quicksort)

1.  **Initialization**: MPI environment setup. Rank 0 generates random data.
2.  **Sequential Baseline**: Rank 0 performs a sequential Quicksort and times it.
3.  **Data Distribution**: The array is scattered from rank 0 to all MPI processes (`MPI_Scatterv`).
4.  **Local Sort**: Each process sorts its local data segment (`std::sort`).
5.  **Pivot Selection**:
    *   Processes select local samples.
    *   Samples are gathered on rank 0.
    *   Rank 0 determines global pivots from sorted samples.
6.  **Broadcast Pivots**: Pivots are broadcast to all processes (`MPI_Bcast`).
7.  **Data Partitioning**: Each process partitions its local data based on global pivots, determining where each element should be sent.
8.  **All-to-All Exchange**: Processes exchange data counts (`MPI_Alltoall`) and then the actual data elements (`MPI_Alltoallv`) so each process receives elements within its assigned pivot range.
9.  **Final Local Sort**: Each process sorts its newly received data.
10. **Gather Results**: Sorted segments are gathered on rank 0 (`MPI_Gatherv`) to form the final sorted array.
11. **Verification & Timing**: Rank 0 verifies the sorted array and calculates parallel execution time and speedup.

## Code Structure

*   **Languages/Libraries**: C++11, MPI.
*   **Key MPI Functions Used**: `MPI_Scatterv`, `MPI_Gather`, `MPI_Bcast`, `MPI_Alltoall`, `MPI_Alltoallv`, `MPI_Gatherv`, `MPI_Barrier`, `MPI_Wtime`.
*   **Sequential Sort**: Standard recursive Quicksort implementation.
*   **Verification**: `is_sorted()` function to check correctness.

## Prerequisites

*   C++11 (or newer) compiler (e.g., GCC, Clang).
*   MPI implementation (e.g., Open MPI, MPICH).

## Compilation

Use an MPI C++ compiler wrapper:

```bash
mpic++ parallel_quicksort.cpp -o parallel_quicksort -std=c++11 -O3
```

## Execution

Run the compiled program using `mpirun`:

```bash
mpirun -np <num_processes> [--oversubscribe] [--allow-run-as-root] ./parallel_quicksort <array_size_N>
```

*   `<num_processes>`: Number of MPI processes (e.g., 8).
*   `<array_size_N>`: (Optional) Total elements in the array. Defaults to 1,000,000.
*   `--oversubscribe`: (Optional) Allows running more processes than available cores (useful for testing on a single machine).
*   `--allow-run-as-root`: (Optional, generally not recommended for production) Allows running as the root user if necessary.

**Example (as provided):**

```bash
mpirun -np 8 --oversubscribe --allow-run-as-root ./parallel_quicksort 2000000
```

## Output

The program outputs:
*   Array size and number of MPI processes used.
*   Sequential Quicksort execution time.
*   Parallel MPI Quicksort execution time.
*   Verification status of the parallel sort.
*   Calculated speedup (Sequential Time / Parallel Time).

A warning may appear if the final size of the sorted data in the parallel version doesn't match the input size `N`.

```bash
----------------------------------------
MPI Quicksort Performance Evaluation (Kaggle Node)
Array Size (N): 2000000
MPI Processes Requested: 8
----------------------------------------
Sequential Time: 0.53989 s
Parallel Time:   0.238298 s
Parallel sort Verified.
----------------------------------------
Speedup:         2.26561x
----------------------------------------
```