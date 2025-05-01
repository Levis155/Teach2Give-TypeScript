# Type Inference

Type inference in TypeScript is the ability of the compiler to automatically determining the type of a variable based on its assigned value, without explicitly specifying the type.

**For instance:**

```ts
let message = "Hello world!"; //inferred as a string
let count = 3; //inferred as a number
```

Since message is assigned as a string, TypeScript infers its type as string, preventing accidental assignment of other types later.

```ts
let message = "Hello world!"; //inferred as a string
let count = 3; //inferred as a number

message = 5; //Error: Type number is not assignable to type 'string'
count = "Good morning!" // Error: Type 'string' is not assignable to type 'number'
```