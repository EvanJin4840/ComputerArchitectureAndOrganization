## Common type of Registers
- Data Registers: Hold numeric data, such as integers, that the CPU is currently processing.
- Address Registers: Store memory addresses to keep track of where data is located in RAM. This is like remembering which shelf in the pantry an ingredient is on.
- Instruction Register (IR): Holds the current instruction that the CPU is executing.
- Program Counter (PC): Holds the memory address of the next instruction to be fetched and executed. It's like a bookmark telling the CPU what to do next.
- Accumulator: A special register that often stores the result of the last calculation made by the arithmetic logic unit (ALU).

### How Much Data Can Be Stored in a MIPS Register?
- A single MIPS register stores 32 bits of data.
- This 32-bit chunk of data is also called a word.
* A 32-bit pattern can be interpreted in several ways, including:
- An Unsigned Integer: A number from 0 to 2^32 − 1 (which is 4,294,967,295).
- A Signed Integer: A number from −2^31 to 2^31 − 1 (from approx. -2.1 billion to +2.1 billion).
- A Memory Address: It can point to one of 2^32
  unique byte locations in memory, which allows the CPU to access up to 4GB of RAM.
- A Floating-Point Number: A number with a fractional part (though this is typically handled by separate floating-point registers).

#### & zero Register
- In the MIPS architecture, $zero (also written as $0) is a special-purpose register that is hardwired to always contain the value 0.
+ key features
2. Read-Only: You can read the value 0 from it at any time, but you cannot write a different value into it. Any instruction that attempts to modify $zero will have no effect; its value will remain 0.
1. Real Hardware: It's not just a programming convenience or a placeholder; it is a physical register implemented in the CPU hardware.
- common use
1. Comparing with Zero: It provides an easy way to check if a value is zero, positive, or negative.
2. Creating Pseudo-instructions: The assembler uses $zero to create simple, intuitive instructions that don't exist in the actual hardware instruction set. Such as Loading an Immediate Value and Register-to-Register Move.
- In the MIPS architecture, there is only one $zero register.

### Basic blocks
- A basic block is a sequence of instructions with no embedded branches (except at end), no branch target (except for beginning)
- A compiler identifies basic blocks for optimization
- An advanced processor can accelerate execution of basic blocks

## Instruction Representation

##### R-format (Register)
Purpose: For operations that only use registers.
Examples: add, sub, and, slt
Structure: op | rs | rt | rd | shamt | funct
Key Idea: All data comes from registers (rs, rt), and the result goes to a register (rd). The funct code specifies the exact operation.

##### I-format (Immediate)
Purpose: For operations involving a constant value, a memory address offset, or a branch target.
Examples: addi, lw, sw, beq
Structure: op | rs | rt | constant or address
Key Idea: It combines a register (rs) with a 16-bit immediate value. This value can be a number to add, an offset for memory, or a branch distance.

##### J-format (Jump)
Purpose: Exclusively for unconditional jumps to a far-away address.
Examples: j, jal
Structure: op | address
Key Idea: It dedicates a large 26-bit field to the target address, allowing the program to jump to almost anywhere in the code.