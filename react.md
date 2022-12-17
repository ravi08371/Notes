<h1>React Interview Questions and Notes</h1>

<h2>What is React</h2>
<p>React is a JavaScript-based UI development library Which is used to create Interactive UI . Facebook and an open-source developer community run it. Although React is a library rather than a language, it is widely used in web development. The library first appeared in May 2013 and is now one of the most commonly used frontend libraries for web development.</p>
<h2>ReactJS Advantages</h2>
<ul>
  <li>React.js builds a customized virtual DOM. Because the JavaScript virtual DOM is quicker than the conventional DOM, this will enhance the performance of apps.</li>
  <li>ReactJS makes an amazing UI possible.</li>
  <li>Search - engine friendly ReactJS. </li>
  <li>React integrates various architectures.</li>
  <li>It makes advanced maintenance easier and boosts output. </li>
  <li>Guarantees quicker rendering </li>
  <li>ReactJS is supported by a large community.</li>
</ul>
<h2>JSX</h2>
<img src="https://www.simplilearn.com/ice9/free_resources_article_thumb/JSX.PNG">

<h2>Components in React</h2>
<p>Components are the building blocks that comprise a React application representing a part of the user interface.</p>
<img src="https://www.simplilearn.com/ice9/free_resources_article_thumb/ReactComponents.PNG" width="60%">
<p>React separates the user interface into numerous components, making debugging more accessible, and each component has its own set of properties and functions.</p>
<h2>Props in React</h2>
<p>Props, short for Properties in React Props, short for properties, allow the user to pass arguments or data to components. These props help make the components more dynamic. Props in a component are read-only and cannot be changed.</p>

<h2>State in React </h2>
<p>A state is an object that stores properties values for those attributed to a component that could change over some time.State is an object that represents the variables or data that a React component needs to render its UI. It is an essential part of a React component, as it determines how a component will behave and what it will display. A component can update its own state, and when it does, the component's UI will be re-rendered to reflect the new state.</p>
<h2>Why can't Browsers read JSX</h2>
<p>Browsers can’t read JSX because there is no inherent implementation for the browser engines to read and understand them. JSX is not intended to be implemented by the engines or browsers, it is intended to be used by various transpilers to transform these JSX into valid JavaScript code.</p>
<ul>
  <li>React renders HTML to the web page by using a function called render().</li>
  <li>The purpose of the function is to display the specified HTML code inside the specified HTML element.</li>
  <li>In the render() method, we can read props and state and return our JSX code to the root component of our app.</li>
  <li>In the render() method, we cannot change the state, and we cannot cause side effects( such as making an HTTP request to the webserver).</li>

</ul>
<h2>What is Event in React</h2>
<p>An event is an action that could be triggered as a result of the user action or system generated event. For example, a mouse click, loading of a web page, pressing a key, window resizes, and other interactions are called events.</p>

<h2><b>Question 1 :-</b>Create a react application that counts from 0 to 10 and vice-versa also changing the background depending on the value of the counter.</h2>

```react
import "./App.css";
import { useState } from "react";

function App() {
  const [num, setNum] = useState(0);

  const handleDecrement = () => {
    setNum(num - 1);
    document.getElementById("incre").style.backgroundColor = "purple";

    if (num <= 0) {
      setNum(0);
    }
  };
  const handleIncrement = () => {
    setNum(num + 1);
    document.getElementById("incre").style.backgroundColor = "magenta";
    if (num >= 5) {
      document.getElementById("incre").style.backgroundColor = "orange";
    }
    if (num === 10) {
      document.getElementById("incre").style.backgroundColor = "blue";
    }
    if (num >= 10) {
      setNum(10);
    }
  };
  return (
    <div className="App">
      <p id="incre">Preview: {num}</p>
      <button onClick={handleIncrement}>Increment</button>
      <button onClick={handleDecrement}>Decrement</button>
    </div>
  );
}

export default App;
```

<h2>What is Event Bubbeling</h2>
<p>Event bubbling is a term used to describe the way that events propagate, or "bubble," through the DOM (Document Object Model) hierarchy. When an event occurs on an element, it is first handled by that element, and then it is passed up the hierarchy of parent elements to be handled by each of those elements as well. This process is called event bubbling.

For example, consider a simple component that displays a button and a list of items. The button and the list are wrapped in a div element, like this:</p>
```javascript
<div>
  <button>Click me</button>
  <ul>
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>
</div>
```
<p>If you attach an event handler to the button element, it will be called whenever the button is clicked. However, the event will also bubble up to the div element, and if you have attached an event handler to the div element, it will be called as well.

You can use the event.stopPropagation() method to prevent an event from bubbling up the DOM hierarchy. This can be useful if you only want to handle the event at the element where it occurs, and not at any of the parent elements.</p>
<p>Here's an example of how you might use event.stopPropagation() in a React component:</p>


```javascript
import React from 'react';

function Button() {
  function handleClick(event) {
    console.log('Button was clicked!');
    event.stopPropagation();
  }

  return (
    <button onClick={handleClick}>Click me</button>
  );
}
```



<h2>
What are react Hooks
</h2>
<p>
React Hooks are simple JavaScript functions that we can use to isolate the reusable part from a functional component. Hooks can be stateful and can manage side-effects.React hooks are a way to use state and other React features without writing a class. They were introduced in React 16.8 as a way to allow developers to use state and other React features in functional components, rather than just in class-based components.

Functional components are components that are defined as JavaScript functions, rather than as classes. They are simple, easy to understand, and can make your code more readable and maintainable. However, before the introduction of hooks, functional components were not able to use state or other React features that required the component to have access to the component's instance (such as lifecycle methods).
</p>
<h2>
React provides a bunch of standard in-built hooks:
</h2>
<ul>
<li><b>useState:</b>To manage states. Returns a stateful value and an updater function to update it.
</li>
<li><b>useEffect:</b>To manage side-effects like API calls, subscriptions, timers, mutations, and more.</li>
<li><b>useContext:</b>o return the current value for a context.</li>
<li><b>useReducer:</b>A useState alternative to help with complex state management.</li>
<li><b>useCallback:</b>It returns a memorized version of a callback to help a child component not re-render unnecessarily.</li>
<li><b>useMemo:</b>It returns a memoized value that helps in performance optimizations.</li>
<li><b>useRef:</b>It returns a ref object with a .current property. The ref object is mutable. It is mainly used to access a child component imperatively.</li>
<li><b>useLayoutEffect:</b>It fires at the end of all DOM mutations. It's best to use useEffect as much as possible over this one as the useLayoutEffect fires synchronously.</li>
<li><b>useDebugValue:</b>Helps to display a label in React DevTools for custom hooks.</li>

</ul>

<h2>What is useReduser</h2>
<p>Reduser is a simple function which takes an existing state and based on the action it recieves it will return a new state.</p>
