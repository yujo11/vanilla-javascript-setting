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

