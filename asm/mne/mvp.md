---
title: MVP
parent: Architecture
layout: default
---

# Move Value Privileged Instruction
Mnemonic: `MVP`  
Opcode: `0x02`

## Syntax
```
mv [reg/mem], [reg/mem/imm8/imm16]
```

**Note: This syntax is the same as MV as this one allows previledged instructions. See the examples [here.](mv.md)**

### Previlege Examples
```
mvp sf, 0x5000
```

```
mvp fb, 0x4000
```