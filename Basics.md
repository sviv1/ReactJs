# reactJs
 ## What is React? Introduction
 >- Javascript library developed by Facebook.
 >- Instead of manipulating the browser's DOM directly, React creates a virtual DOM in memory, where it does all the necessary manipulating, before making the changes in the browser DOM.
 >- React only changes what needs to be changed!
 >- We can directly use React in HTML by injecting three scripst first two for javascript and Babel for using jsx and Eslint but for production purposes we need to install npm
 >- if we create react app and open it and change anything suppose html Notice that the changes are visible immediately after you save the file, you do not have to reload the browser!
 >- React main purpose is to render HTML in webpage using its function createRoot() and render() method
 >- createRoot() function takes only one argument ie HTML element , to define the HTML element where react component should be displayed
 >- render is called to define the react component that should be rendered in the container containing the place root in html where it has to be rendered

 ## What is JSX? (Javascript XML)
 >- with JSX we can write html in javascript and converts html tags into react elements.
 >- With JSX you can write expression inside curly braces.

  ```javascript
  const myElement = <h1>React is {5 + 5} times better with JSX</h1>;
  ```
 >- When large html block is there put the HTML inside parenthesis.

 ```javascript
 const myElement = (
  <ul>
    <li>Apples</li>
    <li>Bananas</li>
    <li>Cherries</li>
  </ul>
);
```

>- The html code must be wrapped inside only one top level element for ease we can use fragment look like empty html tag `<></>`.
 ```javascript
 const myElement = (
  <>
    <p>I am a paragraph.</p>
    <p>I am a paragraph too.</p>
  </>
);
```
>- html elements must be closed with `</>`
```javascript
const myElement = <input type="text" />;
```

>- Use attribute className instead of class in JSX:
```javascript
  const myElement = <h1 className="myclass">Hello World</h1>;
```
>- If else statements do not work in JSX so instead use ternary operator if required we have to use if else only outside the jsx.
>- Note that in order to embed a JavaScript expression inside JSX, the JavaScript must be wrapped with curly braces, `{}`.
```javascript
 const x = 5;

const myElement = <h1>{(x) < 10 ? "Hello" : "Goodbye"}</h1>;
```

## Components and Props
 >- Components are just usable bit of code like functions but work in isolation and return HTML.
 ### Rendering a component
  ```javascript
  const root = ReactDOM.createRoot(document.getElementById('root'));
 root.render(<Car />);
```
 ### Props (properties)
 >- Components can be passed as props.
 >- props are like funtion arguments and we send them into the component as attributes.(will see examples)

 ### Components in Componenets
 ```Javascript
   function Car() {
  return <h2>I am a Car!</h2>;
}

function Garage() {
  return (
    <>
      <h1>Who lives in my Garage?</h1>
      <Car />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
>- We split the components in new seperate files .js files and name of such files must start with an uppercase

>- To able to use the component we have to import the file in the application.
```javascript
function Car() {
  return <h2>Hi, I am a Car!</h2>;
}

export default Car;
'''
'''javscript
import React from 'react';
import ReactDOM from 'react-dom/client';
import Car from './Car.js';

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Car />);
```
### Revisiting Props
>- To send props into components , use the same syntax like html attributes.
```javascript
const myElement = <Car brand="Ford" />;
```
>- To use the prop 
```javascript
function Car({brand,info}) {
  return <h2>I am a { props.brand }!</h2>;
}
```
>- If we have a varibale or object to send , then just put the variable name or object name inside the curly brackets.
```javascript
function Car(props) {
  return <h2>I am a { props.info.model }!</h2>;
}

function Garage() {
  const carName = "Ford";
  const carInfo = { name: "Ford", model: "Mustang" } ;
  return (
    <>
      <h1>Who lives in my garage?</h1>
      <Car brand={carName} info={carInfo} />
    </>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Garage />);
```
## React Events
 >- React events are written in camelCase syntax like onClick 
 >- React event handlers are written inside curly braces.

 ```Javascript
 function Football() {
  const shoot = () => {
    alert("Great Shot!");
  }

  return (
    <button onClick={shoot}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```
>- To pass an argument to an event handler, use an arrow function
```javascript
function Football() {
  const shoot = (a) => {
    alert(a);
  }

  return (
    <button onClick={() => shoot("Goal!")}>Take the shot!</button>
  );
}

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<Football />);
```








   



