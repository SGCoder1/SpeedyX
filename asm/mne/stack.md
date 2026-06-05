---
title: Stack Instructions
parent: Architecture
layout: default
---

# Stack Instructions
Mnemonic: `PUSH`  
Opcode: `0x0F`

Mnemonic: `POP`  
Opcode: `0x10`

## Syntaxes
```
push [reg/imm8/imm16]
```

```
pop [reg/mem]
```

### Examples
PUSH: "Pushes" or places a value on top of the stack.

```
; push 12 bytes (6 bytes on 16-bit mode) of example data
mv p4, 0x2940
push 40
push 0x2000
push p4
```

POP: "Pops" or removes the value at the top of the stack and saves it into a register.
```
; pop (or free) 12 bytes (6 bytes on 16-bit mode) of example data
mv p4, 0x2940
pop a0
pop a1
pop [0x4000]
```