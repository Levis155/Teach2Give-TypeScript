# Combining Types

TypeScript provides several ways to combine and manipulate types, allowing for more flexibility and code reuse.

The key techniques include:

- Union Types
- Type aliases
- Intersection Types
- The __keyof__ operator

## Union ( | )

Union types are used when a value can be more than a single type.

It means either one type or another.

E.g.:

```ts
let myVariable: string | number;

myVariable = "Hello, World!"; // valid
myVariable = 44; // valid
myVariable = false; // invalid
```

## Type Aliases (type)

A type alias gives a custom name to a type, making complex types easier to read and reuse.

Type aliases use the type keyword.

```ts
type idNumber = string | number;

let userId: idNumber = 7485748; //valid
let otherUserId: idNumber = "HFDJHF22" // valid
```

We can also use Type alias with objects:

```ts
type User = {
    firstName: string;
    lastName: string;
    age: number
}

const john: User = {
    firstName: "John",
    lastName: "Doe",
    age: 23
};
```

## Intersection Types (&)

An intersection type combines multiple types into one, meaning the variable must satisfy all types.

Intersection types allow you to combine multiple types into one.

This means that the resulting type will have all the properties of the intersected types.

You can create an intersection type using the & operator.

For instance if you have two interfaces: Person and PersonDetails, and you want to create a new type that includes properties from both:

```ts
interface Person {
  firstName: string;
  lastName: string;
}

interface PersonDetails {
  location: string;
  email: string;
  phoneNumber: string;
}

type Employee = Person & PersonDetails;

const john: Employee = {
  firstName: "John",
  lastName: "Doe",
  location: "Fake ST",
  email: "John@gmail.com",
  phoneNumber: "+234023849453",
};

console.log(john);
```

## keyof Operator

keyof is a keyword in TypeScript that is used to extract the key type from an object type.

It allows you to extract the keys of an object type as a union of string or numeric literal types.

```ts
interface Person {
    firstName: string;
    lastName:string;
    age: number;
}

type Keys = keyof Person;

let a: Keys = "firstName";
let b: Keys = "lastName";
let c: Keys = "age";
```