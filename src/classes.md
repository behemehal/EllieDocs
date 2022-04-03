# Classes

### No constructor body
If body of the constructor is not given, values will be set to corresponding fields.

```ellie
class Test {
    co(x);
    v x : int;
}
```

### Generics

```ellie
class Test<T> {
    co(x);
    v x : T;
}
```

### Constructor body
```ellie
class Test {
    co(x) {
        this.x = x;
    }
    v x : int;
}
```
