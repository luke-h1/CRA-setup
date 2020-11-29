

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

## LINTING DEPENDENCIES  
````
npm i -D babel-eslint eslint eslint-config-airbnb eslint-config-prettier eslint-plugin-import eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-react-hooks prettier 
````


## LINTING SCRIPTS 
```
  "format": "prettier \"src/**/*.{js,html,scss,jsx,ts,tsx,md}\" --write",
  "lint": "eslint \"src/**/*.{js,jsx}\" --quiet",
  "clean": "rm -rf node_modules && npm i",
```

## HTTP LIBRARIES: 
```
npm i axios 
```


## JEST / TESTING SETUP: 

* dependencies 
```
npm i @testing-library/react @testing-library/user-event @testing-library/jest-dom @wojtekmaj/enzyme-adapter-react-17 enzyme jest-enzyme --legacy-peer-deps
```


* config 
```
import React from 'react';
import ExampleComponent from './ExampleComponent';
import Enzyme, {shallow} from 'enzyme';
import EnzymeAdapter from '@wojtekmaj/enzyme-adapter-react-17';


Enzyme.configure({ adapter: new EnzymeAdapter() });
```


* package.json JEST config 
```
  "jest": {
    "automock": false,
    "moduleFileExtensions": [
      "jsx",
      "js"
    ],
    "moduleDirectories": [
      "node_modules"
    ],
    
    "transform": {
      "^.+\\.jsx?$": "./node_modules/babel-jest",
      "\\.(jpg|jpeg|png|gif|eot|otf|webp|svg|ttf|woff|woff2|mp4|webm|wav|mp3|m4a|aac|oga)$": "./FileTransformer.js"
    },
    "testEnvironment": "jsdom",
    "roots": [
      "./src/components/__tests__/"
    ],
    "modulePathIgnorePatterns": ["<rootDir>/src/components/__tests__/__snapshots__"], 

    "testRegex": ".*.test.js",
    "verbose": true
  },

```