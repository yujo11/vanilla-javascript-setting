# vanila-javascript-boilerplate


## ⚙️ setting

### eslint & prettier
### 1. npm init
```
npm init -y
```
### 2. install eslint, prettier, eslint-config-prettier, eslint-plugin-prettier, babel-eslint
```
npm install eslint prettier eslint-config-prettier eslint-plugin-prettier babel-eslint --save-dev
```
### 3-1(optional). install eslint-config-google
```
npx install-peerdeps --dev eslint-config-google
```
### 3-2(optional). install eslint-config-airbnb-base
```
npx install-peerdeps --dev eslint-config-airbnb-base
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
  "singleQuote": true,
  "arrowParens": "always",
  "trailingComma": "all"
}
```

### .eslintrc.json
#### 3-1. google config
```
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": ["google", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "parserOptions": {
    "sourceType": "module"
  },
  "rules": {
    "parser": "babel-eslint"
    "no-new": "off",
    "no-alert": "off",
    "no-console": "off",
    "no-plusplus": "off",
    "no-param-reassign": "off",
    "no-return-assign": "off",
    "import/extensions": "off",
    "require-jsdoc": "off",
    "max-depth": ["error", 1],
    "max-lines-per-function": ["error", 15]
  }
}

```
#### 3-2. airbnb-base config
```
{
  "env": {
    "browser": true,
    "es2021": true
  },
  "extends": ["airbnb-base", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "parserOptions": {
    "sourceType": "module"
  },
  "rules": {
    "parser": "babel-eslint"
    "no-new": "off",
    "no-alert": "off",
    "no-console": "off",
    "no-plusplus": "off",
    "no-param-reassign": "off",
    "no-return-assign": "off",
    "import/extensions": "off",
    "require-jsdoc": "off",
    "max-depth": ["error", 1],
    "max-lines-per-function": ["error", 15]
  }
}

```
