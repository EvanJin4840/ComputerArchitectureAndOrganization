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

### What is the ALU?

ALU stands for Arithmetic Logic Unit.
It is the actual "calculator" inside the CPU that performs the mathematical work.

- Role: It takes two 32-bit numbers as input and performs an operation on them.
- Operations:Arithmetic: Add, Subtract (used for math and address calculations).Logic: AND, OR (used for bitwise operations).\*

##### Outputs

- Result: The calculated answer (e.g., $3 + 5 = 8$).Zero Flag: A 1-bit signal that says "The result is zero." (Crucial for beq to check if two numbers are equal).
- Analogy: Think of the ALU as a Chef. You give the chef ingredients (data), and the chef cooks them (calculates).2. What is the ALU Control? (The Manager)The ALU Control is a small logic unit that tells the ALU exactly what to do.You might ask, "Doesn't the main Control Unit do that?"Not exactly. The Main Control Unit is too general. It looks at the opcode (the first 6 bits) and says generic things like "This is an R-format instruction."The ALU Control takes that generic command and translates it into the specific electronic signal the ALU needs.

#### Inputs to ALU Control

- ALUOp: A signal from the Main Control Unit (e.g., "Do R-type" or "Do Add for Load").
- Funct Field: The last 6 bits of the instruction (only for R-type instructions). This distinguishes add (100000) from sub (100010).
- Output: A specific 4-bit signal sent to the ALU (e.g., 0010 might mean "Add", 0110 might mean "Subtract").
- Analogy: Think of the ALU Control as the Head Waiter. The Customer (Main Control) says "I want the special (R-format). "The Head Waiter (ALU Control) looks at the specific menu item (Funct code) and yells to the Chef (ALU): "Make the Steak!" or "Make the Pasta!"3. How they work togetherHere is the flow of command:Instruction comes in. Main Control Unit looks at the Opcode. If it's lw or sw, it tells ALU Control: "We need to calculate an address (Add)."If it's beq, it tells ALU Control: "We need to compare (Subtract)."If it's R-type, it tells ALU Control: "Look at the function bits (funct) at the end of the instruction to decide."ALU Control generates the specific 4-bit signal.ALU receives the signal and performs the actual math (+, -, AND, OR).
