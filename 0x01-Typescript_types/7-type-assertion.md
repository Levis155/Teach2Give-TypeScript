# Type Assertion

Type assertion is another way of telling the TypeScript compiler about the type of value a variable is going to have.

Type assertions in TypeScript allow you to override the inferred type of a variable

Type assertion can be done in the following ways:

## __as__ assertions

The __as__ keyword is the most common way to assert a type.

It tells TypeScript, **"I know this value better than you do."**

The syntax is:

```ts
let value = someValue as Type;
```

In the example below, we will get an error: __Property 'length' does not exist on type 'unknown'__

```ts
let str: unknown = "Hello, World";
let stringLength = str.length; // 'str' is of type unknown
console.log(stringLength);
```

For the code to work, we need to tell TypeScript **"I know better than you do, the type is string"**. We do this by using the as keyword as shown:

```ts
let str: unknown = "Hello, World";
let stringLength = (str as string).length; // 'str' is of type unknown
console.log(stringLength);
```

TypeScript will now treat str as a string, allowing us to safely access .length.

## __as any__

Using __as any__ tuns off TypeScript's type checking, allowing any operation on the value.

**as any should be avoided unless absolutely necessary, as it removes all type safety.**

```ts
let num: unknown = 55;
let something = (num as any).length; // No TypeScript error
```

## __as const__ (making values immutable)

The __as const__ assertion treats a value as a read-only constant, preventing modifications.

```ts
let animals = ["goats", "cows", "cats", "dogs"] as const;
animals.push("chicken");
// Property 'push' does not exist on type 'readonly' ["goats", "cows", "cats", "dogs"]
console.log(animals);
```

When we explicitly type the variables, then as const will have no effect, this is because as const only works when applied to values, not to variables explicitly typed

## Non-Null Assertions (!)

The non-null assertion operator (!) tells TypeScript, **"I guarantee this value is not null or undefined."**

It tells the compiler that a value is not null or undefined, even if its type suggests it could be.

In the example below, since we have declared in the interface that the age property is optional, TypeScript will complain that john.age might be undefined when we try to use it as shown:

```ts
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
}

let john: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 35,
};

if (john.age > 18) {// 'john.age' is possibly 'undefined'
  console.log("John is an adult");
}
```

We can assure TypeScript that john.age is not null or undefined through non-null assertion (!) as shown:

```ts
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
}

let john: Person = {
  firstName: "John",
  lastName: "Doe",
  age: 35,
};

if (john.age! > 18) {
  console.log("John is an adult");
}
```

## __satisfies__ keyword

The __satisfies__ operator checks if a given type satisfies a specific interface.

It ensures that a type has all the required properties and methods of a specific interface, allowing a variable to fit into a definition of a type.

In other words, it ensures that a type has all the required properties and methods of a specific interface.

```ts
interface Person {
  firstName: string;
  lastName: string;
  age?: number;
}

let john = {
  firstName: "John",
  lastName: "Doe",
  age: 35,
} satisfies Person;
```