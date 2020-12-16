# vanila-javascript-boilerplate


## ⚙️ setting

### eslint & prettier
### 1. npm init
```
npm init
```
### 2. install eslint
```
npm install eslint --save-dev
```
### 3. eslint init
```
npx eslint --init
```
### 4.(option)install style config
- google
```
npm install --save-dev eslint-config-google
```
- airbnb
```
npm install --save-dev eslint-config-airbnb 
```
### 5. install prettier config
```
npm install --save-dev eslint-config-prettier
```
### 6. install prettier plugin
```
npm install --save-dev eslint-plugin-prettier
```
#### 
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
    "browser": true
  },
  "extends": ["google-base", "plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "rules": {
    "no-new": "off",
    "no-alert": "off",
    "no-console": "off",
    "no-plusplus": "off",
    "no-param-reassign": "off",
    "no-return-assign": "off",
    "import/extensions": "off",
    "max-depth": ["error", 2],
    "max-lines-per-function": ["error", 15]
  }
}
```
