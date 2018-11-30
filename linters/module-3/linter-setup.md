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

### 3. Add an .eslintrc file to override the airbnb rules:

Create a `.eslintrc` file in your src directory. **It must be in src for the lint script to work properly**

Copy the content below into that file. This rule override makes it so that there is no error for having devDependencies.

```json
// Use this file as a starting point for your project's .eslintrc. 
// By default we're using airbnb's .eslintrc

{
  "rules": {
    "import/no-extraneous-dependencies": ["error", { devDependencies: true }],
  }
}
```

### 4. (Optionally) Add some more rules to your eslint file:

* Comma dangle is for trailing commas - airbnb requires them, below makes it required to omit them
* Max lines per function - airbnb defaults to 50. Below makes it 30
* Semicolons are required by airbnb by default, below makes it so they are required to be absent

```json
{
  "rules": {
    "import/no-extraneous-dependencies": ["error", { "devDependencies": true }],
    "comma-dangle": ["error", "never"],
    "max-lines-per-function": ["error", 30],
    "semi": ["error", "never"],
  }
}
```
