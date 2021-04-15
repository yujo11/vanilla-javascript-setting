# vanila-javascript-boilerplate


## ⚙️ setting

#### 1. yarn init

```
yarn init
```

#### 2. install eslint, prettier, eslint-config-prettier, semistandard

```
yarn add -D eslint prettier eslint-config-prettier semistandard
```

#### 3. install webpack, webpack-dev-server

```
yarn add -D webpack webpack-cli webpack-dev-server
```

#### 4. install webpack plugins, loaders

```
yarn add -D babel-loader css-loader mini-css-extract-plugin html-webpack-plugin
```

#### 5. install babel

```
yarn add -D @babel/core @babel/eslint-parser @babel/preset-env
```

#### (optional) install cypress

```
yarn add cypress --dev
```


## 📜 config files

### .gitignore

```
node_modules/
.vscode/
.DS_Store
```

### .prettierrc.js

```
module.exports = {
  printWidth: 120,
  singleQuote: true,
};
```

### .eslintrc.js

```
module.exports = {
  env: {
    browser: true,
    es2021: true,
  },
  parser: "@babel/eslint-parser",
  extends: ["semistandard", "prettier"],
  parserOptions: {
    ecmaVersion: 2021,
    sourceType: "module",
  },
  plugins: [],
  rules: {},
};
```

#### webpack.config.js

```
const path = require('path');
const HtmlWebpackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = (_, argv) => {
  const isDevelopment = argv.mode !== 'production';

  return {
    entry: './src/index.js',
    output: {
      filename: 'bundle.js',
      path: path.resolve(__dirname, 'build'),
      clean: true,
    },
    devServer: {
      port: 3000,
      hot: true,
    },
    devtool: isDevelopment ? 'eval-source-map' : 'source-map',
    module: {
      rules: [
        {
          test: /\.(js)$/,
          exclude: /node_modules/,
          use: {
            loader: 'babel-loader',
            options: {
              cacheDirectory: true,
              cacheCompression: false,
              compact: !isDevelopment,
            },
          },
        },
        {
          test: /\.css$/,
          use: [MiniCssExtractPlugin.loader, 'css-loader'],
        },
      ],
    },
    plugins: [
      new HtmlWebpackPlugin({ template: './index.html' }), //
      new MiniCssExtractPlugin({ filename: 'style.css' }),
    ],
    performance: {
      hints: isDevelopment ? 'warning' : 'error',
    },
  };
};
```

#### babel.config.js

```
module.exports = {
  presets: [
    [
      '@babel/preset-env',
      {
        targets: '> 1% and last 2 versions',
      },
    ],
  ],
};
```

#### .editorconfig

```
root = true

[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```

#### .vscode/settings.json

```
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "files.trimTrailingWhitespace": true,
  "editor.formatOnSave": true,
  "editor.codeActionsOnSave": {
    "source.fixAll.eslint": true
  },
  "prettier.useEditorConfig": true
}
```

#### (example)package.json

```
{
  "name": "it-article-archive",
  "version": "1.0.0",
  "main": "index.js",
  "repository": "https://github.com/yujo11/it-article-archive.git",
  "author": {
    "name": "yujo",
    "email": "bedro27@gmail.com",
    "url": "https://yujo11.github.io/"
  },
  "license": "MIT",
  "scripts": {
    "prod": "webpack serve --mode=production",
    "dev": "webpack serve --mode=development",
    "build": "webpack --mode=production"
  },
  "devDependencies": {
    "@babel/core": "^7.13.15",
    "@babel/eslint-parser": "^7.13.14",
    "@babel/preset-env": "^7.13.15",
    "babel-loader": "^8.2.2",
    "css-loader": "^5.2.1",
    "cypress": "^7.1.0",
    "eslint": "^7.24.0",
    "eslint-config-airbnb-base": "^14.2.1",
    "eslint-config-prettier": "^8.2.0",
    "html-webpack-plugin": "^5.3.1",
    "mini-css-extract-plugin": "^1.4.1",
    "prettier": "^2.2.1",
    "semistandard": "^16.0.0",
    "webpack": "^5.33.2",
    "webpack-cli": "^4.6.0",
    "webpack-dev-server": "^3.11.2"
  }
}

```
