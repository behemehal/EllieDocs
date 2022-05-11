# Creating new project

## Creating new project

```sh
lia init
```

## Optios

* `-l` or `--lib`: Create a library project.

This command will give you the [file structure](./file_structure.md) of a new project.

# lia.yaml configuration file

```yaml
package_name: MyProject
details: My project
license: MIT
version: 0.0.1
dependencies:
  - name: ellieStd
    version: 0.1.0
    url: github.com/behemehal/Ellie-Standard-Library
```