---
title: Previlege Write Instructions
parent: Architecture
layout: default
---

# Previlege Write Instructions
Name: Write To Fault Base  
Mnemonic: `WRFLTB`  
Opcode: `0x17`

Name: Write To System Function  
Mnemonic: `WRSYSF`  
Opcode: `0x18`

## Description
Writes the value from `p0` to its corresponding previleged register.

## Syntaxes
```
wrfltb
```
```
wrsysf
```

{: .caution }
Since these write to the interrupt registers, a general protection fault will occur if not written to a valid address.