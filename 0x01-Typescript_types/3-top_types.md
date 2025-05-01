# Top Types

In TypeScript, top types are types that can represent any value.

They can accept any value causing a type error.

The tow top types in TypeScript are:

- _any_: The most permissive types.

- _unknown_: A safer alternative to _any_.

## any

The _any_ type allows you to assign any value to a variable and perform any operation on it without TypeScript complaining.

```ts
//because we gave variable myVariable the any type we can assign any type of value to it without Typescript complaining

let myVariable: any = 20;
console.log(myVariable);

myVariable = 'Levis';
console.log(myVariable);

myVariable = {};
console.log(myVariable);

myVariable = [];
console.log(myVariable);

console.log(myVariable.toUpperCase());
```

**JavaScript file:**

```js
var myVariable = 20;
console.log(myVariable);
myVariable = 'Levis';
console.log(myVariable);
myVariable = {};
console.log(myVariable);
myVariable = [];
console.log(myVariable);
console.log(myVariable.toUpperCase());

```

**Output:**

```js
20
Levis
{}
[]
```  

**Avoid using _any_ type most of the time because it disables type checking, making TypeScript useless**

## Unknown

The _unknown_ type is like any but it forces you to check the type before using it.

```ts
let myVar: unknown = 55;
console.log(myVar); 

myVar = 'st'
console.log(myVar);

myVar = [3, 12, 55];
console.log(myVar); 

myVar = {}
console.log(myVar); 

console.log(myVar.toUpperCase()); // Here TypeScript throws the error: myVar is of type unknown
```

To check the value we can do the following:

```ts
let myVar: unknown = 'Levis';

if(typeof (myVar === 'string')) {
    console.log(myVar.toUpperCase());
}
```

**JavaScript file:**

```js
var myVar = 'Levis';
//check the type of myVar 
if (typeof (myVar) === 'string') {
    console.log(myVar.toUpperCase());
};

```

**Output:**

```
LEVIS
```