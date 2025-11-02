### Terms

* Nested function
- A nested function, also known as a non-leaf function, is a function that calls other functions within its own body.
It sits in the middle of a call chain, acting like a "branch" on a tree rather than a "leaf" at the end.

##### procedure frame
- a procedure frame (also called an activation record) is a specific block or segment of memory on the stack that is allocated for a single function call.
* What it contains
- This workspace holds all the temporary information that a specific function needs to do its job. It contains:
1. Saved argument registers: If this function needs to call another function, it saves the arguments it received.
2. Saved return address: The $ra register is saved here if this function calls another function.
3. Saved saved registers: Any $s registers that this function plans to use.
4. Local arrays and structures: Any local variables that the function creates.
* How It's Managed (Pointers)
Two main pointers manage this frame:
- Stack Pointer ($sp): This pointer is dynamic. It always points to the very top (the "end," at the lowest memory address) of the stack. As the function adds new data (like in diagram b), the $sp moves down.
- Frame Pointer ($fp): This pointer is stable. The slide states it points to the first word of the procedure frame (the "beginning," at the highest memory address).
* Why It's Useful
Why the $fp is so important: it provides a stable base for references.
Even if the function calls other functions (which would move the $sp pointer), the $fp pointer stays in the same place. This allows the function to reliably find its own local variables by using a fixed, constant offset from the $fp (e.g., "my first local variable is always at $fp - 8").