### Why convert 16-bit to 32-bit? (English Explanation)

- The MIPS architecture uses 32-bit registers and a 32-bit ALU. However, the immediate offset provided in the instruction is only 16 bits. To add this 16-bit offset to a 32-bit base address, the offset must be extended to 32 bits to match the input size of the ALU.
