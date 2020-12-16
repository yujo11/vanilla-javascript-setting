# vanila-javascript-boilerplate


## setting

### eslint & prettier

___
## config files

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
