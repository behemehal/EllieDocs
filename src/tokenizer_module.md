# Tokenizer Module

Source: [/ellie_engine/tokenizer](https://github.com/behemehal/Ellie-Language/tree/main/ellie_engine/tokenizer)

- ### [Creating Tokenizer](#creating-tokenizer)
    - #### [Example Implementation](#example-implementation)
        - [Creating `ProgramRepository`](#creating-programrepository)
            * [What is `ProgramRepository::read_main`?](#what-is-programrepositoryread_main)
            * [Implementing `ProgramRepository::read_main`](#implementing-programrepositoryread_main)
            * [Implementing `ProgramRepository::read_module`](#implementing-programrepositoryread_module)
        - [Building Pager](#building-pager)
            * [What is `Pager::new`?](#what-is-pagernew)

## Creating Tokenizer

### Example Implementation

#### Creating `ProgramRepository`

To create tokenizer you should create a struct for `[Program Repository]()` trait. ProgramRepository is the file reader bridge between tokenizer and user-defined code.


Create a struct that implements `ProgramRepository` trait.

```rust,noplayground
#[derive(Clone)]
struct Repository {
    used_modules: Vec<String>,
    main_hash: usize,
    module_name: String,
    target_path: String,
}
```
---

##### What is `ProgramRepository::read_main`?

*Signature of `ProgramRepository::read_main`:*

```rust,noplayground
impl ProgramRepository for Repository {
    fn read_main(&self) -> MainProgram {
        //...
    }
    //...
}
```

What is `ellie_engine::utils::MainProgram`? And whats content of it?

By default every file's should have a unique `file_hash`, contents of it `file_content` and directory information such as `file_name` and `start_director`. `file_hash` is a unique hash, but Id doesn't need to be hash of file content. It can be anything that is unique.

---

##### Implementing `ProgramRepository::read_main`

In this example we got the hash of the file but its not necessary.


```rust,noplayground
impl ProgramRepository for Repository {
    fn read_main(&self) -> MainProgram {
        let main_file_content = fs::read_to_string(&self.target_path).unwrap();

        let file_name = self.target_path.split("/").collect::<Vec<&str>>();
        let file_name = file_name[file_name.len() - 1];

        let mut main_file_hasher = DefaultHasher::new();
        main_file_content.hash(&mut main_file_hasher);
        let first_page_hash = main_file_hasher.finish();
        self.main_hash = first_page_hash as usize;
        MainProgram {
            file_content: main_file_content,
            file_name: 
            file_hash: first_page_hash as usize,
            start_directory: format!(
                "<ellie_module_{}>",
                self.cli_compiler_settings.compiler_settings.name
            ),
        }
    }
    //...
}
```
Now `ProgramRepository::read_main` function is implemented. Lets implement `ProgramRepository::read_module` function.

---

##### What is `ProgramRepository::read_module`?

*Signature of `ProgramRepository::read_module`:*

```rust,noplayground
impl ProgramRepository for Repository {
    fn read_module(
        &mut self,
        link_module: bool,
        current_path: String,
        requested_path: String,
    ) -> ResolvedImport {
        //...
    }
    //...
}
```

So what is `ResolvedImport`? `ResolvedImport` is message that we're sending to tokenizer.

```rust,noplayground
#[derive(Default, Debug)]
pub struct ResolvedImport {
    pub found: bool,
    pub resolve_error: String,
    pub hash: usize,
    pub path: String,
    pub matched: ImportType,
}
```

- `ResolvedImport::found` is a boolean that tells tokenizer if the file is found or not. If the file is not found tokenizer will throw an error. The error message is dependend on `ResolvedImport::resolve_error` if its provided it will display that custom error message. If not it will display default error message.

- `ResolvedImport::hash` is a hash of the file. It can be anything that is unique.
- `ResolvedImport::path` is a path of the file. It can be anything that is unique.
- `ResolvedImport::matched`
    This is the part where everything gets complicated.

    ```rust,noplayground
    pub enum ImportType {
        Code(String),
        Module(Module),
    }
    ```
    So this enum has two variants. `Code` and `Module`. `Code` variant is for importing code. `Module` variant is for importing pre-compiled modules, we will talk about this later.

- What is parameters of `ProgramRepository::read_module`?
    - `link_module` is a boolean that tells tokenizer if the file is a module or not. Think of it like you are importing a module from package manager. Usually import imports from path this is why we need `link_module` parameter.
    - `current_path` is a path of the file that is importing the module.
    - `requested_path` is a path of the module that is being imported.

##### Implementing `ProgramRepository::read_module`

##### Providing Code `ImportType::Code`
In this example we will provide `ImportType::Code` (Text) to tokenizer. We will read the file and return it as `ImportType::Code`.


First of all, we should see how paramters could be:

```sh
Link module: false
Current path: <ellie_module_main>/main.ei
Requested path: ./deb.ei
```

What's this `<ellie_module_main>`?

Ellie does not have a directory manager built-in because of maximum flexibility. So we need to provide a directory manager. In this example we will use `<ellie_module_main>` as our main directory. We already know our `main.ei` file's path so its not that hard to figure out where is `./deb.ei` file.


```rust,noplayground
impl ProgramRepository for Repository {
    fn read_module(
        &mut self,
        link_module: bool,
        current_path: String,
        requested_path: String,
    ) -> ResolvedImport {
        let starter_name = format!("<ellie_module_{}>", self.module_name);
        match parse_module_import(&current_path, &requested_path) {
            Ok(path) => {
                ...
            },
            Err(err) => {
                ...
            }
        }
```

Wow what happened here? Do you remember `module_name` variable? We used it in `Repository` struct. Also `parse_module_import` function comes from `ellie_engine::ellie_core::module_path` module. It takes two parameters `current_path` and `requested_path`. It returns `Ok(path)` if the path is valid. If the path is not valid it returns `Err(err)`. Now how to handle errors?

```rust,noplayground
impl ProgramRepository for Repository {
    fn read_module(
        &mut self,
        link_module: bool,
        current_path: String,
        requested_path: String,
    ) -> ResolvedImport {
        let starter_name = format!("<ellie_module_{}>", self.module_name);
        match parse_module_import(&current_path, &requested_path) {
            Ok(path) => {
                ...
            }
            Err(err) => {
                ResolvedImport {
                    found: false,
                    resolve_error: "Cannot access outside of workspace".to_string(),
                    ..Default::default()
                }
            }
        }
```

If `parse_module_import` gives a error its definetly because of the path is not valid. So we will return `ResolvedImport` with `found` as `false` and `resolve_error` as `Cannot access outside of workspace`. Now lets handle `Ok(path)`.

```rust,noplayground
impl ProgramRepository for Repository {
    fn read_module(
        &mut self,
        link_module: bool,
        current_path: String,
        requested_path: String,
    ) -> ResolvedImport {
        let starter_name = format!("<ellie_module_{}>", self.module_name);
        match parse_module_import(&current_path, &requested_path) {
            Ok(path) => {
                let real_path = path
                    .replace(
                        &starter_name,
                        Path::new(&self.target_path)
                            .absolutize()
                            .unwrap()
                            .parent()
                            .unwrap()
                            .to_str()
                            .unwrap(),
                    ).clone();
                if Path::new(&real_path).exists() {
                    let mut file = File::open(&real_path).unwrap();
                    let mut contents = String::new();
                    file.read_to_string(&mut contents).unwrap();
                    let mut hasher = DefaultHasher::new();
                    contents.hash(&mut hasher);
                    ResolvedImport {
                        found: true,
                        hash: hasher.finish().try_into().unwrap(),
                        path,
                        matched: ImportType::Code(contents),
                    }
                } else {
                    ResolvedImport {
                        found: false,
                        resolve_error: "Path does not exist".to_string(),
                        ..Default::default()
                    }
                }
            }
            Err(err) => {
                ...
            }
        }
    }
}
```

In this part we got `target_path` from our struct. Its the `main.ei` file's absolute path. `path` is `<ellie_module_main>/deb.ei` and we replaced `<ellie_module_main>` with absolute path of our `main.ei` file. Which in this case its `/home/ellie/main.ei`. Now we are changing `<ellie_module_main>` with this path. So the path is now `/home/ellie/deb.ei`. Now we are checking if the file exists. If it exists we will read the file and return it as `ImportType::Code`. If it does not exist we will return `ResolvedImport` with `found` as `false` and `resolve_error` as `Path does not exist`.

##### Providing Module `ImportType::Module`
This functionality will be removed in the future. So we will not talk about it.
---

#### Building Pager

**Signature:**

```rust,noplayground
pub fn new(
        main: String,
        main_file_name: String,
        path: String,
        import_resolver: E,
        initial_hash: usize,
    ) -> Self {
        ...
    }
```

- `main` is the main file's content.
- `main_file_name` is the main file's name.
- `path` is the main file's path.
- `import_resolver` is closure for importing modules. |link_module: boolean, path: string, current_path: string| -> ResolvedImport

`Pager` is interface for tokenizing workspace. It takes `main` file's content and `main_file_name` and `path` and `import_resolver` and `initial_hash`. `initial_hash` is the hash of `main` file's content. It returns `Pager` struct.

---

##### What is Pager::new?

```rust,noplayground
let main_program = program_repository.read_main();
let mut pager = Pager::new(
    main_program.file_content,
    main_program.file_name,
    format!("{}/", main_program.start_directory),
    move |link_module, path, module_identifier| {
        program_repository.read_module(link_module, path.clone(), module_identifier)
    },
    main_program.file_hash,
);
match pager.run() {
    Ok(_) => Ok(pager.pages),
    Err(errors) => Err(errors),
}
```

Now we are creating `Pager` with `main_program.file_content` and `main_program.file_name` and `format!("{}/", main_program.start_directory)` and closure for importing modules and `main_program.file_hash`. Now we are running `pager` and if it returns `Ok` we are returning `pager.pages`. If it returns `Err` we are returning `Err(errors)`.

---

In next stage, we will talk about `Parser` and how to use `pager.pages`.