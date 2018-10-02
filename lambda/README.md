# Lambdas in Javascript

A characteristic of a lambda expression is that it is used as data. That means that the function is passed as an argument to another function, returned as a value from a function, or assigned to variables or data structures.

Note: Not all lambdas are anonymous, and not all anonymous functions are lambdas!


```
* Example 1: 
// anonymous, pure and lambda

const sum = (a, b) => a + b;


* Example 2:
// functional programming using lambda

const capitalize = message => message.toUpperCase();

const capitalizeMessage = (message, _function) => {
  return _function(message);
}

capitalizeMessage('hey there', capitalize); //output HEY THERE


* Example 3:
const squared = (n) => n**2;
const calculateSquared = (n, f) => f(n);

calculateSquared(3, squared);

```

## IIFE - Immediately-invoked Function Expression
```
// IIFE

* Example 1
function makeCounter(){
  var n = 0;

  return () => {
    console.log(++n);
  }
}

const counter1 = makeCounter();
counter1() //1
counter1() //2

const counter2 = makeCounter();
counter2() //1
counter2() //2

counter1() //3


* Example 2

!function() {
    alert("Hello from IIFE!");
}();

void function() {
    alert("Hello from IIFE!");
}();

+ function() {
    alert("Hello from IIFE!");
}();


(function(){console.log('hey iife')})()
```