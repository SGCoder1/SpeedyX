---
title: Architecture
parent: Speedy-X
layout: default
---

# Instruction Set
- This specifies the instruction set for BOTH the 16-bit and 32-bit architectures. The 16-bit only segments will be specified.
- Count: 27 instructions | 32 registers

## Instructions
**0x01: [MV]({% link asm/mne/mv.md %})**  
**0x02: [ADD]({% link asm/mne/arith.md %})**  
**0x03: [SUB]({% link asm/mne/arith.md %})**  
**0x04: [MUL]({% link asm/mne/arith.md %})**  
**0x05: [DIV]({% link asm/mne/arith.md %})**  
**0x06: [MOD]({% link asm/mne/arith.md %})**  
**0x07: [JMP]({% link asm/mne/jmps.md %})**  
**0x08: [JEQ]({% link asm/mne/jmps.md %})**  
**0x09: [JNQ]({% link asm/mne/jmps.md %})**  
**0x0A: [JLS]({% link asm/mne/jmps.md %})**  
**0x0B: [JGT]({% link asm/mne/jmps.md %})**  
**0x0C: [CALL]({% link asm/mne/jmps.md %})**  
**0x0D: [RET]({% link asm/mne/jmps.md %})**   
**0x0E: [PUSH]({% link asm/mne/stack.md %})**  
**0x0F: [POP]({% link asm/mne/stack.md %})**  
**0x10: [CMP]({% link asm/mne/cmp.md %})**  
**0x11: [AND]({% link asm/mne/binmp.md %})**  
**0x12: [OR]({% link asm/mne/binmp.md %})**  
**0x13: [XOR]({% link asm/mne/binmp.md %})**  
**0x14: [LSH]({% link asm/mne/binmp.md %})**  
**0x15: [RSH]({% link asm/mne/binmp.md %})** 
**0x16: [HLT]({% link asm/mne/hlt.md %})**  
**0x17: [WRFLTB]({% link asm/mne/wrtsys.md %})**  
**0x18: [WRSYSF]({% link asm/mne/wrtsys.md %})**  
**0x19: [BRK]({% link asm/mne/brk.md %})**  
**0x1A: [BV]({% link asm/mne/bv.md %})** _(16-bit only)_  
**0x55: [SYSEXEC]({% link asm/mne/sysexec.md %})**

## Registers

### General Purpose

| Register | Opcode | 16-bit Size | 32-bit Size |
| ----     |-----   | -------     | -------     |
| A0       | 0x01   | 2 bytes     | 4 bytes     |
| A1       | 0x02   | 2 bytes     | 4 bytes     |
| A2       | 0x03   | 2 bytes     | 4 bytes     |
| A3       | 0x04   | 2 bytes     | 4 bytes     |
| B0       | 0x05   | 2 bytes     | 4 bytes     |
| B1       | 0x06   | 2 bytes     | 4 bytes     |
| B2       | 0x07   | 2 bytes     | 4 bytes     |
| B3       | 0x08   | 2 bytes     | 4 bytes     |

### Special

| Register | Full Name           | Opcode | 16-bit Size | 32-bit Size | Priviledge Required? |
| ----     |-----                |-----   | -------     | -------     | -------------------  |
| SO       | System Operation    | 0x19   | 2 bytes     | 2 bytes     | No                   |
| ST       | Screen Output Type  | 0x1A   | 2 bytes     | 2 bytes     | No                   |
| SV       | Screen Output Value | 0x1B   | 2 bytes     | 2 bytes     | No                   |
| SF       | System Function     | 0x1C   | 2 bytes     | 4 bytes     | Yes                  |
| FB	   | Fault Base          | 0x1D   | 2 bytes     | 4 bytes     | Yes                  |
| FC       | Fault Code          | 0x1E   | 2 bytes     | 4 bytes     | No (readonly)        |
| PC       | Program Counter     | 0x1F   | 2 bytes     | 4 bytes     | No (readonly)        |
| CI       | Current Instruction | 0x20   | 2 bytes     | 4 bytes     | No (readonly)        |