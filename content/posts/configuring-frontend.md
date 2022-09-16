---
title: "Frontend Development setups"
date: 2022-07-01T09:49:47+03:00
draft: true
---

## Front end development

## what is esbuild?

### Is Typescript Necessary for frontend development?

### Places where typescript comes handy

### Setting up typescript with frontend frameworks
* [Getting Started with typescript](./typescript.md)

### es-lint

* what is linting?
* es-lint
  `npx eslint --init`  # installs a bunch of dev dependancies(although there are some more useful deps missing like react-hooks, ... ) and adds linting configuration eslintrc.cjs
  there is a flag to use with npm's install command that will make sure it installs all the dependancies the dependancy relies on it is: `npx install-peerdeps --dev eslint-config-airbnb`
    this also will install and extends frameworks linting styles.
* famous/widely used es-lint configurations
  * airbnb overview and configurations
    install using eslint-config-airbnb like so: `npx install-peerdeps --dev eslint-config-airbnb`
    airbnb will override the default eslint:recommended, therefore we should remove that line from the extends section, and add 'airbnb', 'airbnb-typescript'.

    and when it is typescript it also needs to have the location of tsconfig.json. to add it use the parseOptions: {..., project: './tsconfig.json'} otherwise the .ts files will not be compiled to .js

    we should also config, the "include": ["eslintrc.cjs", ...] to the tsconfig.json which will link them together so that the work really well together, when connected.

### Prettier

prettier can be configured to work with eslint,
`npm i -D prettier eslint-config-prettier eslint-plugin-prettier`
this will install prettier and program that let prettier utilize the eslint configs and any plugins installed from eslint.

then prettier should be added to the plugin section of the eslintrc.cjs 

also add the `'plugin:prettier/recommended'` as the last element of extends section, at last because the extended plugins at top might have rules that do not go well with prettiers rules so we want to make sure they pass there requirements first

* configuration
.prettierrc.cjs
```cjs
module.exports = {
    "trailingComma": "es5",
    "tabWidth": 4,
};
```


```YAML
# .prettierrc or prettierrc.yml
trailingComma: "es5"
tabWidth: 4
```

## VITE FOR FRONTEND

## Testing

### Vitest
vitest is just a test runner, if finds test files and run them.

install
`npm install -D vitest`

* configure vitest

1. to create a new viteconfig file
2. because we used vite to scaffold the project, we can use that file to add the test section.

we should also add the vite.config.ts file to include section of tsconfig.json, 

eslint will complain because vite is not a dev dependancy but we want it to be a dev dependancy.

* eslint Extreneous dependancies error, happen when we use the dev dependancies in the code, in our case we need to do so for our test files, therefore we will disable the rule for that specific file. 

### Testing Library

Testing library for a whole bunch of frameworks.

However vitest and testing-library needs a bit more configurations to work together. which is `jest-dom`  

installation:

`npm i -d @testing-library/react`

### What is jsdom

it let us do web like things without a web-browser for testing.

### finally testing

```js
import {describe, it} from 'vitest';
import {render, screen} from '@testing-library/react';

import App from './App';

describe('App', () => {
  it("Renders hello world", () => {
    // The way we typically do testing is by using
    // ARRANGE
    // ACT
    // EXPECT

    // ARRANGE
    render(<App />)

    // ACT
    // will come in to play if we need to interact, like click a button.
    // EXPECT
    expect(screen.getByRole('heading', {
      level: 1,
    })).toHaveTextContent('Hello, World!')
  });
  // testing react-router-dom
  it ("Renders the 404 page"), () => {
    // ARRAGE
    render(
      <MemoryRouter initialEntries={['/nonexisting-page']}>
        {/* We want to give the App not the WrappedApp for the memory router */}
        <App />
      </MemoryRouter>
      // EXPECT
      expect(
        screengetByRole('heading', {level: 1})
        .toHaveTextContent("Go home")
      )
    )
  }
})
```

try to find an element and select it with `getByRole` therefore we can get an accecibility testing and component testing all in one go.
otherwise  getByLabelTest, ... 

try to not use the byId, because that is not how the user will interact with the website.

## React Router
 
we should wrap the App component. with HashRouter or others.
this way we can test the App compoent with the router, instead of the App compoenet being a wrapper for the rest of the page.

the reason for not using BrowserRouter is it uses the `history router` the issue is if deployed to a static web server, the we have to allow 404 to redirect to the index.
but with HashRoute will make sure we can deploy to a static cdn and we don't have to worry about redirect configurations.

make a directory for pages that the top level comp will call.

like a home.tsx and notfound.tsx

```tsx
function Home() {
  return <h1>Hello, World!</h1>
}

export default Home;
```

```tsx
import {Link} from 'react-router-dom';

function NotFound() {
  return (
    <>
      <h1>Page not found !</h1>
      <Link to="/">Go home</Link>
    </>
  )
}

export default Home;
```

```jsx
import {HashRouter, BrowserRouter, Route, Routes } from 'react-router';
import Home from './pages/Home';
import NotFound from './pages/notfound';

function App() {
  return (
    <Rootes>
      <Route path="/" element={Home} />
      {/* this will run if all the above are not found.*/}
      <Route path="*" element={NotFound} />
    </Routes>
  );
}

function WrappedApp() {
  return (
    <HashRouter> {/* this could be a BrowserRouter */}
      <App />
    </HashRouter>
  )
}

export default WrappedApp;
```


the test will still pass for the App.test.tsx
### Seting up Route.


## Editors setup for Frontend development (Vim Vs Code)
