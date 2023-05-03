# Building Ellie

# Package Features

## Packages

- `ellie_engine` - Ellie Engine contains tokenizer, parser, bytecode, fmt, vm and other core components.
- `elliec` - EllieC is compiler binary for Ellie.
- `ellievm` - EllieVM is virtual machine binary for Ellie.
- `elliefmt` - EllieFmt is formatter binary for Ellie.


## ellie-engine
- ### Features
    * #### compiler
        This feature enables only compiler related components. Imports following libraries `ellie_tokenizer`, `ellie_parser`, `ellie_bytecode` and `ellie_core/compiler_utils`.
    * #### vm
        This feature enables only vm related components. Imports following libraries `ellie_vm`, `ellie_vm/std`.
    * #### fmt
        This feature enables only fmt related components. Imports following libraries `ellie_fmt`.
    * #### standard_rules
        This feature enables standard rules check on syntax. Imports following libraries `ellie_parser/standard_rules`.
    * #### cli-utils
        This feature enables cli utils. Imports following libraries `ellie_renderer_utils/cli-utils`.
    * #### B64
        This feature selects x64 architecture. Imports following libraries `ellie_vm/B64`.
    * #### B32
        This feature selects x32 architecture. Imports following libraries `ellie_vm/B32`.
    * #### B16
        This feature selects x16 architecture. Imports following libraries `ellie_vm/B16`.

# Tools
Ellie has tools relasing reAssembling bytecode instuctions, cleaning up repository and many more.

- ### `clean_up.sh` | `clean_up.ps1`
    This script cleans up repository by removing all the compiled binaries and other files.

- ### `reAssembler.js`
    This script reAssembles `instruction.json` file to required `instruction_table.rs, instruction_utils.rs` and `instructions.md` files.

- ### `release.js`
    This script selected binaries and preapares output for release.

- ### `integration_test` crate
    This crate contains integration tests for Ellie. You can test compiler, tokenizer, parser, vm and fmt using this crate.