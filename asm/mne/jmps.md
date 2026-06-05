---
title: Jump Instructions
parent: Architecture
layout: default
---

# Jump Instructions
Mnemonic: `JMP`  
Opcode: `0x08`

Mnemonic: `JEQ`  
Opcode: `0x09`

Mnemonic: `JNQ`  
Opcode: `0x0A`

Mnemonic: `JLS`  
Opcode: `0x0B`

Mnemonic: `JGT`  
Opcode: `0x0C`

Mnemonic: `CALL`  
Opcode: `0x0D`

Mnemonic: `RET`  
Opcode: `0x0E`

## Syntax
This syntax applies to JEQ, JNQ, JLS and JGT. The RET instruction does not take operands.
```
jmp [label/mem/imm8/imm16]
```

### Conditional Examples
JEQ: Only jumps if FLAGS has the equal flag. See [CMP](cmp.md) for more info.
```
cmp a0, 4
jeq label0
jmp label1

label0:
mv a1, 1

label1:
; if condition satifies, a1 should be 1
```

JNQ: Similar format to JEQ, just its counterpart. See [CMP](cmp.md) for more info.
```
; da reversed logic

cmp a0, 4
jnq label1
; jmp label0 (can fall through)

label0:
mv a1, 1

label1:
; if condition satisfies, a1 should be 1
```

JLS: Only jumps if FLAGS has the less than flag. See [CMP](cmp.md) for more info.
```
cmp b6, 28
jls label0
jmp label1

label0:
mv a1, 1

label1:
; if condition satisfies, a1 should be 1
```

JGT: Similar format to JLS, just its counterpart. See [CMP](cmp.md) for more info.
```
cmp b6, 50
jgt label0
jmp label1

label0:
mv a1, 1

label1:
; if condition satisfies, a1 should be 1
```

<br/>

### Extra Examples
CALL: Saves the address of the next instruction into the return address register, then jumps to the address.  

{: .warning }
You MUST have the RET instruction at the end of a function label or the CPU will fall through them and potentially cause memory access faults. See [Bad Examples](###bad-examples) for more info.

```
main:
  call foo
  ret

foo:
  mv a0, 1
  mv a1, 2
  add a0, a1
  mv p1, a0
  ret

```

RET: Takes the address of the return address and jumps to it.

{: .warning }
Only use this at the end of a function label. I'll let you figure out what happens. See [Bad Examples](###bad-examples) for more info.

<br/>

### Bad Examples
CALL:
```
main:
   call func0
   call func1
   ret

func0:
  add a0, 1    ; does not return, falling into func1()

func1:
  mv a0, 2
  ret
```

RET:
```
main:
   jmp func0
   call func1
   ret

func0:
  add a0, 1    ; return address not saved, jumps to random memory
  ret

func1:
  mv a0, 2
  ret
```