# Linter Setup

During mod 3 we want y'all to use airbnb's eslint config for your projects.

Here is a list of setup instructions for adding it to your project along with a lint script. 

## Steps

### 1. Add eslint-config-airbnb as a dev dependency
  * `npm i eslint-config-airbnb -D`
  * or `yarn add eslint-config-airbnb -D`

### 2. Add a lint script and extend airbnb in the eslintrc config portion of package.json

```json
// update the scripts and eslintConfig portions of your package.json to match below
  "scripts": {
    "start": "react-scripts start",
    "build": "react-scripts build",
    "test": "react-scripts test",
    "eject": "react-scripts eject",
    "lint": "./node_modules/eslint/bin/eslint.js --ignore-pattern node_modules/ '**/*.js'"
  },
  "eslintConfig": {
    "extends": [
      "react-app",
      "airbnb"
    ]
  },
```

And that's it! Now you can lint your application by running:
 * `npm lint`
 * or `yarn lint`

### 3. **Optionally:** Add an .eslintrc file to override the airbnb rules:

Create a .eslintrc file in your src directory. **It must be in src for the lint script to work properly**

Copy the content below into that file and update as you like.

```json
// Use this file as a starting point for your project's .eslintrc. 
// By default we're using airbnb's .eslintrc
// Copy this file, and add rule overrides as needed.
// Below are some that you may use.

// comma dangle is for trailing commas - airbnb requires them
// max lines per function - airbnb defaults to 50 
// semicolons are required by airbnb 
{
  "rules": {
    "comma-dangle": ["error", "never"],
    "max-lines-per-function": ["error", 30],
    "semi": ["error", "never"]
  }
}
```
