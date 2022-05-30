# File Keys

There is two types of file keys:

### Global File Key
This could be used to store global file keys. For example disabling various syntax warnings.

```ellie
@!allow="ClassNameRule"; //Allow 'ClassNameRule' rule to be ignored
```

### Element File Key
This could be used in top of the language items. For example disabling single syntax warning or creating comment.

```ellie
@description = "Print line";
@example = "
    v text = "Hello world!";
    test(text); //Prints 'Hello world!'
";
fn test(text: string) {
    print(text);
}
```
