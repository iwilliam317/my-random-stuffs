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

```
let numbers = [1, 2, 3];

const square = x => x**2;
const squaredNumber = numbers.map(square);
console.log(squaredNumber); // output 1, 4, 9
```


```
const students = [
  { name: 'Harry', age: 7 },
  { name: 'Joseph', age: 8 },
  { name: 'Vito', age: 7},
  { name: 'Eddie', age: 8}
  ];

const byName = object => object.name;
const isGreaterThanSever = object => object.age > 7;

const studentsNames = students.map(byName);
const studentsGreaterThanSeven = students.filter(isGreaterThanSever).map(byName);

console.group('Results:');
console.log(`Student's name: ${studentsNames}`);
console.log(`Age superior than 7 years: ${studentsGreaterThanSeven}`);
console.groupEnd();
```