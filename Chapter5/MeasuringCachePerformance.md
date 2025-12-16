#### Simplified model

- Execution time = (execution clock cycles + stall clock cycles) \* cycle time
- Stall cycles = number of instructions _ miss ratio _ miss penalty

* Miss penalty : the time to replace a block in cache with the corresponding block from the Memory + the time to deliever this block(or word) to the processor

* Note that : hit time << miss penalty

- The time to replace a block in cache with the corresponding block from memory consists of the following three processes:
  1. Address Transfer : Time for sending the address
  2. DRAM Access : Time for finding the data(in DRAM)
  3. Data Transfer : Time for sending the found data through the bus

##### Two ways of improving performance

- Decreasing the miss ratio(==increasing the hit ratio)
- Decreasing the miss penalty

### What is a Bus Cycle?

- A Bus Cycle is the time unit (clock cycle) of the system bus that connects the CPU and the Main Memory.
- Key Point: The bus clock is typically much slower than the CPU clock.

* Example: CPU might run at 3 GHz, while the Bus runs at 400 MHz.
* Therefore, the calculations in the slide ($1, 15, 65$, etc.) are based on these slower bus cycles, not CPU cycles.
