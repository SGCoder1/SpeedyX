---
title: System Execute
parent: Architecture
layout: default
---

# System Execute Instruction
Mnemonic: `SYSEXEC`  
Opcode: `0x55`

## Syntax
```
sysexec
```

## Description
Calls a system function using the SO, ST and SV as the arguments and SF as the address of the dispatch function. 
This is the closest equivalent of calling an interrupt (or more of a syscall in x86-64).

{: .caution }
This documentation is currently a stub. While the emulator currently uses these 3 registers as arguemnts, **they are subject to change.**