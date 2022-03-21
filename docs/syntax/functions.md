# Functions

```ellie
fn functionName(param1: Type, param2: Type) : ReturnType {
    // function body
}
```

## Generics with functions

```ellie
fn functionName<T>(param1: T, param2: T) : T {
    // function body
}
```

## Functions with unsized parameter
```ellie
fn functionName(*param1: T) {
    // function body
}
```

Now you can call the function with any size of parameter. But inside the function, variable `param1` will be a array of `T` type.

```ellie

fn functionName(*param1: int) {
    // function body
    println("I have " + param1.length + " elements");
}

functionName(1, 2, 3, 4, 5);
// I have 5 elements

functionName(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
// I have 10 elements
```