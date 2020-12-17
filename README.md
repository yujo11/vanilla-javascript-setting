# vanila-javascript-boilerplate


## ⚙️ setting

### eslint & prettier
### 1. npm init
```
npm init -y
```
### 2. install eslint, prettier, eslint-config-prettier, eslint-plugin-prettier
```
npm install eslint prettier eslint-config-prettier eslint-plugin-prettier --save-dev
```
### 3. install eslint-config-google
```
npx install-peerdeps --dev eslint-config-google
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
