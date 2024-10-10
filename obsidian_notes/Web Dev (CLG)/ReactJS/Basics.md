*SIngle Page vs Multi Page*

- Single Page are web apps that only changes a part of website content with other json file for different options and the base UI remains same(EX:GMAIL)
- Multi page are web apps that reload everytime and a different html file is given to browser for every different item and option which makes it slower compared to single page web apps(Ex:Amazon)
- Web Page -> divided into small parts are called components.
- Component based architecture supports reusability.ReactJS is based on component based architecture.
- `npx create-react-app  name` => creates the base configuration files and other files to support the react app with name "name". (We can write those configuration files and other manually if needed and it's quite complicated and fun)
- A react element can be created using function component or class component.Function components are preferred more as they are easier to implement and also support everything that class does from the react 16.0 v
- The components in react are in heirarchiacal order  and the starting component or base is called root component.
- React elements are created using JSX(JS xtended ) => similar to JS
- `npm start` => starts running the react app on one of the ports 
- `npm start` => under the hood runs 7 process.
- ![[Pasted image 20240815182925.png]]
- Every component can only return one element. So if u want to return like multiple html elements pack them in a div and return the div
- External values outside the html content in jsx can be used in content of html by placing them in `{value(static or dynamic or primitive or non-primitive)}`
- A component can be used as html element in another component which is also called as nesting of components.(parent & child stuff like in trees)

*Hooks*

- Hooks are used to update the state of an element in jsx.
- `import {useState} from 'react'` is the syntax to import the useState named hook from react library.This hook is used to update the current state of an element using a function.Example: 
```jsx
import logo from "./logo.svg";
import "./App.css";
import "bootstrap/dist/css/bootstrap.min.css";
import { useState } from "react";
function Counter() {
  let [counter, setcounter] = useState(1);

  function incr() {
    setcounter(counter + 1);
  }

  return (
    <div>
      <h1>Counter Increment</h1>
      <h1 className="display-2">{counter}</h1>
      <button className="btn btn-success" onClick={incr}>
        Increment
      </button>
    </div>
  );
}

export default Counter;
```
- ![[Pasted image 20240818190701.png]]
- 

