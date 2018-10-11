# React

React is an Open Source view library created and maintained by Facebook. It uses a syntax extension of JavaScript called JSX that allows you to write HTML directly within JavaScript. JSX code must be compiled into JavaScript, so a transpiler is required


1. Simple JSX Element

```
const JSX = (
  <div>
    <h1>This is a block of JSX</h1>
    <p>Here's a subtitle</p>
  </div>
); 
```

2. Render HTML Elements to the DOM

```
const JSX = (
  <div>
    <h1>Hello World</h1>
    <p>Lets render this to the DOM</p>
  </div>
);

ReactDOM.render(JSX,document.getElementById('challenge-node'));
// change code below this line

Credits - [freeCodeCamp](https://www.freecodecamp.org/)