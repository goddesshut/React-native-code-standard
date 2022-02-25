# Typescript Style guides

**TSLint** has been deprecated. In favor of support should using `typescript-eslint` in order to benefit.
### ESLint
ESLint is used for the style guide wiht rule from Airbnb React/JSX.

#### Installation
In your repository, you need to do the following steps
##### Global Install
> npm install -g eslint


### Prettier
Prettier is helful config to help ensure ESLint doesn't report formatting issue. 
It can be run in your editor `on-save`, in a `pre-commit hook` or `CI`

```javascript
.eslintrc.js
{
  "root": true,
  "extends": [
      "@nbc-studio/eslint-config/standard",
      "prettier"
    ],
  "parserOptions": {
    "project": "./tsconfig.json"
  }
}

```