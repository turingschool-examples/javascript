# Linter Setup

During mod 3 we want y'all to use airbnb's eslint config for your projects.

Here is a list of setup instructions for adding it to your project along with a lint script. 

## Steps

### 1. Add eslint-config-airbnb and babel-eslint as a dev dependency
  * `npm i eslint-config-airbnb -D`
  * `npm i babel-eslint -D`

### 2. Add a `lint` script to your package.json file

```json
// update the scripts and eslintConfig portions of your package.json to match below
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "lint": "eslint src/**/*.js"
  },
```

And that's it! Now you can lint your application by running:
  * `npm run lint`

### 3. Add an .eslintrc file to override some of the airbnb rules:

Create a `.eslintrc` file in your project's root
  
```json
// Use this file as a starting point for your project's .eslintrc.
// By default we're using airbnb's .eslintrc

{
  "extends": ["airbnb", "react-app"],
  "parser": "babel-eslint",
  "ignorePatterns": ["node_modules/", "src/serviceWorker.js", "src/reportWebVitals.js"],
  "rules": {
    "react/react-in-jsx-scope": "off",
    "import/no-extraneous-dependencies": ["error", { "devDependencies": true }],
    "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }],
    "react/forbid-prop-types": 0,
  }
}
```
