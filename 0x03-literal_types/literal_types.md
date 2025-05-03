# Literal Types

Literal Types allow a variable to have a specific string, number, or boolean value instead of general types.

```ts
type Status = "success" | "error" | "loading";

let state: Status = "success";
let state: Status = "error";
let state: Status = "loading";
let state: Status = "pending"; // will not work
```

# Template literal types

These allow us to construct new types using template literals, similar to JavaScript string templates.

```ts
type Shade = "dark" | "light";
type Color = "red" | "green";

type ColorShade = `${Shade}-${Color}`;
// "dark-red" | "dark-blue" | "light-red" | "light-blue"

let color: ColorShade = "light-green";
console.log(color);
```