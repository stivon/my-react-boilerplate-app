## MODERN JAVASCRIPT TOOLING WITH REACT

## npm init

## git init

## npm init -Y

## Install webpack and webpack-cli

- node_modules/.bin/webpack
- node dist/main.js
- in package.json add : "build": "webpack" and then type npm run build in the terminal
  -In development, you can use : npm run build -- --mode development

## Define an Entry Point with a webpack Configuration File

-webpack.config.js

## control the output of webpack wkth the mode setting : mode: 'development'

- we can let it with mode: production and use : npm run build -- --mode development

## Transform Modern Javscript features with Babel

- npm i -D @babel/core @babel/cli @babel/preset-env

## Configure webpack to Load JavaScript Files through Babel with babel-loader

- npm i -D babel-loader

## Configure Babel for React with preset-react

- npm i -S react react-dom prop-types
- npm i -D @babel/preset-react

## Inject a JavaScript bundle into HTML with the HtmlWebpackPlugin

- npm i -D html-webpack-plugin

## Update your bundle with Each File Save with Webpack's watch mode

- "dev": "webpack --watch --mode development"

## Create separate webpack configs for development and production

- npm i -D webpack-merge
- update webpack.config.js to webpack.config.base.js and add two files : webpack.config.dev.js and webpack.config.dev.js

## Serve a webpack Bundle while Developing with webpack-dev-server

- npm i -D webpack-dev-server
- we can change package.json to configure build et dev
- we can added a new port in webpack.config.development

## Generate source Maps for a better Debugging

- debugger
- Support Proposed JAvscript Features with Babel Plugins
- npm i -D @babel/plugin-proposal-class-properties
- Added an another key in webpack.config.base : plugins: ['@babel/plugin-proposal-class-properties']

## Automatically Import CSS in JavaScript with webpack

- npm i -D css-loader style-loader
- Added rules in package.json :

```javascript
{
  test: /\.css\$/,
  use: ['style-loader', 'css-loader'],
  exclude: /node_modules/
}
```

## Hot Reload a React App in Development with react-hot-loader

- npm i -S react-hot-loader
- added a line in webpack.config.base.js

```javascript
plugins: [
  'react-hot-loader/babel'
  '@babel/plugin-proposal-class-properties'
]
```

- added an import at the top of the file app.js : import { hot } from 'react-hot-loader'
- added this line at the bottom of the file app.js : export default hot(module)(App)
- duplicate the dev line in package.json : "dev:hot": "webpack-dev-server --open --hot --config webpack.config.dev.js",

## Avoid Duplicate Commands by Calling one NPM Script from Another

- Added this line : "dev:hot": "npm run dev -- --hot"

## Analyze a Production JavaScript Bundle with webpack-bundle-analyzer

- npm i -D webpack-bundle-analyzer

## Externalize Dependencies to be Loaded via CDN with webpack

## Target specific browsers with babel-preset-env and the babel pollyfill

## Asynchronously Load webpack Bundles through Code-splitting and React Suspense

```javascript
const Warning = React.lazy(() => import('./Warning'))

<React.Suspense fallback={null}><Warning /></React.Suspense>
```

```
npm i -D @babel/plugin-syntax-dynamic-import
```

- Added a line in webpack.config.base.js : '@babel/plugin-syntax-dynamic-import'

## Run a Simple Test with Jest in a React App

## Set up Tests that render a REact Component with Jest and Babel

## Configure Prettier to Automatically Format Code

- npm i -D prettier pretty-quick
- added this line in package.json : "format": "pretty-quick"
- use this line to test previous file that don't test : npx prettier --write "\*_/_.js"

## Avoid Common JavaScript Errors with ESLint

- npm i -D eslint eslint-plugin-react
- Added this line in scripts from package.json : "lint": "eslint ./"
- In the terminal, type npx eslint --init
- Added the dist directory in an .eslintignore
- npm i -D babel-eslint
- Added this line at the fole of the file eslintrc.json : "parser": "babel-eslint",
- and this line in the "env" on eslintrc.json : "jest": true

## Check for Accessibility Issues in JSX with the jsx-a11y ESLint Plugin

## Run Linting, Tests and Prettier in git Hooks with Husky

- npm i -D husky
- Added these lines in package.json :

```javascript
"husky": {
  "hooks": {
    "pre-commit": "pretty-quick --staged && npm run lint && npm run test"
  }
},
```

## Avoid Deprecated React APIs with React.StrictMode

## Create a New Project by Cloning the Boilerplate Project
