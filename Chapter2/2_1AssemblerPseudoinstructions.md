## Common type of Registers
- Data Registers: Hold numeric data, such as integers, that the CPU is currently processing.
- Address Registers: Store memory addresses to keep track of where data is located in RAM. This is like remembering which shelf in the pantry an ingredient is on.
- Instruction Register (IR): Holds the current instruction that the CPU is executing.
- Program Counter (PC): Holds the memory address of the next instruction to be fetched and executed. It's like a bookmark telling the CPU what to do next.
- Accumulator: A special register that often stores the result of the last calculation made by the arithmetic logic unit (ALU).


#### & zero Register
- In the MIPS architecture, $zero (also written as $0) is a special-purpose register that is hardwired to always contain the value 0.
+ key features
2. Read-Only: You can read the value 0 from it at any time, but you cannot write a different value into it. Any instruction that attempts to modify $zero will have no effect; its value will remain 0.
1. Real Hardware: It's not just a programming convenience or a placeholder; it is a physical register implemented in the CPU hardware.
- common use
1. Comparing with Zero: It provides an easy way to check if a value is zero, positive, or negative.
2. Creating Pseudo-instructions: The assembler uses $zero to create simple, intuitive instructions that don't exist in the actual hardware instruction set. Such as Loading an Immediate Value and Register-to-Register Move.
- In the MIPS architecture, there is only one $zero register.