#### The 5 Stages of Pipeline

1. IF (Instruction Fetch)

- Action: Fetches the instruction from memory (specifically I-Cache) using the address in the Program Counter (PC).

2. ID (Instruction Decode / Register Fetch)

- Action: Decodes the instruction to understand what to do and reads the data from the Register File.

3. EX (Execute / Address Calculation)

- Action: The ALU performs the operation.

For arithmetic instructions, it performs the calculation.

For memory instructions, it calculates the effective memory address.

4. MEM (Memory Access)

- Action: Accesses the data memory (specifically D-Cache) to read (Load) or write (Store) data.

- Note: Only Load/Store instructions utilize this stage effectively.

5. WB (Write Back)

Action: Writes the result (from ALU or Memory) back into the Register File.
