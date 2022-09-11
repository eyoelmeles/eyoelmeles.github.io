---
title: "Getting started with Typescript"
date: 2022-07-01T09:49:47+03:00
draft: true
---

there are about 20 times more StackOverflow question tagged as `JavaScript` than `typescript` all the javascript questions will also apply to typescript.

## What is CoffeeScript

**TODO**

write something about coffeescript and compare it with typescript.

## Typescript syntax

### Type Anotations

:number, :string ... sets the variable with a type.

### Infered Types

by setting the value while initializing a variable, ts will set the type to the assigned values type.

let c = 43;
c = 'stringed' # this is a runtime error. unless specified otherwise.

### Union

using the `|` pipe symbol, we can specify more types for a datastructure.

### Objects and Interfaces

**Interface**
always use the to define objects.
`inteface Person {
    name: string;
    favNumber: number;

}

**Types**
can be used as enums in javascript.
types cannot be re-opened to add new properties vs an interface which is always extendable.

**Duck-Typing** this means if it seems like the interface defined, then it is of that type interface.

### Classes

```js
class Person {
    name: string;
    dog: string;
    favNumber: number;
    constructor(name: string, dogname: string, favNumber: number) {
        this.name = name;
        this.dogName = dogName;
        this.favNumber = favNumber;
    }
}
```

but there are a better ways of doing classes.
```js
// Adding public will clean some code,
// No need to initialize the variables.
// This class is exactly the same as above.
class Person {
    constructor(public name: string, public dogname: string, public favNumber: number) {}
}
```

sometimes classes are used same as interfaces, for creating objects. but classes more and more.

## Typescript Configuratons(tsconfig.json)

* to generate a tsconfig file.
    `npx tsc --init`

* choosing the javascript version
    "compilerOptions": {
        "target": "ESNext",
        "outDir": "./dist", # don't want to upload this file to github. 
    }

* not generating a js file while there is a type errors.
    1 - "strict": true,
        or
    2 - "noEmitOnError": true

### Generics
<T> this basically means a custom types.

```js
function sortItems<T>(items: T[], compareFn:(a: T, b: T) => number): T[] {
    return items.sort(compareFn);
}

const numbers = [42, 3, 77, 13, 104, 82];
const   names = ["CJ", "Trash_Dev", "RyanRoga", "loco86"];

console.log(sortItems(numbers, (a, b) => a -b))
console.log(sortItems(names, (a, b) => a.localCompare(b)))
```

<T = number> # means if you don't specify a type typescript will use number type
we can also use a unions of type.

## typescript with nodejs

* Typescript should be installed as a dev dependancy.
  and this will make the tsc command work in this dir.

* building typescript files

    "scripts": {
        "build": "tsc" # this will generate the js code.
    }

* TSNODE
node doesn't run a ts file.
so we need a ts-note
`npx ts-node example.ts` # this is similar to `tsc example.ts && ./dist/example.js`
