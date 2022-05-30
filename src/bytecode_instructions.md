# Instructions

## Addressing Modes
- Implict
  - Instruction that takes no operands.
- Immediate
  - Load immediate value
- Absolute
  - Get data from stack position
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
- AbsoluteIndex
  - Get data from stack position and get index of it
- AbsoluteProperty
  - Get data from stack position and get property of it


## All Instructions

- [LDA](./bytecode_instructions.md#lda)
- [LDB](./bytecode_instructions.md#ldb)
- [LDC](./bytecode_instructions.md#ldc)
- [LDX](./bytecode_instructions.md#LDX)
- [LDY](./bytecode_instructions.md#LDY)
- [STA](./bytecode_instructions.md#STA)
- [STB](./bytecode_instructions.md#STB)
- [STC](./bytecode_instructions.md#STC)
- [STX](./bytecode_instructions.md#STX)
- [STY](./bytecode_instructions.md#STY)
- [EQ](./bytecode_instructions.md#EQ)
- [NE](./bytecode_instructions.md#NE)
- [GT](./bytecode_instructions.md#GT)
- [LT](./bytecode_instructions.md#LT)
- [GQ](./bytecode_instructions.md#GQ)
- [LQ](./bytecode_instructions.md#LQ)
- [AND](./bytecode_instructions.md#AND)
- [OR](./bytecode_instructions.md#OR)
- [ADD](./bytecode_instructions.md#ADD)
- [SUB](./bytecode_instructions.md#SUB)
- [MUL](./bytecode_instructions.md#MUL)
- [EXP](./bytecode_instructions.md#EXP)
- [DIV](./bytecode_instructions.md#DIV)
- [MOD](./bytecode_instructions.md#MOD)
- [INC](./bytecode_instructions.md#INC)
- [DEC](./bytecode_instructions.md#DEC)
- [JMP](./bytecode_instructions.md#JMP)
- [CALL](./bytecode_instructions.md#CALL)
- [RET](./bytecode_instructions.md#RET)
- [AOL](./bytecode_instructions.md#AOL)
- [PUSH](./bytecode_instructions.md#PUSH)
- [LEN](./bytecode_instructions.md#LEN)
- [A2I](./bytecode_instructions.md#A2I)
- [A2F](./bytecode_instructions.md#A2F)
- [A2D](./bytecode_instructions.md#A2D)
- [A2B](./bytecode_instructions.md#A2B)
- [A2S](./bytecode_instructions.md#A2S)
- [A2C](./bytecode_instructions.md#A2C)
- [A2O](./bytecode_instructions.md#A2O)



# LDA
Load value to A register

## Addressing Modes
- Immediate
- Absolute
- IndirectB
- IndirectC
- IndirectX
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# LDB
Load value to B register

## Addressing Modes
- Immediate
- Absolute
- IndirectA
- IndirectC
- IndirectX
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# LDC
Load value to C register

## Addressing Modes
- Immediate
- Absolute
- IndirectA
- IndirectB
- IndirectX
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# LDX
Load value to X register

## Addressing Modes
- Immediate
- Absolute
- IndirectA
- IndirectB
- IndirectC
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# LDY
Load value to A register

## Addressing Modes
- Immediate
- Absolute
- IndirectA
- IndirectB
- IndirectC
- IndirectX
- AbsoluteIndex
- AbsoluteProperty

# STA
Store value from A register to stack position

## Addressing Modes
- Implict

# STB
Store value from B register to stack position

## Addressing Modes
- Implict

# STC
Store value from C register to stack position

## Addressing Modes
- Implict

# STX
Store value from X register to stack position

## Addressing Modes
- Implict

# STY
Store value from Y register to stack position

## Addressing Modes
- Implict

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

# INC
Increment A register

## Addressing Modes
- Implict

# DEC
Decrement A register

## Addressing Modes
- Implict

# JMP
Jump to address

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
- Immidiate
- Absolute
- IndirectA
- IndirectB
- IndirectC
- IndirectX
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# AOL
Alter locals for next instruction from other scope resets in next instruction

## Addressing Modes
- Absolute

# PUSH
Push value to array

## Addressing Modes
- Immidiate
- Absolute
- IndirectA
- IndirectB
- IndirectC
- IndirectX
- IndirectY
- AbsoluteIndex
- AbsoluteProperty

# LEN
Get length of array push to A register

## Addressing Modes
- Implict

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