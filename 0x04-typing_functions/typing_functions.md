# Typing Functions

In TypeScript, functions can be strongly typed to improve code reliability.

Function typing includes:

- Specifying parameter types
- specifying return types
- Using function signatures
- Working with optional and default parameters
- Handling function overloads

## Typing Function Parameters

You can specify the type of each function parameter.

```ts
function add(a: number, b: number) {
  console.log(a + b);
}

add(5, 12);
```

## Typing Return Values

You can specify return types to ensure type safety.

```ts
function add (a: number, b: number): number {
    return a + b;
}

add(5, 9);
```

If a function does not return anything, use _void_.

```ts
function add(a: number, b: number): void {
  console.log(a + b);
}

add(5, 12);
```

## Function Type Signatures

You can define a function type separately and assign it to variables.

```ts
type MathOperation = (a: number, b: number) => number;

const add: MathOperation = function (number1, number2) {
  return number1 + number2;
};
console.log(add(5, 5));

const multiply: MathOperation = function (number1, number2) {
  return number1 * number2;
};
console.log(multiply(5, 5));

const divide: MathOperation = function (number1, number2) {
  return number1 / number2;
};
console.log(divide(5, 5));
```

## Optional and Default Parameters

- **Optional parameters:** Use ? after a parameter name to make it optional.

- **Default parameters:** Assign a default value to the parameters.

**Optional parameter:**

```ts
function greet(name: string, greeting?: string): void {
  if (greeting) {
    console.log(`${greeting} ${name}`);
  } else {
    console.log(`Hello, ${name}`);
  }
}

greet("John");
greet("John", "Howdy");
```

**Note: Required parameters should never follow optional parameters.**

**Default parameter:**

```ts
function greet(name: string, greeting: string = "Hello"): void {
  console.log(`${greeting} ${name}`);
}

greet("John");
greet("John", "Howdy");
```

**Note: Default parameters should always come last**

## Function Overloads

Function overloading allows multiple function signatures with different types.

```ts
function processInput(input: number): void;
function processInput(input: string): void;
function processInput(input: boolean): void;

function processInput(input: number | string | boolean) {
  if (typeof input === "number") {
    console.log(input * 10);
  } else if (typeof input === "string") {
    console.log(input.toUpperCase());
  } else if (typeof input === "boolean") {
    console.log(input);
  }
}

processInput(55);
processInput("hello");
processInput(true);
```

## Rest Parameters

Rest parameters allow passing multiple arguments into a function.

These values are collected into an array which we can type as shown:

```ts
function sum() {
  var numbers = [];
  for (var _i = 0; _i < arguments.length; _i++) {
    numbers[_i] = arguments[_i];
  }
  var total = 0;
  numbers.forEach(function (number) {
    total += number;
  });
  return total;
}
console.log(sum(3, 5));
console.log(sum(3));
console.log(sum(12, 44, 1, 18, 99, 55));
console.log(sum());
```

## Typing Callback Functions

A callback function is a function that is passed as an argument to another function.

We can type callback functions in TypeScript:

**Basic syntax for typing callback functions:**

Use _() => void_ to define a function type (that returns nothing in this case):

```ts
function greet(name: string, callback: () => void): void {
  console.log(`Hello, ${name}`);
  callback();
}

greet("John Doe", function () {
  console.log("Good bye");
});
```

**Callback with a parameter:**

```ts
function greet(name: string, callback: (message: string) => void): void {
  console.log(`Hello ${name}`);
  callback(`You are a great person ${name}`);
}

greet("John Doe", function (message: string) {
  console.log(message);
});
```

The callback receives a string message and logs it.

**Callback that returns a value:**

```ts
function greet(name: string, callback: (message: string) => string): void {
  console.log(`Hello ${name}`);
  callback(`You are a great person ${name}`);
}

greet("John Doe", function (message: string) {
  return message;
});
```