---
title: "Dev Environment for Svelte"
date: 2022-09-18T10:49:40+03:00
draft: true
---

\#vite \#eslint \#prettier \#eslint:svelte3 \#husky \#lint-staged \#TypeScript
# Development Environment for Svelte Apps

### What is linting and in how many ways can it help us?

*Linters* are tools integrated to editors that understand the programming language and try to help the developer by showing and fixing warnings and errors in realtime, And also help by inforcing to write a more consistent code.

## Creating a Svelte project with vite

this blog uses the `npm` to manage packages.

if you are using VsCode, download the svelte extention. and the go to the settings.json and add the following,

```json
"eslint.validate": [
    // ...,
    "svelte"
],

"eslint.options": {
    "overrideConfig": {
        "parserOptions": {
            "createDefaultProgram": true,
        }
    }
}

```

`npm create vite@latest`

Select Svelte and TypeScript from the cli

then cd into the project and install the dependancies.

## Linting

to install eslint install these dev dependacies.

This will install eslint linter for svelte

`npm install --save-dev eslint eslint-plugin-svelte3`

To make eslint and typescript work together.

`npm install --save-dev @typescript-eslint/parser @typescript-eslint/eslint-plugin`

Installs prettier and make it work with eslint.

`npm install --save-dev prettier eslint-config-prettier eslint-plugin-prettier`

now we need to create eslint config file. to do so

`npm init @eslint/config`

then we have to integrate all the dev packages we intalled to this file for the linting process.

in my case i choose the commonjs `.eslintrc.cjs` file extention.

this is how my configured .eslintrc.cjs file looks like

```js
module.exports = {
    env: {
        browser: true,
        commonjs: true,
        es2021: true,
    },
    extends: [
        "eslint:recommended",
        "plugin:@typescript-eslint/recommended",
        "plugin:@typescript-eslint/recommended-requiring-type-checking",
        "plugin:prettier/recommended",
    ],
    overrides: [
        // this stays the same
        {
            files: ["*.svelte"],
            processor: "svelte3/svelte3",
        },
    ],
    parser: "@typescript-eslint/parser",
    parserOptions: {
        ecmaVersion: "latest",
        // eslint-disable-next-line no-undef
        tsconfigRootDir: __dirname,
        project: ["./tsconfig.json"],
        extraFileExtensions: [".svelte"],
    },
    plugins: ["svelte3", "@typescript-eslint", "prettier"],
    rules: {
        quotes: ["error", "double"],
        semi: ["error", "always"],
    },
    settings: {
        "svelte3/typescript": () => require("typescript"), // pass the TypeScript package to the Svelte plugin
    },
};
```

The `.prettierrc.cjs` file

```js
module.exports = {
    tabWidth: 4,
    semi: true,
    doubleQuote: true,
    trailingComma: "es5",
}
```

Now eslint will pick the prettier file and apply it to the project.
