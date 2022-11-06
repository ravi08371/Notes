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
<p>A state is an object that stores properties values for those attributed to a component that could change over some time</p>
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
<p>Any event which get Triggers on a child event handlera on the parent get triggers automatically</p>

