# Run Stages

Ellie code has 4 stages to be run. These stages are:

- ## [Tokenizer Module](./tokenizer_module.md)
    Tokenizes the code. This stage is the first stage of the code. It takes the code and splits it into code elements. These tokens are used in the next stage.
- ## Parser
    Parses the code. This stage is the second stage of the code. It takes the tokens and parses them into a tree and checks for type errors. These `Definite` items are used in the next stage.
- ## ByteCode
    Generates bytecode. This stage is the third stage of the code. It takes the `Definite` items and generates bytecode. These bytecode are used in the next stage.
- ## VM
    Runs the bytecode. This stage is the fourth stage of the code. It takes the bytecode and runs it.