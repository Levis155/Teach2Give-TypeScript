# Bottom Types

In TypeScript, a bottom type is a type that represents a value that never exists.

The only bottom type in TypeScript in **_never_**, which is a type that represents values that never occur.

It is used in situations where a value can never be observed.

This usually happens in:

- Functions that never return (e.g. infinite loops and errors)

- Exhaustive switch-case handling

- Unreachable code.