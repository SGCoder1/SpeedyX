---
title: Move Value Instructions
parent: Architecture
layout: default
---

# Move Value Instructions
Mnemonic: `MV`  
Opcode: `0x01`

Mnemonic: `MVP`  
Opcode: `0x02`

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

### Previlege Examples
{: .warning }
`MVP` is an experimental instruction and is subject to change. In the best case, avoid using this instruction.

```
mvp sf, 0x5000
```

```
mvp fb, 0x4000
```


{: .caution }
Speedy-X does not support memory-to-memory or immediate-to-displacement instructions. Also, the `MV` instruction cannot access previleged registers.

### Invalid
```
mv [0x50], [p0 + 3]
```

```
mv [p0 + 3], 0x20
```

```
mv sf, 0x5000
```