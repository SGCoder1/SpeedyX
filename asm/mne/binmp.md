---
title: Binary Manipulation Instructions
parent: Architecture
layout: default
---

# Binary Manipulation Instruction
Mnemonic: `AND`  
Opcode: `0x12`

Mnemonic: `OR`  
Opcode: `0x13`

Mnemonic: `XOR`  
Opcode: `0x14`

Mnemonic: `LSH`  
Opcode: `0x15`

Mnemonic: `RSH`  
Opcode: `0x16`

## Syntaxes
For AND, OR and XOR:
```
mne [reg/mem], [reg/mem/imm8/imm16]
```

For LSH and RSH:
```
mne reg, imm8/imm16
```

### Examples
```
mv a0, 2 
mv a1, 4
mv a2, 8

and a0, 1
or a1, a2
xor a0, a2
```

```
mv a1, 32
lsh a1, 3
rsh a1, 2
```