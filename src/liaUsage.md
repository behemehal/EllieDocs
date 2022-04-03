# Usage

## Installing Compiler

```sh
lia installFeature elliec
```

## Installing EllieVM

```sh
lia installFeature ellievm
```

## Creating new project

```sh
lia init
```

This command will give you the [file structure](./file_structure.md) of a new project.

# lia.yaml configuration file

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

```sh
lia install github.com/ahmtcn123/wole
```

## Install from lia

```sh
lia install wole
```

---

# Publishing packages

For publishing packages, you need to register to [lia](https://lia.ellie-lang.org).

~~After registering, you can get your [api key](https://lia.ellie-lang.org/api-key) and save it by running the following command:~~

_`Lia cannot serve any packages right now`_

```sh
lia config set api-key <api-key>
```

After that, you can publish your package by running the following command:

```sh
lia publish
```

---

# Compiling workspace

For compiling ellie workspace, you can use the following command:

```sh
lia compile
```

---

# Running ellie code

For running ellie code, you can use the following command:

```sh
lia run
```

---

# Running tests

```sh
lia test
```
