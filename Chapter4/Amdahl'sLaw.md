1. Key Terms & Variables
- $P$ (Parallel Fraction): The portion of the program that can be parallelized (e.g., 0.9 for 90%).
- $1-P$ (Serial Fraction): The portion that must run sequentially (e.g., 0.1 for 10%). This is the bottleneck.
- $N$ (Number of Processors): The number of CPU cores or threads added to the task.
- $S$ (Speedup): How much faster the program runs compared to a single processor.

2. The FormulaThe overall speedup $S$ is calculated as:
$$S(N) = \frac{1}{(1-P) + \frac{P}{N}}$$