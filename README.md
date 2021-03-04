# vanila-javascript-boilerplate


## ⚙️ setting

#### 1. yarn init

```
yarn init
```
#### 2. install eslint, prettier, eslint-config-prettier, eslint-plugin-prettier
```
yarn add eslint prettier eslint-config-prettier eslint-plugin-prettier --dev
```

#### 3(optional). install eslint-config-airbnb-base
```
yarn add eslint-config-airbnb-base --dev
```

#### 4(optional). install cypress
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

### .prettierrc
```
{
  "semi": true,
  "useTabs": false,
  "tabWidth": 2,
  "printWidth": 80,
  "endOfLine": "auto",
  "singleQuote": true,
  "arrowParens": "always",
  "trailingComma": "all"
}
```

### .eslintrc.json

```
{
  "env": {
    "browser": true
  },
  "extends": ["airbnb-base", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "parserOptions": {
    "sourceType": "module"
  },
  "ignorePatterns": ["cypress/"],
  "rules": {
    "no-new": "off",
    "no-alert": "off",
    "no-param-reassign": "off",
    "no-return-assign": "off",
    "import/extensions": "off",
    "import/prefer-default-export": "off",
    "max-depth": ["error", 1],
    "max-lines-per-function": ["error", 15]
  }
}
```
