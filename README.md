

## PWA CRA: 
```
create-react-app APP_NAME_HERE --template cra-template-pwa 
```


## dependencies 
````
npm i normalize.css react-router-dom  
````

## CSS / CSS-IN-JS FRAMEWORKS 
```
npm i node-sass@4.14.1
npm i styled-components polished 
```

## LINTING

* setup 
```
npx eslint --init (airbnb option)
```

* dependencies  
````
npm i -D babel-eslint eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks prettier 
````


## PACKAGE.JSON SCRIPTS 
```
    "format": "prettier \"src/**/*.{js,html,scss,jsx,ts,tsx,md}\" --write",
    "lint": "eslint \"src/**/*.{js,jsx}\" --quiet --fix",
    "clean": "rm -rf node_modules package-lock.json && npm i --legacy-peer-deps",
    "jest:update": "jest --silent -u",
    "jest:interactive": "jest --watch",
    "stats": "react-scripts build \"--stats\" && webpack-bundle-analyzer build/bundle-stats.json",
    "serve": "serve -s build"
```

## HTTP LIBRARIES: 
```
npm i axios 
```

## ESLINT 

* .eslintignore 
```
reportWebVitals.js
```

* .eslintrc.json
```
{
  "env": {
    "es6": true,
    "browser": true,
    "node": true,
    "commonjs": true
  },
  "extends": ["plugin:react/recommended", "airbnb"],
  "globals": {
    "Atomics": "readonly",
    "SharedArrayBuffer": "readonly"
  },

  "parserOptions": {
    "ecmaFeatures": {
      "jsx": true
    },
    "ecmaVersion": 2018
  },
  "plugins": ["react"],
  "rules": {
    "no-console": "warn",
    "react/jsx-filename-extension": [1, { "extensions": [".jsx"] }],
    "react/jsx-props-no-spreading": "off",
    "react/state-in-constructor": "off",
    "no-unsafe-finally": "off",
    "react/no-unescaped-entities": [
      "error",
      {
        "forbid": [
          {
            "char": ">",
            "alertnatives": ["@gt;"]
          },
          {
            "char": "}",
            "alertnatives": ["&125;"]
          }
        ]
      }
    ]
  }
}
```


### EDITOR CONFIG 
```
# editorconfig.org
root = true
[*]
indent_style = space
indent_size = 2
end_of_line = lf
charset = utf-8
insert_final_newline = true
trim_trailing_whitespace = true
```


### PRETTIER 

* .prettierrc 

```
{"singleQuote": true}
```

### DEPLOY SCRIPT 
```
#!/bin/bash
echo "Are you sure your changes aren't going to break production ?"
read -r response
if [[ $response =~ ^([yY][eE][sS]|[yY])$ ]]; then
    CONTINUE=true
fi

if ! $CONTINUE; then
    # Check if we're continuing and output a message if not
    echo "Exiting with status code 1"
    exit 1
fi
if ! npm run lint; then
    echo ''
    echo ''
    echo "###########################################" 
    echo "# ❌     ESLINT returned an error.     ❌  #" 
    echo "# ❌ process exited with status code 1 ❌  #" 
    echo "###########################################" 
    exit 1
else
    echo 'eslint returned no errors. Deploying to production ✅'
fi
rm -rf build/ 
npm run build 
vc --prod 
```


### BABEL 

* .babelrc 
``` 
{
  "presets": ["@babel/preset-react", "@babel/preset-env"],
  "plugins": ["@babel/plugin-proposal-class-properties"],
  "env": {
    "test": {
      "plugins": ["@babel/plugin-transform-modules-commonjs"]
    }
  }
}

```
