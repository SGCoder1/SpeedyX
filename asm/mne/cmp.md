---
title: Compare Instructions
parent: Architecture
layout: default
---

# Compare Instruction
Mnemonic: `CMP`  
Opcode: `0x11`  
Description: Compares the 2 values and writes the result as a flag.

## Syntax
```
cmp [reg/mem], [reg/mem/imm8/imm16]
```

## Notes
This instruction implicitly writes to the FLAGS register (FL).
The [conditional jump instructions](jmps.md) implicitly read this also.

The following flags (from LSBit to MSBit) are as follows:  
- CMEQU
- CMNQU
- CMLSS
- CMGRT
- OVFLW (unused)