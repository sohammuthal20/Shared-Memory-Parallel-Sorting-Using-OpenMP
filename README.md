Here’s a `README.md` file for your **Shared Memory Parallel Sorting Using OpenMP** project:

---

# Shared Memory Parallel Sorting Using OpenMP

This project demonstrates how to implement **parallel sorting** (using algorithms like **Merge Sort**) with **OpenMP** for shared memory parallelism in **C**. The sorting algorithm divides an array into smaller parts, sorts them concurrently using multiple threads, and merges the sorted results.

## Objective

- Implement a **parallel sorting algorithm** (e.g., Merge Sort) using OpenMP.
- Utilize **multi-threading** with OpenMP to split the array into smaller subarrays, sort them in parallel, and merge the results after sorting.
  
## Key Concepts

1. **OpenMP for Multi-threaded Execution**: OpenMP is used to parallelize the sorting algorithm, taking advantage of multi-core processors.
2. **Task Parallelism**: Sorting tasks are divided among different threads using OpenMP tasks.
3. **Merging Results**: After sorting subarrays, the results are combined to form the final sorted array.

## Prerequisites

- **OpenMP**: Ensure your compiler supports OpenMP (e.g., GCC).
- **GCC Compiler**: Install GCC if you don't have it installed. On Ubuntu, you can use the following command:
  ```bash
  sudo apt-get install gcc
  ```

## Setup

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/yourusername/shared-memory-parallel-sorting-openmp.git
   cd shared-memory-parallel-sorting-openmp
   ```

2. **Create the C File**:
   - In the project directory, create a C file named `parallel_sort.c` and add the code for parallel merge sort using OpenMP.

3. **Write the Code**:
   - Implement the parallel sorting algorithm, leveraging OpenMP tasks for sorting parts of the array in parallel. You can use the sample code provided in this repository.

4. **Compile the Code**:
   - Use the `gcc` compiler with OpenMP support to compile the program:
   ```bash
   gcc -fopenmp -o parallel_sort parallel_sort.c
   ```

5. **Run the Program**:
   - Execute the compiled program:
   ```bash
   ./parallel_sort
   ```

## Explanation

1. **Merge Sort Algorithm**:
   - The array is divided into two halves recursively.
   - Each half is sorted in parallel using OpenMP tasks, and then the sorted halves are merged.
   
2. **OpenMP Parallel Tasks**:
   - **Task Parallelism** is applied to sort subarrays concurrently using `#pragma omp task`.
   - Synchronization between tasks is ensured using `#pragma omp taskwait` to guarantee merging happens only after both halves are sorted.

3. **Time Measurement**:
   - The program measures the execution time using OpenMP's `omp_get_wtime()` to demonstrate the performance improvement from parallelism.
