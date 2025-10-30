

#### & zero Register
- In the MIPS architecture, $zero (also written as $0) is a special-purpose register that is hardwired to always contain the value 0.
+ key features
2. Read-Only: You can read the value 0 from it at any time, but you cannot write a different value into it. Any instruction that attempts to modify $zero will have no effect; its value will remain 0.
1. Real Hardware: It's not just a programming convenience or a placeholder; it is a physical register implemented in the CPU hardware.