---
title: Break Insruction
parent: Architecture
layout: default
---

# Break Instruction
Mnemonic: `BRK`  
Opcode: `0x19`

## Syntax
```
brk
```

{: .caution }
Use this instruction only under debugging mode, or your program size can bloat. (Let the compiler handle this.)  
Also, **make sure the handler for break is implemented if this is ever used, or it will become a general protection fault.**