# Lia


Lia is the package manager for Ellie. Also version manager for ellie.

## Creating new project

```shell
lia new my_project
```

This command will give you the [file structure](./file_structure.md) of a new project.

# .lia configuration file

```yaml
package_name: my_project
details: My project
version: 0.0.1
dependencies:
    - # Package from github
      branch: main
      source: github.com/ahmtcn123/wole
    - # Package from lia
      name: wole
      version: 0.0.1

```
---
# Installing packages

## Install from github
```shell
lia install github.com/ahmtcn123/wole
```

## Install from lia
```shell
lia install wole
```
---
# Publishing packages

For publishing packages, you need to register to [lia](https://lia.ellie-lang.org).

After registering, you can get your [api key](https://lia.ellie-lang.org/api-key) and save it by running the following command:

```shell	
lia config set api-key <api-key>
```

After that, you can publish your package by running the following command:

```shell
lia publish
```
---
# Running ellie code

For running ellie code, you can use the following command:
```shell
lia run
```
---
# Running tests
```shell
lia test
```

Next: [Syntax](./syntax/README.md)