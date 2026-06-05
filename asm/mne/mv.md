---
title: MV
parent: Architecture
layout: default
---

# Move Value Instruction
Mnemonic: `MV`  
Opcode: `0x01`

## Syntax
```
mv [reg/mem], [reg/mem/imm8/imm16]
```

### Register Examples
```
mv a0, 2 
```

```
mv a1, a0
```

### Memory Examples
```
mv a1, [32]
```

```
mv [0x20], a1
```

```
mv [a1 + 4], a2
```

<br/>
<br/>


**Note: Speedy-X does not support memory-to-memory or immediate-to-displacement instructions. Also, this mnemonic does not
have access to certain registers.**

### Invalid
```
mv [0x50], [p0 + 3]
```

```
mv [p0 + 3], 0x20
```