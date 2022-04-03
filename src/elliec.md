# EllieC

EllieC is the compiler for the Ellie language

## Commands

- ### compile
  `elliec compile [file] -j -b [version] -c [module-description] -m [module-name] -p ./ -o bin -i [File]=[Folder]`
  #### Options
  - `-j | --json-log`
    - Outputs the compilation log in JSON format
  - `-b | --binary-version`
    - Version of the package
  - `-c | --module-description`
    - Description of the module
  - `-m | --module-name`
    - Name of the module
  - `-p | --output-path`
    - Output path
  - `-o | --output-type json | `
    - Output type
        * `bin`: Binary
        * `json`: JSON
        * `byteCode`: Bytecode
        * `depA`: Dependency Analysis
        * `nop`: No Output
  - `-i | --import-module {binary}={workspaceFolder}`:
    - Import a module
    - example usage: `--insert-module ./ellieStd.eib`. For referencing code in other modules, you can give directory path to this option. For example; `--insert-module ./ellieStd.eib=./ellieStdFolder`.
- ### viewModule
    `elliec viewModule [file]`
    #### Options
    - `-j | --json-log`
      - Outputs the viewer process log in JSON format
    #### Output
    ```
        ModuleName        = test
        ModuleDescription = A ellie package
        ModuleVersion     = 1.0.0
        EllieVersion      = 2.0.0
        InnerModules      =
            ModuleName    = ellie
            ModuleVersion = 1.0.0
    ```
