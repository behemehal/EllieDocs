# Imports

Ellie has two kinds of imports:

### Unnamed import
Imports anything public from module.

```ellie
    import ellieStd;

    v age : int = 11;
```

### Named import
Imports anything public from module, but with reference.

```ellie
    import ellieStd as std;
    v age : std.int = 11;
```