# Function Programming
Functional programming (often abbreviated FP) is a programming paradigm 
Characteristics
* composing pure functions
* avoiding shared state
* avoiding mutable data
* avoiding side-effects. 

Functional programming is a programming paradigm
```
const sum = (a, b) => a + b;

const calculateSum = (a, b, fn) => {
  return fn(a, b);
}

calculateSum(10, 5, sum); //15
```