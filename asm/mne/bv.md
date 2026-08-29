---
title: Bank Value Instruction
parent: Architecture
layout: default
---

# Bank Value Instruction
Mnemonic: `BV`  
Opcode: `0x1A`  
Description: Banks a 64 KB memory chunk from a base.

## Syntax
```
bv imm8/imm16
```

## Notes
- This instruction is only compatible for the 16-bit CPU.
- Register B1 is used as the banked chunk reference. The access is formatted as: `base + (B1 * 64KB)`.