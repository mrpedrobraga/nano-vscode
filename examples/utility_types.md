# Utility types

Let's say we have an object

```nano
const MyType = struct {
    a: int
    b: int
}
```

## Member Types

```nano
const MyTypeFirstMember = MyType.a
#        ^? int
```

## Map Types

```nano
const Partial<T> = T {}|> (_ | exclude)

const MyTypeUpdate = Partial<MyType>
#        ^? {a: int | exclude, b: int | exclude}

const AllRequired<T> = T {}|> (_ - exclude)

const MyTypeUpdateAll = AllRequired<MyTypeUpdate>
#        ^? {a: int, b: int}
# This is just the original "MyType," lol.
```

## Literal Types

```nano
const NumberType = typeof 3
const Three = type : 3
```
