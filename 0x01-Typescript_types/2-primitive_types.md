# Primitive Types

Primitive types in TypeScript are the most basic types that represent simple values and are immutable.

They include **boolean, number, string, undefined,** and **null.**

## Numbers

Numeric values including positive numbers, negative numbers, 0, Infinity, -Infinity and floating point numbers.

Use the _number_ keyword to define number data types in TypeScript:

```ts
const age: number = 23;
const balance: number = 70.5;
```

## Strings

A string is a collection of characters enclosed within double, single quotes, or backticks.

Use the _string_ keyword to define a string data type in TypeScript.

```ts
const username: string = 'Levis';
const emailAddress: string = 'levismbui@gmail.com';
```

## Booleans

Booleans can either be true or false.

Use _boolean_ keyword to define a boolean data type in TypeScript:

```ts
const isRaining: boolean = false;
const isSunny: boolean = true;
```

## null

Null is used when we want to explicitly define something that is empty or non-existent.

Null variables automatically get _any_ data type, which means they can hold values of any data type. To fix this we use the _null_ key word as shown and the variable will never accept any other data type:

```ts
let data: null = null;
```

## Undefined

Undefined is used as a placeholder to mean that a variable has been declared but has not yet been assigned a value but will have a value soon.

It has its own keyword which is _undefined_.