### Why convert 16-bit to 32-bit? (English Explanation)

- The MIPS architecture uses 32-bit registers and a 32-bit ALU. However, the immediate offset provided in the instruction is only 16 bits. To add this 16-bit offset to a 32-bit base address, the offset must be extended to 32 bits to match the input size of the ALU.

### What is RTL?

- RTL (Register Transfer Language) is a symbolic notation used in computer architecture to describe the flow of data between registers, memory, and the ALU.

It breaks down high-level machine instructions (like lw, sw, add) into a sequence of simple micro-operations that the hardware performs step-by-step.

Key Notation
<- (Transfer Arrow):

Indicates data movement. The value on the right is copied to the location on the left.

Example: A <- B means "Copy the value of B into A."

R[x] (Register Access):

Represents the value stored inside register x.

Example: R[rs] means "The value inside register rs."

Mem[y] (Memory Access):

Represents the value stored at memory address y.

Example: Mem[PC] means "The instruction located at the address inside the PC."

Example: RTL for sw (Store Word)
To execute the instruction sw rt, rs, imm16, the hardware performs these steps:

Address Calculation: Addr <- R[rs] + SignExt(imm16) (Calculate the memory address by adding the base register and the offset.)

Memory Write: Mem[Addr] <- R[rt] (Copy the value from the source register rt into the calculated memory address.)

- Summary: RTL is the "blueprint" that shows exactly how data moves through the datapath wires during each instruction.
