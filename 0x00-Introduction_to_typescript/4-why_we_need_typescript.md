# Why We need TypeScript

JavaScript has some issues especially in large-scale applications. 

**For instance:**

**JavaScipt allows accessing properties which aren't present in an object**

```js
const triangle = {height: 30, base: 15};
const area = 1/2 * triangle.height * triangle.something; //This in most programming languages throws an error as the property something does not exist. 
```

**output:**
```
NaN
```

## Type Safety (Fewer Runtime Errors)

JavaScript is dynamically typed, meanint type-related errors often appear at runtime. TypeScript catches these errors at compile time, reducing bugs.  

**For instance:**

```js
function add (a, b) {
    return a + b;
};

// This function is expected to work with numbers but nothing is preventing us from passing the string '2' as an argument
console.log(add(3, '2'));
```
**output:**
```
32
```

## Better code readability and maintainability

In large codebases JavaScript's dynamic nature makes it hard to understand what a function expects or returns

**For instance:**

```js
// We do not understand what type of data the function below is expected to add

function add(a, b) {
    return a + b;
}
```

## Enhanced IDE support and AutoCompletion

With TypeScript, editors like VS Code provide:

- Autocomplete and intellisense

- Error checking as you type

- Quick refactoring and navigation boosting developer productivity compared to JavaScript.

## Scalability for large applications

JavaScript works well for small projects but as applications grow it becomes harder to manage in the sense that:

- No type enforcement leads to hidden bugs.

- Developers struggle to understand data structures. TypeScript enforces structure in the code, making collaboration and scaling easier.

## Easier refactoring debugging

Renaming variables, moving functions, and restructuring code is safer in TypeScript because the compiler ensures consistency. **For instance:**

- In JavaScript, renaming a function might break parts of your app.

- In TypeScript, the compiler warns you about all affected places.

## Popularity and industry adoption

Many major companies like Google, Microsoft, Airbnb, etc. use TypeScript for large projects.

- Used in frameworks like Angular, Nest.js, Next.js etc.

- Adopted in backend (node.js) and frontend (React, Vue, Angular)