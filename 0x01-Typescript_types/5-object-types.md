# Object Types

In TypeScript, object types define the shape of complex values.

The most common object types include:

1. **Interface** - Defines a shape for an object structure.

1. **Class** - Defines blueprints for creating objects.

1. **Enum** - Represents a set of named constant values.

1. **Array** - Represents a collection of elements that are of the same type.

1. **Tuple** - Represents an ordered list of elements with fixed types and lengths.


## Interface

An interface defines the structure of an object.

It type checks objects and enforces consistency.

**For instance:**

```ts
interface Person {
  name: string;
  age: number;
  address?: string; // Optional property
}

function greet(person: Person): string {
  return `Hello, ${person.name}!`;
}

const user: Person = {
  name: "Alice",
  age: 30
};

console.log(greet(user)); 

```

**JavaScript code:**

```js
function greet(person) {
    return "Hello, ".concat(person.name, "!");
}
var user = {
    name: "Alice",
    age: 30
};
console.log(greet(user));

```

### Optional properties for interface

We can use _?_ to show optional properties.

In the example above, **address** property is optional.

### Readonly properties for interfaces

The _readonly_ keyword is used for properties that should not be modified.

**Example:**

```ts
interface User {
  firstName: string;
  lastName: string;
  age: number;
  readonly isAdmin: boolean;
}

const levis: User = {
  firstName: 'Levis',
  lastName: 'Mbui',
  age: 23,
  isAdmin: false //variable isAdmin is not successfully assigned because it is read-only
}
```

### Extending interfaces

Extending interfaces means creating a new interface that inherits properties from an existing one, allowing for reuse.

To achieve this, the _extends_ keyword is used.

```ts
interface user {
  firstName: string;
  lastName: string;
  age: number;
  isAdmin: boolean;
}

interface Employee extends user{
  employeeId: string;
  department: string;
  role: string;
}

var jane: Employee = {
  firstName: 'Jane',
  lastName: 'Doe',
  age: 20,
  isAdmin: false,
  employeeId: '293894',
  department: 'finance',  
  role: 'assistant',
}

console.log(jane);
```

## Class

A class is a blueprint for creating objects with properties and methods.

When creating a class in TypeScript, we start by defining the properties then initialize those properties in the constructor function.

```ts
class User {
  firstName: string;
  lastName: string;
  age: number;

  constructor(firstName: string, lastName: string, age: number) {
    this.firstName = firstName;
    this.lastName = lastName;
    this.age = age;
  }

  printInformation() {
    console.log(`My name is ${this.firstName} ${this.lastName}. I am ${this.age} years old`,);
  }
}

const john: User = new User("John", "Doe", 35);
john.printInformation();
```

## Enum

An enum is a special type that defines a set of named constants.

Enums help prevent invalid values and ensure consistency.

There are two types of enums:

- Numeric enums
- String enums

### Numeric Enums

Numeric enums in TypeScript assign numerical values to their members, starting from 0 with subsequent numbers auto-incrementing.

```ts
enum ShoeSize {
  Small, // 8
  Medium, // 9
  Large, // 10
  ExtraLarge, // 11
}

console.log(ShoeSize.Small); // 0
console.log(ShoeSize.ExtraLarge); // 3

let boughtShoeSize: ShoeSize = 0;

if (boughtShoeSize === ShoeSize.Small) {
  console.log(`Pay $5`);
}
```

Numeric enums start from 0 and the rest of the elements automatically increment by 1, we can change the starting point as shown:

```ts
enum ShoeSize {
  Small = 100,
  Medium,
  Large,
  ExtraLarge,
}

console.log(ShoeSize.Small); // 100
console.log(ShoeSize.Medium); // 101
console.log(ShoeSize.Large); // 102
console.log(ShoeSize.ExtraLarge); // 103
```

We can also set completely custom integer values as shown:

```ts
enum ShoeSize {
  Small = 100,
  Medium = 200,
  Large = 300,
  ExtraLarge = 400,
}

console.log(ShoeSize.Small); // 100
console.log(ShoeSize.Medium); // 200
console.log(ShoeSize.Large); // 300
console.log(ShoeSize.ExtraLarge); // 400
```

### String Enums

String enums in TypeScript assign string values to their members explicitly, ensuring each member holds a unique string value.

```ts
enum ShoeSize {
  Small = "Small",
  Medium = "Medium",
  Large = "Large",
  ExtraLarge = "ExtraLarge",
}

console.log(ShoeSize.Small); // Small
console.log(ShoeSize.Medium); // Medium
console.log(ShoeSize.Large); // Large
console.log(ShoeSize.ExtraLarge); // ExtraLarge
```

## Array

An array is a collection of elements that have the same type.

```ts
let luckyNumbers: number[] = [12, 4, 7, 14, 35]
console.log(luckyNumbers)
```

If you want your array to hold items of various data types, you can specify these data types using the **union type**.

```ts
let myArray : (string | number | boolean)[] = ["cat", true, 7, "dog", false];
console.log(myArray);
```

## Tuple

A tuple is a special kind of array with fixed types and a fixed number of elements.

```ts
const myArray:[string, number] = ["Messi", 10];
console.log(myArray);
```

### Named Tuples

Named tuples in TypeScript allow you to give labels to tuple elements, improving readability and maintainability.

E.g.

**compare:**

```ts
const border: [string, string, string] = ["1px", "solid", "white"];
```

**with:**

```ts
const border: [width: string, style: string, color: string] = ["1px", "solid", "white"];
```

### Tuples with optional elements

To specify that an element of a tuple is optional, use ?.

```ts
const border: [string, string, string?] = ["1px", "solid"];
```

For name tuples:

```ts
const border: [width: string, style: string, color?: string] = ["1px", "solid"];
```
