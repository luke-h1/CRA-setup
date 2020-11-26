

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


## JEST SETUP: 

* dependencies 
```
npm i @testing-library/react @testing-library/user-event @testing-library/jest-dom @wojtekmaj/enzyme-adapter-react-17 enzyme jest-enzyme
```


* config 
```
import React from 'react';
import ExampleComponent from './ExampleComponent';
import Enzyme, {shallow} from 'enzyme';
import EnzymeAdapter from '@wojtekmaj/enzyme-adapter-react-17';


Enzyme.configure({ adapter: new EnzymeAdapter() });
```
