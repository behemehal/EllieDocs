# What is ellie
Ellie is a type-safe programing language that runs on embedded and sandboxed environments. 

## Package Management
Ellie's package manager [Lia](./lia.md) keeps all the packages in a global archive. Lia uses ellie's pre-compile system, so when you install a package, it will be compiled and stored in the archive. This helps you out in speed and memory usage.

## Universally Compiled
Ellie has leveling system on target environments. Packages with matching levels can be used on the target environment.

### VM Levels
| Level | Environment | Architecture      |
| ----- | ----------- | ----------------- |
| 0     | Windows     | x86, ARM, x64     |
| 0     | Linux       | x86, ARM, x64     |
| 2     | Redox       | x86               |
| 0     | MacOS       | x86, ARM, x64     |
| 1     | Metal       | stm32f1xx         |
| 1     | Metal       | CortexM           |

## FFI Interface
Ellie has a [Foreign Function Interface](./ffi.md) that allows you to call C functions from your code. Also you can call Ellie functions from C.

