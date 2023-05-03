# Instructions

## Addressing Modes
- Implict
  - Instruction that takes no operands.
- Immediate
  - Load immediate value
- Absolute
  - Get data from stack position
- AbsoluteIndex
  - Get data from from pointer[ index pointer ]
- AbsoluteProperty
  - Get data from array type's property
- AbsoluteStatic
  - Get data from static program
- IndirectA
  - Load A register value
- IndirectB
  - Load B register value
- IndirectC
  - Load C register value
- IndirectX
  - Load X register value
- IndirectY
  - Load Y register value

## All Instructions

- [LDA](./bytecode_instructions.md#lda)
- [LDB](./bytecode_instructions.md#ldb)
- [LDC](./bytecode_instructions.md#ldc)
- [LDX](./bytecode_instructions.md#ldx)
- [LDY](./bytecode_instructions.md#ldy)
- [STA](./bytecode_instructions.md#sta)
- [STB](./bytecode_instructions.md#stb)
- [STC](./bytecode_instructions.md#stc)
- [STX](./bytecode_instructions.md#stx)
- [STY](./bytecode_instructions.md#sty)
- [EQ](./bytecode_instructions.md#eq)
- [NE](./bytecode_instructions.md#ne)
- [GT](./bytecode_instructions.md#gt)
- [LT](./bytecode_instructions.md#lt)
- [GQ](./bytecode_instructions.md#gq)
- [LQ](./bytecode_instructions.md#lq)
- [AND](./bytecode_instructions.md#and)
- [OR](./bytecode_instructions.md#or)
- [ADD](./bytecode_instructions.md#add)
- [SUB](./bytecode_instructions.md#sub)
- [MUL](./bytecode_instructions.md#mul)
- [EXP](./bytecode_instructions.md#exp)
- [DIV](./bytecode_instructions.md#div)
- [MOD](./bytecode_instructions.md#mod)
- [INC](./bytecode_instructions.md#inc)
- [DEC](./bytecode_instructions.md#dec)
- [JMP](./bytecode_instructions.md#jmp)
- [CALL](./bytecode_instructions.md#call)
- [RET](./bytecode_instructions.md#ret)
- [AOL](./bytecode_instructions.md#aol)
- [PUSH](./bytecode_instructions.md#push)
- [LEN](./bytecode_instructions.md#len)
- [A2I](./bytecode_instructions.md#a2i)
- [A2F](./bytecode_instructions.md#a2f)
- [A2D](./bytecode_instructions.md#a2d)
- [A2B](./bytecode_instructions.md#a2b)
- [A2S](./bytecode_instructions.md#a2s)
- [A2C](./bytecode_instructions.md#a2c)
- [A2O](./bytecode_instructions.md#a2o)
- [JMPA](./bytecode_instructions.md#jmpa)
- [POPS](./bytecode_instructions.md#pops)
- [ACP](./bytecode_instructions.md#acp)
- [BRK](./bytecode_instructions.md#brk)
- [CALLN](./bytecode_instructions.md#calln)



# LDA
Load value to A register

## Addressing Modes
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty
- AbsoluteStatic
- IndirectB
- IndirectC
- IndirectX
- IndirectY

# LDB
Load value to B register

## Addressing Modes
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty
- AbsoluteStatic
- IndirectA
- IndirectC
- IndirectX
- IndirectY
- Paramater

# LDC
Load value to C register

## Addressing Modes
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty
- AbsoluteStatic
- IndirectA
- IndirectB
- IndirectX
- IndirectY

# LDX
Load value to X register

## Addressing Modes
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty
- AbsoluteStatic
- IndirectA
- IndirectB
- IndirectC
- IndirectY

# LDY
Load value to A register

## Addressing Modes
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty
- AbsoluteStatic
- IndirectA
- IndirectB
- IndirectC
- IndirectX

# STA
Store value from A register to stack position

## Addressing Modes
- Implict
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty

# STB
Store value from B register to stack position

## Addressing Modes
- Implict
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty

# STC
Store value from C register to stack position

## Addressing Modes
- Implict
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty

# STY
Store value from Y register to stack position

## Addressing Modes
- Implict
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty

# STX
Store value from X register to stack position

## Addressing Modes
- Implict
- Immediate
- Absolute
- AbsoluteIndex
- AbsoluteProperty

# EQ
Compare equality on B and C registers and set A register to 1 if equal, 0 otherwise

## Addressing Modes
- Implict

# NE
Compare inequality on B and C registers and set A register to 1 if not equal, 0 otherwise

## Addressing Modes
- Implict

# GT
Compare greater than on B and C registers and set A register to 1 if greater, 0 otherwise

## Addressing Modes
- Implict

# LT
Compare less than on B and C registers and set A register to 1 if less, 0 otherwise

## Addressing Modes
- Implict

# GQ
Compare greater than or equal to on B and C registers and set A register to 1 if greater or equal, 0 otherwise

## Addressing Modes
- Implict

# LQ
Compare less than or equal to on B and C registers and set A register to 1 if less or equal, 0 otherwise.

## Addressing Modes
- Implict

# AND
Perform AND operation on B and C registers and set A register to result

## Addressing Modes
- Implict

# OR
Perform OR operation on B and C registers and set A register to result

## Addressing Modes
- Implict

# ADD
Perform addition on B and C registers and set A register to result

## Addressing Modes
- Implict

# SUB
Perform subtraction on B and C registers and set A register to result

## Addressing Modes
- Implict

# MUL
Perform multiplication on B and C registers and set A register to result

## Addressing Modes
- Implict

# EXP
Perform exponentiation on B and C registers and set A register to result

## Addressing Modes
- Implict

# DIV
Perform division on B and C registers and set A register to result

## Addressing Modes
- Implict

# MOD
Perform modulus on B and C registers and set A register to result

## Addressing Modes
- Implict

# JMP
Jump to address

## Addressing Modes
- Absolute

# JMPA
Jump to address if A register is true

## Addressing Modes
- Absolute

# CALL
Call function

## Addressing Modes
- Absolute

# RET
Return data

## Addressing Modes
- Implict

# PUSH
Push A register value to array

## Addressing Modes
- Absolute
- AbsoluteIndex
- IndirectA
- IndirectB
- IndirectC
- IndirectX
- IndirectY

# SPUS
Push char to allocated string

## Addressing Modes
- Absolute
- AbsoluteIndex
- IndirectA
- IndirectB
- IndirectC
- IndirectX
- IndirectY

# LEN [DEPRECATED]
Get length of array push to A register

## Addressing Modes
- Absolute

# A2I
Convert A register to integer

## Addressing Modes
- Implict

# A2F
Convert A register to float

## Addressing Modes
- Implict

# A2D
Convert A register to double

## Addressing Modes
- Implict

# A2B
Convert A register to byte

## Addressing Modes
- Implict

# A2S
Convert A register to string

## Addressing Modes
- Implict

# A2C
Convert A register to char

## Addressing Modes
- Implict

# A2O
Convert A register to bool

## Addressing Modes
- Implict

# ARR
Allocated stack array indicator, shows how many items are in array next [size] instructions will be array

## Addressing Modes
- Implict

# STR
Allocate string on heap register its reference in stack memory

## Addressing Modes
- Implict

# SAR
To-be removed

## Addressing Modes
- Immediate

# POPS
Pops last stack location

## Addressing Modes
- Implict

# BRK
Remove stack

## Addressing Modes
- Implicit

# CALLN
Call native function in VM

## Addressing Modes
- Immediate

# CO [DEPRECATED]
Construct class

## Addressing Modes
- Absolute

# FN
Function definition, if active stack does not match with FN's absolute address then it will be ignored and skipped to end of it

## Addressing Modes
- Immediate

# DEA
Deallocate memory

## Addressing Modes
- Absolute