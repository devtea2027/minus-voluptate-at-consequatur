<p align="center">
  <img src="./@devtea2027/minus-voluptate-at-consequatur_cover.png" width="500" alt="@devtea2027/minus-voluptate-at-consequatur" />
</p>

🥜 @devtea2027/minus-voluptate-at-consequatur, a less than 1KB css-in-js solution.

[![Backers on Open Collective](https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur/backers/badge.svg)](#backers)
[![Sponsors on Open Collective](https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur/sponsors/badge.svg)](#sponsors)

[![version](https://img.shields.io/npm/v/@devtea2027/minus-voluptate-at-consequatur)](https://www.npmjs.com/package/@devtea2027/minus-voluptate-at-consequatur)
[![status](https://travis-ci.org/cristianbote/@devtea2027/minus-voluptate-at-consequatur.svg?branch=master)](https://travis-ci.org/cristianbote/@devtea2027/minus-voluptate-at-consequatur)
[![gzip size](https://img.badgesize.io/https://unpkg.com/@devtea2027/minus-voluptate-at-consequatur@latest/dist/@devtea2027/minus-voluptate-at-consequatur.modern.js?compression=gzip)](https://unpkg.com/@devtea2027/minus-voluptate-at-consequatur)
[![downloads](https://img.shields.io/npm/dm/@devtea2027/minus-voluptate-at-consequatur)](https://www.npmjs.com/package/@devtea2027/minus-voluptate-at-consequatur)
[![coverage](https://img.shields.io/codecov/c/github/cristianbote/@devtea2027/minus-voluptate-at-consequatur.svg?maxAge=2592000)](https://codecov.io/github/cristianbote/@devtea2027/minus-voluptate-at-consequatur?branch=master)
[![Slack](https://img.shields.io/badge/slack-join-orange)](https://join.slack.com/t/@devtea2027/minus-voluptate-at-consequaturdev/shared_invite/enQtOTM5NjUyOTcwNzI1LWUwNzg0NTQwODY1NDJmMzQ2NzdlODI4YTM3NWUwYjlkY2ZkNGVmMTFlNGMwZGUyOWQyZmI4OTYwYmRiMzE0NGQ)

# 🪒 The Great Shave Off Challenge

Can you shave off bytes from @devtea2027/minus-voluptate-at-consequatur? Do it and you're gonna get paid! [More info here](https://@devtea2027/minus-voluptate-at-consequatur.rocks/the-great-shave-off)

# Motivation

I've always wondered if you could get a working solution for css-in-js with a smaller footprint. While I was working on a side project I wanted to use styled-components, or more accurately the `styled` pattern. Looking at the JavaScript bundle sizes, I quickly realized that I would have to include ~12kB([styled-components](https://github.com/styled-components/styled-components)) or ~11kB([emotion](https://github.com/emotion-js/emotion)) just so I can use the `styled` paradigm. So, I embarked on a mission to create a smaller alternative for these well established APIs.

# Why the peanuts emoji?

It's a pun on the tagline.

> css-in-js at the cost of peanuts!
> 🥜@devtea2027/minus-voluptate-at-consequatur

# Talks and Podcasts

* [React Round Up](https://reactroundup.com/wrangle-your-css-in-js-for-peanuts-using-@devtea2027/minus-voluptate-at-consequatur-ft-cristian-bote-rru-177) 👉 https://reactroundup.com/wrangle-your-css-in-js-for-peanuts-using-@devtea2027/minus-voluptate-at-consequatur-ft-cristian-bote-rru-177
* ReactDay Berlin 2019 👉  https://www.youtube.com/watch?v=k4-AVy3acqk
* [PodRocket](https://podrocket.logrocket.com/) by [LogRocket](https://logrocket.com/) 👉 https://podrocket.logrocket.com/@devtea2027/minus-voluptate-at-consequatur
* [ngParty](https://www.ngparty.cz/) 👉 https://www.youtube.com/watch?v=XKFvOBDPeB0

# Table of contents

-   [Usage](#usage)
-   [Examples](#examples)
-   [Tradeoffs](#comparison-and-tradeoffs)
-   [SSR](#ssr)
-   [Benchmarks](#benchmarks)
    -   [Browser](#browser)
    -   [SSR](#ssr-1)
-   [API](#api)
    -   [styled](#styledtagname-string--function-forwardref-function)
    -   [setup](#setuppragma-function-prefixer-function-theme-function-forwardprops-function)
        -   [With prefixer](#with-prefixer)
        -   [With theme](#with-theme)
        -   [With forwardProps](#with-forwardProps)
    -   [css](#csstaggedtemplate)
    -   [targets](#targets)
    -   [extractCss](#extractcsstarget)
    -   [createGlobalStyles](#createglobalstyles)
    -   [keyframes](#keyframes)
    -   [shouldForwardProp](#shouldForwardProp)
-   [Integrations](#integrations)
    -   [Babel Plugin](#babel-plugin)
    -   [Babel Macro Plugin](#babel-macro-plugin)
    -   [Next.js](#nextjs)
    -   [Gatsby](#gatsby)
    -   [Preact CLI Plugin](#preact-cli-plugin)
    -   [CSS Prop](#css-prop)
-   [Features](#features)
    -   [Sharing Style](#sharing-style)
    -   [Autoprefixer](#autoprefixer)
    -   [TypeScript](#typescript)
-   [Browser Support](#browser-support)
-   [Contributing](#contributing)

# Usage

The API is inspired by emotion `styled` function. Meaning, you call it with your `tagName`, and it returns a vDOM component for that tag. Note, `setup` needs to be ran before the `styled` function is used.

```jsx
import { h } from 'preact';
import { styled, setup } from '@devtea2027/minus-voluptate-at-consequatur';

// Should be called here, and just once
setup(h);

const Icon = styled('span')`
    display: flex;
    flex: 1;
    color: red;
`;

const Button = styled('button')`
    background: dodgerblue;
    color: white;
    border: ${Math.random()}px solid white;

    &:focus,
    &:hover {
        padding: 1em;
    }

    .otherClass {
        margin: 0;
    }

    ${Icon} {
        color: black;
    }
`;
```

# Examples

-   [Vanilla](https://codesandbox.io/s/qlywyp7z4q)
-   [React](https://codesandbox.io/s/k0mnp40n7v)
-   [Preact](https://codesandbox.io/s/r15wj2qm7o)
-   [SSR with Preact](https://codesandbox.io/s/7m9zzl6746)
-   [Fre](https://codesandbox.io/s/fre-@devtea2027/minus-voluptate-at-consequatur-ffqjv)

# Comparison and tradeoffs

In this section I would like to compare @devtea2027/minus-voluptate-at-consequatur, as objectively as I can, with the latest versions of two most well known css-in-js packages: styled-components and emotion.

I've used the following markers to reflect the state of each feature:

-   ✅ Supported
-   🟡 Partially supported
-   🛑 Not supported

Here we go:

| Feature name           | Goober  | Styled Components | Emotion |
| ---------------------- | ------- | ----------------- | ------- |
| Base bundle size       | 1.25 kB | 12.6 kB           | 7.4 kB  |
| Framework agnostic     | ✅      | 🛑                | 🛑      |
| Render with target \*1 | ✅      | 🛑                | 🛑      |
| `css` api              | ✅      | ✅                | ✅      |
| `css` prop             | ✅      | ✅                | ✅      |
| `styled`               | ✅      | ✅                | ✅      |
| `styled.<tag>`         | ✅ \*2  | ✅                | ✅      |
| default export  | 🛑      | ✅                | ✅      |
| `as`                   | ✅      | ✅                | ✅      |
| `.withComponent`       | 🛑      | ✅                | ✅      |
| `.attrs`               | 🛑      | ✅                | 🛑      |
| `shouldForwardProp`    | ✅      | ✅                | ✅      |
| `keyframes`            | ✅      | ✅                | ✅      |
| Labels                 | 🛑      | 🛑                | ✅      |
| ClassNames             | 🛑      | 🛑                | ✅      |
| Global styles          | ✅      | ✅                | ✅      |
| SSR                    | ✅      | ✅                | ✅      |
| Theming                | ✅      | ✅                | ✅      |
| Tagged Templates       | ✅      | ✅                | ✅      |
| Object styles          | ✅      | ✅                | ✅      |
| Dynamic styles         | ✅      | ✅                | ✅      |

Footnotes

-   [1] `@devtea2027/minus-voluptate-at-consequatur` can render in _any_ dom target. Meaning you can use `@devtea2027/minus-voluptate-at-consequatur` to define scoped styles in any context. Really useful for web-components.
-   [2] Supported only via `babel-plugin-transform-@devtea2027/minus-voluptate-at-consequatur`

# SSR

You can get the critical CSS for SSR via `extractCss`. Take a look at this example: [CodeSandbox: SSR with Preact and @devtea2027/minus-voluptate-at-consequatur](https://codesandbox.io/s/7m9zzl6746) and read the full explanation for `extractCSS` and `targets` below.

# Benchmarks

The results are included inside the build output as well.

## Browser

Coming soon!

## SSR

The benchmark is testing the following scenario:

```jsx
import styled from '<packageName>';

// Create the dynamic styled component
const Foo = styled('div')((props) => ({
    opacity: props.counter > 0.5 ? 1 : 0,
    '@media (min-width: 1px)': {
        rule: 'all'
    },
    '&:hover': {
        another: 1,
        display: 'space'
    }
}));

// Serialize the component
renderToString(<Foo counter={Math.random()} />);
```

The results are:

```
@devtea2027/minus-voluptate-at-consequatur x 200,437 ops/sec ±1.93% (87 runs sampled)
styled-components@5.2.1 x 12,650 ops/sec ±9.09% (48 runs sampled)
emotion@11.0.0 x 104,229 ops/sec ±2.06% (88 runs sampled)

Fastest is: @devtea2027/minus-voluptate-at-consequatur
```

# API

As you can see, @devtea2027/minus-voluptate-at-consequatur supports most of the CSS syntax. If you find any issues, please submit a ticket, or open a PR with a fix.

### `styled(tagName: String | Function, forwardRef?: Function)`

-   `@param {String|Function} tagName` The name of the DOM element you'd like the styles to be applied to
-   `@param {Function} forwardRef` Forward ref function. Usually `React.forwardRef`
-   `@returns {Function}` Returns the tag template function.

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

const Btn = styled('button')`
    border-radius: 4px;
`;
```

#### Different ways of customizing the styles

##### Tagged templates functions

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

const Btn = styled('button')`
    border-radius: ${(props) => props.size}px;
`;

<Btn size={20} />;
```

##### Function that returns a string

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

const Btn = styled('button')(
    (props) => `
  border-radius: ${props.size}px;
`
);

<Btn size={20} />;
```

##### JSON/Object

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

const Btn = styled('button')((props) => ({
    borderRadius: props.size + 'px'
}));

<Btn size={20} />;
```

##### Arrays

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

const Btn = styled('button')([
    { color: 'tomato' },
    ({ isPrimary }) => ({ background: isPrimary ? 'cyan' : 'gray' })
]);

<Btn />; // This will render the `Button` with `background: gray;`
<Btn isPrimary />; // This will render the `Button` with `background: cyan;`
```

##### Forward ref function

As @devtea2027/minus-voluptate-at-consequatur is JSX library agnostic, you need to pass in the forward ref function for the library you are using. Here's how you do it for React.

```js
const Title = styled('h1', React.forwardRef)`
    font-weight: bold;
    color: dodgerblue;
`;
```

### `setup(pragma: Function, prefixer?: Function, theme?: Function, forwardProps?: Function)`

The call to `setup()` should occur only once. It should be called in the entry file of your project.

Given the fact that `react` uses `createElement` for the transformed elements and `preact` uses `h`, `setup` should be called with the proper _pragma_ function. This was added to reduce the bundled size and being able to bundle an esmodule version. At the moment, it's the best tradeoff I can think of.

```js
import React from 'react';
import { setup } from '@devtea2027/minus-voluptate-at-consequatur';

setup(React.createElement);
```

#### With prefixer

```js
import React from 'react';
import { setup } from '@devtea2027/minus-voluptate-at-consequatur';

const customPrefixer = (key, value) => `${key}: ${value};\n`;

setup(React.createElement, customPrefixer);
```

#### With theme

```js
import React, { createContext, useContext, createElement } from 'react';
import { setup, styled } from '@devtea2027/minus-voluptate-at-consequatur';

const theme = { primary: 'blue' };
const ThemeContext = createContext(theme);
const useTheme = () => useContext(ThemeContext);

setup(createElement, undefined, useTheme);

const ContainerWithTheme = styled('div')`
    color: ${(props) => props.theme.primary};
`;
```

#### With forwardProps

The `forwardProps` function offers a way to achieve the same `shouldForwardProps` functionality as emotion and styled-components (with transient props) offer. The difference here is that the function receives the whole props and you are in charge of removing the props that should not end up in the DOM.

This is a super useful functionality when paired with theme object, variants, or any other customisation one might need.

```js
import React from 'react';
import { setup, styled } from '@devtea2027/minus-voluptate-at-consequatur';

setup(React.createElement, undefined, undefined, (props) => {
    for (let prop in props) {
        // Or any other conditions.
        // This could also check if this is a dev build and not remove the props
        if (prop === 'size') {
            delete props[prop];
        }
    }
});
```

The functionality of "transient props" (with a "\$" prefix) can be implemented as follows:

```js
import React from 'react';
import { setup, styled } from '@devtea2027/minus-voluptate-at-consequatur';

setup(React.createElement, undefined, undefined, (props) => {
    for (let prop in props) {
        if (prop[0] === '$') {
            delete props[prop];
        }
    }
});
```

Alternatively you can use `@devtea2027/minus-voluptate-at-consequatur/should-forward-prop` addon to pass only the filter function and not have to deal with the full `props` object.

```js
import React from 'react';
import { setup, styled } from '@devtea2027/minus-voluptate-at-consequatur';
import { shouldForwardProp } from '@devtea2027/minus-voluptate-at-consequatur/should-forward-prop';

setup(
    React.createElement,
    undefined,
    undefined,
    // This package accepts a `filter` function. If you return false that prop
    // won't be included in the forwarded props.
    shouldForwardProp((prop) => {
        return prop !== 'size';
    })
);
```

### `css(taggedTemplate)`

-   `@returns {String}` Returns the className.

To create a className, you need to call `css` with your style rules in a tagged template.

```js
import { css } from "@devtea2027/minus-voluptate-at-consequatur";

const BtnClassName = css`
  border-radius: 4px;
`;

// vanilla JS
const btn = document.querySelector("#btn");
// BtnClassName === 'g016232'
btn.classList.add(BtnClassName);

// JSX
// BtnClassName === 'g016232'
const App => <button className={BtnClassName}>click</button>
```

#### Different ways of customizing `css`

##### Passing props to `css` tagged templates

```js
import { css } from '@devtea2027/minus-voluptate-at-consequatur';

// JSX
const CustomButton = (props) => (
    <button
        className={css`
            border-radius: ${props.size}px;
        `}
    >
        click
    </button>
);
```

##### Using `css` with JSON/Object

```js
import { css } from '@devtea2027/minus-voluptate-at-consequatur';
const BtnClassName = (props) =>
    css({
        background: props.color,
        borderRadius: props.radius + 'px'
    });
```

**Notice:** using `css` with object can reduce your bundle size.

We can also declare styles at the top of the file by wrapping `css` into a function that we call to get the className.

```js
import { css } from '@devtea2027/minus-voluptate-at-consequatur';

const BtnClassName = (props) => css`
    border-radius: ${props.size}px;
`;

// vanilla JS
// BtnClassName({size:20}) -> g016360
const btn = document.querySelector('#btn');
btn.classList.add(BtnClassName({ size: 20 }));

// JSX
// BtnClassName({size:20}) -> g016360
const App = () => <button className={BtnClassName({ size: 20 })}>click</button>;
```

The difference between calling `css` directly and wrapping into a function is the timing of its execution. The former is when the component(file) is imported, the latter is when it is actually rendered.

If you use `extractCSS` for SSR, you may prefer to use the latter, or the `styled` API to avoid inconsistent results.

### `targets`

By default, @devtea2027/minus-voluptate-at-consequatur will append a style tag to the `<head>` of a document. You might want to target a different node, for instance, when you want to use @devtea2027/minus-voluptate-at-consequatur with web components (so you'd want it to append style tags to individual shadowRoots). For this purpose, you can `.bind` a new target to the `styled` and `css` methods:

```js
import * as @devtea2027/minus-voluptate-at-consequatur from '@devtea2027/minus-voluptate-at-consequatur';
const target = document.getElementById('target');
const css = @devtea2027/minus-voluptate-at-consequatur.css.bind({ target: target });
const styled = @devtea2027/minus-voluptate-at-consequatur.styled.bind({ target: target });
```

If you don't provide a target, @devtea2027/minus-voluptate-at-consequatur always defaults to `<head>` and in environments without a DOM (think certain SSR solutions), it will just use a plain string cache to store generated styles which you can extract with `extractCSS`(see below).

### `extractCss(target?)`

-   `@returns {String}`

Returns the `<style>` tag that is rendered in a target and clears the style sheet. Defaults to `<head>`.

```js
const { extractCss } = require('@devtea2027/minus-voluptate-at-consequatur');

// After your app has rendered, just call it:
const styleTag = `<style id="_@devtea2027/minus-voluptate-at-consequatur">${extractCss()}</style>`;

// Note: To be able to `hydrate` the styles you should use the proper `id` so `@devtea2027/minus-voluptate-at-consequatur` can pick it up and use it as the target from now on
```

### `createGlobalStyles`

To define your global styles you need to create a `GlobalStyles` component and use it as part of your tree. The `createGlobalStyles` is available at `@devtea2027/minus-voluptate-at-consequatur/global` addon.

```js
import { createGlobalStyles } from '@devtea2027/minus-voluptate-at-consequatur/global';

const GlobalStyles = createGlobalStyles`
  html,
  body {
    background: light;
  }

  * {
    box-sizing: border-box;
  }
`;

export default function App() {
    return (
        <div id="root">
            <GlobalStyles />
            <Navigation>
            <RestOfYourApp>
        </div>
    )
}
```

#### How about using `glob` function directly?

Before the global addon, `@devtea2027/minus-voluptate-at-consequatur/global`, there was a method named `glob` that was part of the main package that would do the same thing, more or less. Having only that method to define global styles usually led to missing global styles from the extracted css, since the pattern did not enforce the evaluation of the styles at render time. The `glob` method is still exported from `@devtea2027/minus-voluptate-at-consequatur/global`, in case you have a hard dependency on it. It still has the same API:

```js
import { glob } from '@devtea2027/minus-voluptate-at-consequatur';

glob`
  html,
  body {
    background: light;
  }

  * {
    box-sizing: border-box;
  }
`;
```

### `keyframes`

`keyframes` is a helpful method to define reusable animations that can be decoupled from the main style declaration and shared across components.

```js
import { keyframes } from '@devtea2027/minus-voluptate-at-consequatur';

const rotate = keyframes`
    from, to {
        transform: rotate(0deg);
    }

    50% {
        transform: rotate(180deg);
    }
`;

const Wicked = styled('div')`
    background: tomato;
    color: white;
    animation: ${rotate} 1s ease-in-out;
`;
```

### `shouldForwardProp`

To implement the `shouldForwardProp` without the need to provide the full loop over `props` you can use the `@devtea2027/minus-voluptate-at-consequatur/should-forward-prop` addon.

```js
import { h } from 'preact';
import { setup } from '@devtea2027/minus-voluptate-at-consequatur';
import { shouldForwardProp } from '@devtea2027/minus-voluptate-at-consequatur/should-forward-prop';

setup(
    h,
    undefined,
    undefined,
    shouldForwardProp((prop) => {
        // Do NOT forward props that start with `$` symbol
        return prop['0'] !== '$';
    })
);
```

# Integrations

## Babel plugin

You're in love with the `styled.div` syntax? Fear no more! We got you covered with a babel plugin that will take your lovely syntax from `styled.tag` and translate it to @devtea2027/minus-voluptate-at-consequatur's `styled("tag")` call.

```sh
npm i --save-dev babel-plugin-transform-@devtea2027/minus-voluptate-at-consequatur
# or
yarn add --dev babel-plugin-transform-@devtea2027/minus-voluptate-at-consequatur
```

Visit the package in here for more info (https://github.com/devtea2027/minus-voluptate-at-consequatur/tree/master/packages/babel-plugin-transform-@devtea2027/minus-voluptate-at-consequatur)

## Babel macro plugin

A babel-plugin-macros macro for [🥜@devtea2027/minus-voluptate-at-consequatur][@devtea2027/minus-voluptate-at-consequatur], rewriting `styled.div` syntax to `styled('div')` calls.

### Usage

Once you've configured [babel-plugin-macros](https://github.com/kentcdodds/babel-plugin-macros), change your imports from `@devtea2027/minus-voluptate-at-consequatur` to `@devtea2027/minus-voluptate-at-consequatur/macro`.

Now you can create your components using `styled.*` syntax:.

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur/macro';

const Button = styled.button`
    margin: 0;
    padding: 1rem;
    font-size: 1rem;
    background-color: tomato;
`;
```

## [Next.js](https://github.com/vercel/next.js)

Want to use `@devtea2027/minus-voluptate-at-consequatur` with Next.js? We've got you covered! Follow the example below or from the main [examples](https://github.com/vercel/next.js/tree/canary/examples/with-@devtea2027/minus-voluptate-at-consequatur) directory.

```sh
npx create-next-app --example with-@devtea2027/minus-voluptate-at-consequatur with-@devtea2027/minus-voluptate-at-consequatur-app
# or
yarn create next-app --example with-@devtea2027/minus-voluptate-at-consequatur with-@devtea2027/minus-voluptate-at-consequatur-app
```

## [Gatsby](https://github.com/gatsbyjs/gatsby)

Want to use `@devtea2027/minus-voluptate-at-consequatur` with Gatsby? We've got you covered! We have our own plugin to deal with styling your Gatsby projects.

```sh
npm i --save @devtea2027/minus-voluptate-at-consequatur gatsby-plugin-@devtea2027/minus-voluptate-at-consequatur
# or
yarn add @devtea2027/minus-voluptate-at-consequatur gatsby-plugin-@devtea2027/minus-voluptate-at-consequatur
```

## Preact CLI plugin

If you use Goober with Preact CLI, you can use [preact-cli-@devtea2027/minus-voluptate-at-consequatur-ssr](https://github.com/gerhardsletten/preact-cli-@devtea2027/minus-voluptate-at-consequatur-ssr)

```sh
npm i --save-dev preact-cli-@devtea2027/minus-voluptate-at-consequatur-ssr
# or
yarn add --dev preact-cli-@devtea2027/minus-voluptate-at-consequatur-ssr

# preact.config.js
const @devtea2027/minus-voluptate-at-consequaturPlugin = require('preact-cli-@devtea2027/minus-voluptate-at-consequatur-ssr')

export default (config, env) => {
  @devtea2027/minus-voluptate-at-consequaturPlugin(config, env)
}
```

When you build your Preact application, this will run `extractCss` on your pre-rendered pages and add critical styles for each page.

## CSS Prop

You can use a custom `css` prop to pass in styles on HTML elements with this Babel plugin.

Installation:

```sh
npm install --save-dev @agney/babel-plugin-@devtea2027/minus-voluptate-at-consequatur-css-prop
```

List the plugin in `.babelrc`:

```
{
  "plugins": [
    "@agney/babel-plugin-@devtea2027/minus-voluptate-at-consequatur-css-prop"
  ]
}
```

Usage:

```javascript
<main
    css={`
        display: flex;
        min-height: 100vh;
        justify-content: center;
        align-items: center;
    `}
>
    <h1 css="color: dodgerblue">Goober</h1>
</main>
```

# Features

-   [x] Basic CSS parsing
-   [x] Nested rules with pseudo selectors
-   [x] Nested styled components
-   [x] [Extending Styles](#sharing-style)
-   [x] Media queries (@media)
-   [x] Keyframes (@keyframes)
-   [x] Smart (lazy) client-side hydration
-   [x] Styling any component
    -   via `` const Btn = ({className}) => {...}; const TomatoBtn = styled(Btn)`color: tomato;` ``
-   [x] Vanilla (via `css` function)
-   [x] `globalStyle` (via `glob`) so one would be able to create global styles
-   [x] target/extract from elements other than `<head>`
-   [x] [vendor prefixing](#autoprefixer)

# Sharing style

There are a couple of ways to effectively share/extend styles across components.

## Extending

You can extend the desired component that needs to be enriched or overwritten with another set of css rules.

```js
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

// Let's declare a primitive for our styled component
const Primitive = styled('span')`
    margin: 0;
    padding: 0;
`;

// Later on we could get the primitive shared styles and also add our owns
const Container = styled(Primitive)`
    padding: 1em;
`;
```

## Using `as` prop

Another helpful way to extend a certain component is with the `as` property. Given our example above we could modify it like:

```jsx
import { styled } from '@devtea2027/minus-voluptate-at-consequatur';

// Our primitive element
const Primitive = styled('span')`
    margin: 0;
    padding: 0;
`;

const Container = styled('div')`
    padding: 1em;
`;

// At composition/render time
<Primitive as={'div'} /> // <div class="go01234" />

// Or using the `Container`
<Primitive as={Container} /> // <div class="go01234 go56789" />
```

# Autoprefixer

Autoprefixing is a helpful way to make sure the generated css will work seamlessly on the whole spectrum of browsers. With that in mind, the core `@devtea2027/minus-voluptate-at-consequatur` package can't hold that logic to determine the autoprefixing needs, so we added a new package that you can choose to address them.

```sh
npm install @devtea2027/minus-voluptate-at-consequatur
# or
yarn add @devtea2027/minus-voluptate-at-consequatur
```

After the main package is installed it's time to bootstrap @devtea2027/minus-voluptate-at-consequatur with it:

```js
import { setup } from '@devtea2027/minus-voluptate-at-consequatur';
import { prefix } from '@devtea2027/minus-voluptate-at-consequatur/prefixer';

// Bootstrap @devtea2027/minus-voluptate-at-consequatur
setup(React.createElement, prefix);
```

And voilà! It is done!

# TypeScript

`@devtea2027/minus-voluptate-at-consequatur` comes with type definitions build in, making it easy to get started in TypeScript straight away.

## Prop Types

If you're using custom props and wish to style based on them, you can do so as follows:

```ts
interface Props {
    size: number;
}

styled('div')<Props>`
    border-radius: ${(props) => props.size}px;
`;

// This also works!

styled<Props>('div')`
    border-radius: ${(props) => props.size}px;
`;
```

## Extending Theme

If you're using a [custom theme](../api/setup.md#with-theme) and want to add types to it, you can create a declaration file at the base of your project.

```ts
// @devtea2027/minus-voluptate-at-consequatur.d.t.s

import '@devtea2027/minus-voluptate-at-consequatur';

declare module '@devtea2027/minus-voluptate-at-consequatur' {
    export interface DefaultTheme {
        colors: {
            primary: string;
        };
    }
}
```

You should now have autocompletion for your theme.

```ts
const ThemeContainer = styled('div')`
    background-color: ${(props) => props.theme.colors.primary};
`;
```

# Browser support

`@devtea2027/minus-voluptate-at-consequatur` supports all major browsers (Chrome, Edge, Firefox, Safari).

To support IE 11 and older browsers, make sure to use a tool like [Babel](https://babeljs.io/) to transform your code into code that works in the browsers you target.

# Contributing

Feel free to try it out and checkout the examples. If you wanna fix something feel free to open a issue or a PR.

## Backers

Thank you to all our backers! 🙏
<a href="https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur#backers" target="_blank"><img src="https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur/backers.svg?width=890"></a>

## Sponsors

Support this project by becoming a sponsor. Your logo will show up here with a link to your website.
<a href="https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur#sponsors" target="_blank"><img src="https://opencollective.com/@devtea2027/minus-voluptate-at-consequatur/sponsors.svg?width=890"></a>
