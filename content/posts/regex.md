---
title: "REGEX notes"
date: 2022-09-01T09:49:47+03:00
draft: false
---

# Getting started with Regular Expression/REGEX

## Pronounced as Regex or rejex?

probably is the most dificult thing to answer, But i will go with _Regex_ as it stands for **Reguar Expression**

### Why use Regex?

1. Validate Text
2. Search through text

builtin functions in js to write regex

- `match()` - search for a matching patern
- `replace()` - replace that maching patterns

Regex strings starts and ends with `/` and if there is extra information needed, we can use regex flags after the ending `/`
like this `//g` the `g` here is a flag

### Special Regex Characters

These are all the Special characters.

`.^&*+-?()[]{}\|`

- `|` logical OR

- `()` Grouping

  quantifiers

      `?` - 0 or 1 times

      `*` - 0 or multiple times

      `+` - 1 or multiple times

  by adding braces `{}` we can give them explicit count.

  `?r{2,6}`

- `\` escape a special characters

  `\d` to escape digits

  `\w` to escape words

  `\D` to escape neither digits nor words

- `[]` Ranging

- `^` Negation, do the opposite

### Flags

are written at the right side of the `/` like so `//g`
The `g` flat turns it into a global, which will make it search for _multiple matches_

visit [regexr.com](regexr.com) for more.
it has amazing cheatsheet and traning area.
