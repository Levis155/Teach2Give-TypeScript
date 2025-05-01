# TypeScript Setup

- To install TypeScript, we need npm which comes bundled with node.js. To verify whether you have node.js:

```
node --version
```

If the command returns a version number, then node.js is installed.

**npm comes bundled with node** so you can now install typescript with npm.

- To **install TypeScript globally** we run the command:

```console
npm install -g typescript
```

- After the intallation, **verify that TypeScript is installed** by checking its version:

```
tsc -v
```

- To **initialize a TypeScript project**, navigate to your project directory and run:

```
tsc --init
```

or 

```
npx tsc --init
```

This generates **tsconfig.json** file which contains configuration options for your TypeScript project. You can modify this file based on your project needs.

## First TypeScript code

Inside the project directory create the file **hello.ts** with the following code:

```ts
let age: number = 55;
console.log(age)
```

To execute the code above **we need to convert it to JavaScript code first and then execute the generated JavaScript code**.

To do this navigate to where hello.ts lives and run the command:

```
tsc hello.ts
```

This generates **hello.js** with the following code:

```js
var age = 55;
console.log(age);
```

We can then execute this Js file with node or view its output in the browser.