---
title: "Getting started with TypeScript"
date: 2022-07-01T09:49:47+03:00
draft: true
---

![TypeScript banner from treehouse.com](http://blog.teamtreehouse.com/wp-content/uploads/2015/05/typescript.png)

## What is TypeScript?

TypeScript is an additional syntax added to JavaScript to add rules to the code, which ultimately will make the development process easy and most importantly catch runtime errors

Specially useful for a big scale projects as TypeScript make the code less proned to errors and unwanted behaviors.

TypeScript is a superset of JavaScript, meaning any valid JavaScript can be considered as a TypeScript

## What is CoffeeScript?

*Coffeescript* a program that takes a .coffee files and returns the JavaScript equivalent. It takes inspirations from `python` `haskal` but mostly `ruby` to make the developement expreriance familiar for people comming from these programming langugages, And also to make the code *readable* by *reducing code* and sharing *easy syntaxes* from these languages.

there is *no interpretation* at runtime, everything get turned into a one-to-one equivalent JavaScript.


`if` `switch` `for` all have to `return a value`

functions are created with the skinny arrow sytax
and we use haskal/yaml like indentations to create blocks of code

```coffee
    console.log car for car in ['Mercedes', 'McLaren', 'Ferrari']
```

this will translate to

```js
var car, i, len,  ref;
ref = ['Mercedes', 'McLaren', 'Ferrari'];
for (i = 0; len = ref.length; i < len; i++) {
    car = ref[i];
    console.log(car);
}
```

### Getting Started with CoffeeScript

```bash
# Installing CoffeeScript from npm

npm i -g coffeescript
# Translating .coffee file to js
# without -c flag there will be no js file

npx coffee -c index.coffee
```

Personally i think JavaScript have come far enough to be used in a more comfortable and relatable way as any other programming languages, specially we with typescript it crosses off most of our essentials for programming language. therefore there is no need for writing a coffescript.

## Getting Started With TypeScript

!disclamer, This blog is only about TypeScript concept and syntax does not talk about setting it up. [Click here]() to see how to set up a Web Development enviroment with typescript.

Important concepts to understand about TypeScript are the following

### Type Anotations

One of the most important tool that JavaScript lacks is *Types*. that is why we have TypeScript and it got its name.

JavaScript premitive values and their type definations


- Numbers
  
  number (floats, int, double) all are just a number type.
- Strings
  
  all the single or double quoted values.

- BigInt
- Symbols
- nulll and undefined

Non-Primitive data types

- Array
    
    1. using TypeScript we can create an array as a tupple.
        This way we can create an array with a different type elements inside of it.
        ```ts
        const message: [int, string, string] = [1, "Message 01", "2022-4-2 12:43pm"]
        ```
    2. we can make Array with the same type element.
        ```ts
        const messages: string[];
        ```
- Objects
    
    There are several ways to type an object as well.
    1. Interface
        We usually use interfaces to define object types.
    2. Type
    3. Class

    Pretty much everything else is just an object.

by providing a type to a variable we can give it the object wrapper we need and that will make writing codes easier.


types can be writen in snake case like so Number or number

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
can be used as enums in JavaScript.
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

## TypeScript Configuratons(tsconfig.json)

* to generate a tsconfig file.
    `npx tsc --init`

* choosing the JavaScript version
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

* TypeScript should be installed as a dev dependancy.
  and this will make the tsc command work in this dir.

* building typescript files

    "scripts": {
        "build": "tsc" # this will generate the js code.
    }

* TSNODE
node doesn't run a ts file.
so we need a ts-note
`npx ts-node example.ts` # this is similar to `tsc example.ts && ./dist/example.js`

## Telling TypeScript we know better that it.

* `as` keyword -> this basically means use this variable/function as a type we provided, meaning telling the let variables to be of a specific type when they get assigned a value later. as can basically be taken as casting.

* `any` if we don't know what type it is then by using as it can be anything. we can get away with a lot of stuff, but also we can't get any type completion
But if it is
* `unknown` if we speciify var as unknown then we can't use it anywhere

  * this could be useful to tell a fuction to return anything(thus unknown) and you don't have to write any to the function.
  
  * the other use of unknown is to use it with conjuction with as, we can not turn a variable that the ts compiler know as a string to be a number, but we can turn it into unknown and then finally turn it into a number. however this is dangerous and my run into a runtime error for using a number methods on a string that turned into a number or any casting

* `never` if we have specified all the posible types for a union, they when iteration through this union typed data it could only be of those union type it can never be anything else(thus the name never). it basically means this type will never happen, meaning this thing should never ever happen so we can set its type to be never, example in doc says if we are switching based on their types in the union then the default case should have nothing that can happen, meaning they can anythiing in the switch cases can only be of those types, otherwise it will never happens
  
### Commenting out typescript to ignore certain things

```ts
// @ts-ignore - will ignore all the ts configurations, and be JavaScript
// @ts-nocheck - written in the top of the file and the file is JavaScript
```
