# Simple Vue App

This is an example of a very simple Vue.js application, intended to help one explore the implementation of the common UI use-case using Vue.

## Getting Started

Before starting, ensure that you have a recent version of Node.js.

This project uses Poi to enjoy webpack's bundling abilities without dealing with any config up front.

**Install Poi**

```bash
npm install -g poi
```

**Install npm dependencies (from package.json)**

```bash
npm install
```

**Run in Development Mode (with hot module reload)**

```bash
poi
```

**Build for Production (with minification)**

```bash
poi build
```

## Where is all the HTML and CSS?

Poi generates a barebones index.html file as the browser's entry point. That imports our root Vue component from `components/App.vue`. All the markup within our Vue container (`div#app`) comes from the root component and its children.

## About single-file components

Files with the extension `.vue` are single-file components. Webpack, the module bundler we are using, uses `vue-loader` to split the file's template, script and styles, and produces the HTML, CSS and JS files needed by the browser.