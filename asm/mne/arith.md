---
title: Arithmetic Instructions
parent: Architecture
layout: default
---

# Arithmetic Instructions
Mnemonic: `ADD`  
Opcode: `0x03`

Mnemonic: `SUB`  
Opcode: `0x04`

Mnemonic: `MUL`  
Opcode: `0x05`
 
Mnemonic: `DIV`  
Opcode: `0x06`

Mnemonic: `MOD`  
Opcode: `0x07`

## Syntax
This syntax applies to all of them.
```
mne reg/mem, reg/mem/imm8/imm16
```

### Examples
```
add a0, a1
```

```
mul a0, [a1 + 1]
```

```
mod a0, 0x40
```