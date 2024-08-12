---
title: 'Getting started with TypeScript'
date: 2022-07-01T05:38:16+03:00
draft: true
---

## What is TypeScript?

TypeScript is an additional syntax added to JavaScript to add rules to the code, which ultimately will make the development process easy and most importantly catch runtime errors

Specially useful for a big scale projects as TypeScript make the code less proned to errors and have no unwanted behaviors.

TypeScript is a superset of JavaScript, meaning any valid JavaScript can be considered as a TypeScript

## What is CoffeeScript?

_Coffeescript_ a program that takes a .coffee files and returns the JavaScript equivalent. It takes inspirations from `python`, `haskal` but mostly `ruby` to make the developement expreriance familiar for people comming from these programming langugages, And also to make the code _readable_ by _reducing code_ and sharing _easy syntaxes_ from these languages.

there is _no interpretation_ at runtime, everything get turned into a one-to-one equivalent of its JavaScript.

`if`, `switch`, and `for` all have to _return a value_

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

Personally i think JavaScript have come far enough to be used in a more comfortable and relatable way as any other programming languages, specially with TypeScript it crosses off most of our essentials for programming language. therefore there is no need for writing a coffescript.

## Getting Started With TypeScript

!disclamer, This blog is only about TypeScript concept and syntax. [Click here]() to see how to set up a Web development enviroment with TypeScript.

Here are some important concepts to understand about TypeScript

### Type Anotations

One of the most important tool that JavaScript lacks is _Types_. that is why we have TypeScript and it got its name from it.

JavaScript's primitive values and their type definations

We can use the Type number, string, undefined and null for JavaScript primitive data types.
By providing a type to a variable we can give it the object wrapper we need and that will make writing code easier.

for more complex data structures we have more options.

### Arrays

Two ways of Type anotation for an Array

1. using TypeScript we can create an array as a tupple.
   This way we can create an array with a different type elements inside of it.

   ```ts
   const message: [number, string, string] = [
     1,
     'Message 01',
     '2022-4-2 12:43pm',
   ];
   ```

2. we can make Array with the same type element.

   ```ts
   const messages: string[];
   ```

### Objects and Interfaces

- Objects (pretty much everything else is an object in JavaScript)
  There are several ways to type an object as well.

  1. ### Interface

     More prefered to use interface to define objects.
     interface is quite similar to types we can use both to define object, but interface will only care about the structure of the
     object being instanciated, it checks weather it satisfies the types required. it doesn't try to be and store types like a type alias.
     The only main differnce between interface and type is that we can _extend interfaces_, but not types.

     TypeScript assumes _duck typing_ for an interface.

     _Duck-Typing_ means if it seems like the interface defined, then it is of that interface type, or in a better words

     > if it walk like a duck and quacks like a duck then it must be a duck.

  2. ### Type
     Types and Interfaces are almost the same thing, and can be used interchangably for object types
     however the key difference between them is that Types. it is called type because we are trying to
     combine types to make one big custom type. so this basically is like using union to combine types,
     however the difference between them is that sometimes we would want to use the same type multiple times
     in one group, this is where type comes in. the other benefit to using type is _naming_. we get even name unions.
     therefore it in core is just an alias, a way of naming multiple types.

### Infered Types

By setting the value while initializing a variable, TypeScript will set the type to the assigned values type.

there are also _literal types_ which takes the value of the variable as a type.
example could be

```ts
// This two are the same, because constant can not change,
// the type in this case is a string Eyoel.
const name = 'Eyoel';
// const name: "Eyoel" = "Eyoel";
```

this is useful, because sometimes we want to specify what kind of string value we want to accept

### Union

using the `|` pipe symbol, we can specify more types options.

### Classes

Most JavaScript/TypeScript projects are done using a functional prgramming paradigm but JavaScript provides a OOP programming approach as well, and TypeScript can help a lot.

By just using the access modifiers we can shorten the class.

```js
// class Animal {
//     name: string;
//     type: string;
//     leg: number;
//     constructor(name: string, type: string, leg: number) {
//         this.name = name;
//         this.type = type;
//         this.leg = leg;
//     }
// }

// Adding public will clean some code,
// No need to initialize the variables.
// This class is exactly the same as above.
class Animal {
    constructor(public name: string, public type: string, public leg: number) {}
}
```

Additional types

- `as`

  is a TypeScript syntax not a type but it means use this variable/function as a type we provided, meaning telling the let variables to be of a specific type when they get assigned a value later. as can be viewed as _casting_.

- `any`

  if we don't know what type it is then by using any it can be anything. we can get away with a lot of stuff, but also we can't get any type completion.

- `unknown`

  If we specify var as unknown then we can't use it anywhere

  - this could be useful to tell a fuction to return anything(thus the name unknown) and you don't have to write any to the function.

  - the other use of unknown is to use it in conjuction with `as`, we can not turn a variable that the ts compiler know as a string to be a number, but we can turn it into unknown and then turn it into a number. however this is dangerous and may run into a runtime error for using a number methods on a string that turned into a number or any casting

- `never`
  If we have specified all the posible types for a union, they when iteration through this union typed data it could only be of those union type it can never be anything else(thus the name never). it basically means this type will never happen, meaning this thing should never ever happen so we can set its type to be never.

### Generics

Generic is a type to be specified later, we use it as a variable or placeholder for the type which comes later.

```js
function sortItems<T>(items: T[], compareFn: (a: T, b: T) => number): T[] {
  return items.sort(compareFn);
}

const numbers = [42, 3, 77, 13, 104, 82];
const names = ['CJ', 'Trash_Dev', 'RyanRoga', 'loco86'];

console.log(sortItems(numbers, (a, b) => a - b));
console.log(sortItems(names, (a, b) => a.localCompare(b)));
```

`<T = number>` means if you don't specify a type TypeScript will use number type
we can also use a unions of type.

## Writing Code TypeScript won't allow.

we can write a JavaScript code inside a TypeScript file and it will work just fine, But we also have a power to write a code that TypeScript assumes is wrong and tell TypeScript to skip checking for weather it is correct or not.

```ts
// @ts-ignore - will ignore all the ts configurations, and be JavaScript. We can also specify rules
// @ts-nocheck - written in the top of the file and the file is JavaScript
```
