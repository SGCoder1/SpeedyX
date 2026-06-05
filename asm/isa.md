---
title: Architecture
parent: Speedy-X
layout: default
---

# Instruction Set
- This specifies the instruction set for BOTH the 16-bit and 32-bit architectures. The 16-bit only segments will be specified.
- Count: 27 instructions | 34 registers

## Instructions
**0x01: [MV](mne/mv.md)**  
**0x02: [MVP](mne/mvp.md)**  
**0x03: [ADD](mne/arith.md)**  
**0x04: [SUB](mne/arith.md)**  
**0x05: [MUL](mne/arith.md)**  
**0x06: [DIV](mne/arith.md)**  
**0x07: [MOD](mne/arith.md)**  
**0x08: [JMP](mne/jmps.md)**  
**0x09: [JEQ](mne/jmps.md)**  
**0x0A: [JNQ](mne/jmps.md)**  
**0x0B: [JLS](mne/jmps.md)**  
**0x0C: [JGT](mne/jmps.md)**  
**0x0D: [CALL](mne/jmps.md)**  
**0x0E: [RET](mne/jmps.md)**  
**0x0F: [PUSH](mne/stack.md)**  
**0x10: [POP](mne/stack.md)**  
**0x11: [CMP](mne/cmp.md)**  
**0x12: [AND](mne/bitmp.md)**  
**0x13: [OR](mne/bitmp.md)**  
**0x14: [XOR](mne/bitmp.md)**  
**0x15: [LSH](mne/bitmp.md)**  
**0x16: [RSH](mne/bitmp.md)**  
**0x17: [HLT](mne/hlt.md)**  
**0x18: [BRK](mne/brk.md)**  
**0x19: [BV](mne/bv.md)**  

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
| SO       | System Operation    | 0x19   | 2 bytes     | 2 bytes     | No
| ST       | Screen Output Type  | 0x1A   | 2 bytes     | 2 bytes     | No
| SV       | Screen Output Value | 0x1B   | 2 bytes     | 2 bytes     | No
| SF       | System Function     | 0x1C   | 2 bytes     | 4 bytes     | Yes
| FB	   | Fault Base          | 0x1D   | 2 bytes     | 4 bytes     | Yes
| FC       | Fault Code          | 0x1E   | 2 bytes     | 4 bytes     | No
| PC       | Program Counter     | 0x1F   | 2 bytes     | 4 bytes     | No (readonly)
| CI       | Current Instruction | 0x20   | 2 bytes     | 4 bytes     | No (readonly)