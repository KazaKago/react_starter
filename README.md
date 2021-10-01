React-Starter
===

https://qiita.com/abouch/items/820588d1f334c79926ca

## Getting Started

1. Setup npm project.

```sh
$ npm init -y
```

2. Install TypeScript.

```sh
$ npm install --save-dev typescript
```

3. Setup TypeScript.

```sh
$ npx tsc --init
```

4. Install Webpack.

```sh
$ npm install --save-dev webpack webpack-cli webpack-dev-server ts-loader
```

5. Setup Webpack.

tsconfig.json (https://webpack.js.org/guides/typescript/)
```json
{
  "compilerOptions": {
    "outDir": "./dist/",
    "sourceMap": true,
    "noImplicitAny": true,
    "module": "es6",
    "target": "es5",
    "jsx": "react",
    "allowJs": true,
    "moduleResolution": "node"
  }
}
```

webpack.config.js
```js
const path = require("path")
module.exports = {
  mode: "development",
  entry: "./src/index.tsx",
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        use: "ts-loader",
        exclude: /node_modules/
      },
    ],
  },
  resolve: {
    extensions: [".tsx", ".ts", ".js"],
  },
  devtool: "inline-source-map",
  devServer: {
    static: "./dist/",
    open: true,
  },
}
```

package.json
```json
{
  "scripts": {
    "start": "webpack-dev-server",
    "build": "webpack"
  }
}
```

6. Install React.

```sh
$ npm install --save-dev react react-dom @types/react @types/react-dom
```

7. Setup React.

dist/index.html
```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>my-app</title>
  </head>
  <body>
    <div id="root"></div>
    <script src="main.js"></script>
  </body>
</html>
```

src/index.tsx
```tsx
import React from "react"
import ReactDOM from "react-dom"

const App = () => <div>hello word</div>

ReactDOM.render(<App />, document.getElementById("root"))
```

8. Run.

for development.
```sh
$ npm start
```
