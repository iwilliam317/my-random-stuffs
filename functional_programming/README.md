# Function Programming
Functional programming (often abbreviated FP) is a programming paradigm. 

Characteristics
* composing pure functions.
* avoiding shared state.
* avoiding mutable data.
* avoiding side-effects. 
* declarative rather than imperative.

Functional code tends to be more concise, more predictable, and easier to test than imperative or object oriented code!

Examples:


```
const sum = (a, b) => a + b;

const calculateSum = (a, b, fn) => {
  return fn(a, b);
}

calculateSum(10, 5, sum); // output 15
```


```
const calculate = (fn, a, b) => fn(a, b);
const sum = (a, b) => a + b;
const mult = (a, b) => a * b;

calculate(sum, 2, 2); // output 4
calculate(mult, 2, 3); // output 6
```