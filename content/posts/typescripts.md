---
title: 'Typescript'
date: 2022-07-01T05:38:16+03:00
draft: true
---

![TypeScript banner from fedojo.com](https://fedojo.com/wp-content/uploads/2019/05/typescript.png)

This is a custom typescript doc!

## Table of Content

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Links](#links)
- [Getting Started](#Getting-Started)
  - [Basics](#Basics)
  - [Useful resources](#useful-resources)
  - [Examples Built with Typescript](#Examples-Built-With-Typescript)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

The one half famous javascript superset that doesn't make it though

[Coffeescript](./coffeescript)

## What is Typescript

It is a superset of javascript meaning, the existing javascript code is already a typescript code,

## Basics

How do we get the types

javascript without using typescript knows what the type of a variable is if it is instantiated with a value

example
`let name= "Eyoel";`
javascript knows the type of the variable `name` is `string` we can check it by using the typeof keyword. `typeof name` would return a string.

typescript would let us utilize this feature of javascript to make sure we can explicitly declare it as a string,
example
`let name: string = "Eyoel"` or without having to initialize it without data `let name: string;`
here just as the first example, we are using a variable `name` with a typeof string. but we are explicitly telling it to be a string, this will inforce the variable to only accept `string` as value for `name`

therefore typescript in a way is forcing our code to only work with some types, this is why it is typescript, as it focuses on types.

Now for the big question **what is Type**?

assuming we know javascript.

javascript has 7 primitive types.
number, string, boolean, object, undefined, symbol, none.

well some might think this is all it is, typescript is just assinging types to variables. but typescript offers more to our coding experiences.

first let's take sometime with the primitive types and then we go more to the intermidiate to advanced topics.
