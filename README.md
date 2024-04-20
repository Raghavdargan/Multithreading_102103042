# Multithreading_102103042
Submitted by: ***Raghav Dargan*** 
Roll No: ***102103042***
Group: ***3COE2***
## Description
Multiply 100 random matrices of size 1k x 1k with a constant matrix of size 1k x 1k and generate the result table and graph. 
## Methodology
#### Import Packages
`numpy` for numerical operations 
`pandas` for data manipulation
`multiprocessing` for parallel processing
`os` for operating system functionality
`threading` for multi-threading
`time` for time-related functions
`matplotlib.pyplot` for plotting

#### Determine Number of Cores
 `numOfCores=mp.cpu_count()` determines the number of CPU cores available on the system and prints it.

#### Generate Random Matrices and Constant Matrix
Random matrices are generated using `np.random.rand(rows,cols)` in a loop (`numMat=200` times) and stored in the list `matrices`. Constant matrix `constMat` is generated of the same dimensions.

#### Define Matrix Multiplication Function
`matMul(matrices, constMat)` function performs matrix multiplication for each matrix in `matrices` with a constant matrix `constMat`.

#### Define Task Function for Multi-threading
`task(numThread, matrices, conMat)` function is defined to perform matrix multiplication using multiple threads. It calculates the execution time for the task.

#### Multi-threading Execution
The code then iterates through a loop to test different numbers of threads (`num_threads` from 1 to 13). For each number of threads, it calls the `task` function to perform matrix multiplication using multi-threading. The execution time for each configuration is recorded in a dictionary `d`.

#### Create DataFrame from Results
A pandas DataFrame `df` is created from the dictionary `d`. The DataFrame includes columns for "Threads" and "Time Taken (s)".

#### Plotting
The DataFrame is plotted using `df.plot()` to visualize the relationship between the number of threads and the time taken for matrix multiplication. Labels and titles are added to the plot for clarity (`plt.xlabel`, `plt.ylabel`, `plt.title`). Finally, `plt.show()` displays the plot.
