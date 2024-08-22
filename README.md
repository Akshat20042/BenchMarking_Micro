Project Report: Matrix Multiplication Benchmarking
1. Introduction
Objective: This project aims to benchmark the performance of matrix multiplication using two different approaches: a standard for loop and OpenMP (Open Multi-Processing) parallelism in C++. The primary goal is to compare execution times for different matrix sizes and demonstrate the benefits of parallel computing using OpenMP.
2. Methodology
Tools & Technologies:

C++: Programming language used for implementing the matrix multiplication algorithms.
OpenMP: A parallel computing model used to speed up the matrix multiplication by utilizing multiple CPU cores.
Google Benchmark: Framework used for microbenchmarking to precisely measure the execution time.
Bazel: Build tool used to compile and run the benchmarking code.
Implementation Details:

Matrix Initialization:
Two square matrices (matrixA and matrixB) are initialized with random integer values between 1 and 10.
A result matrix is initialized to store the multiplication output.
Standard For Loop Multiplication:
The matrices are multiplied using three nested loops, implementing the standard matrix multiplication algorithm.
OpenMP Parallel Multiplication:
The matrix multiplication is parallelized using OpenMP directives to utilize multiple CPU cores. This approach allows different parts of the computation to be executed concurrently, reducing overall execution time.
3. Benchmarking Results
Performance Metrics: Execution time for matrix multiplication was measured for various matrix sizes, ranging from 2x2 to 256x256. The results clearly demonstrate the performance improvements achieved by using OpenMP.

For Loop Results:

2x2 Matrix: 6,525 ns
4x4 Matrix: 7,931 ns
8x8 Matrix: 14,894 ns
16x16 Matrix: 55,369 ns
32x32 Matrix: 344,868 ns
64x64 Matrix: 2,473,194 ns
128x128 Matrix: 18,590,588 ns
256x256 Matrix: 145,733,450 ns
OpenMP Results:

2x2 Matrix: 2,276 ns (2.8x speedup)
4x4 Matrix: 2,348 ns (3.4x speedup)
8x8 Matrix: 3,915 ns (3.8x speedup)
16x16 Matrix: 10,690 ns (5.2x speedup)
32x32 Matrix: 64,650 ns (5.3x speedup)
64x64 Matrix: 395,411 ns (6.3x speedup)
128x128 Matrix: 2,486,479 ns (7.5x speedup)
256x256 Matrix: 19,779,466 ns (7.4x speedup)
4. Analysis
Speedup: The OpenMP implementation consistently outperformed the standard for loop approach, with speedup factors ranging from 2.8x for 2x2 matrices to 7.5x for 128x128 matrices. This clearly demonstrates the efficiency of parallel computing, especially as the matrix size increases.
Scalability: The performance gains from OpenMP become more pronounced with larger matrices. For instance, while the standard approach took over 145 million nanoseconds to compute a 256x256 matrix, the OpenMP version reduced this to under 20 million nanoseconds—a 7.4x improvement.
Efficiency: The results highlight how OpenMP effectively reduces computation time by distributing the workload across multiple CPU cores. This makes it particularly beneficial for large-scale data processing tasks that are common in scientific computing and machine learning applications.
5. Conclusion
Summary: This project successfully demonstrates the significant performance improvements that can be achieved through parallel computing using OpenMP. By benchmarking matrix multiplication across various sizes, the results clearly show that OpenMP offers substantial speedup over traditional methods, particularly as the problem size increases.

Why OpenMP?: OpenMP is an ideal solution for optimizing computationally intensive tasks due to its ability to scale performance with the number of available CPU cores. This makes it an essential tool for developers working with large datasets or complex algorithms.

Future Work: Future experiments could explore other parallel computing models like MPI (Message Passing Interface) or GPU-based solutions to further improve performance and scalability for even larger matrix sizes.
