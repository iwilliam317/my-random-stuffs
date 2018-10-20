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

1. High order functions
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

2. Map
```
//Using map
let numbers = [1, 2, 3];

const square = x => x**2;
const squaredNumber = numbers.map(square);
console.log(squaredNumber); // output 1, 4, 9
```


```
//Using map and filter
const students = [
  { name: 'Harry', age: 7, gender: 'm' },
  { name: 'Joseph', age: 8, gender: 'm' },
  { name: 'Hillary', age: 12, gender: 'f' },
  { name: 'Vito', age: 7, gender: 'm' },
  { name: 'Eddie', age: 8, gender: 'm' },
  { name: 'Francesca', age: 11, gender: 'f' }
  ];

const byName = object => object.name;
const isGreaterThanSever = object => object.age > 7;
const isFemale = object => object.gender === 'f';

const studentsNames = students.map(byName);
const studentsGreaterThanSeven = students.filter(isGreaterThanSever).map(byName);
const studentsFemale = students.filter(isFemale).map(byName);

console.group('Results:');
console.log(`Student's name: ${studentsNames}`);
console.log(`Age superior than 7 years: ${studentsGreaterThanSeven}`);
console.log(`Females: ${studentsFemale}`)
console.groupEnd();
```

3. Filter
```
//Using filter
const numbers = [1, 2, 3, 4, 5, 6];
const isEven = number => number % 2 === 0;
const isOdd = number => number % 2 === 1;

const evenNumbers = numbers.filter(isEven);
const oddNumbers = numbers.filter(isOdd);

console.group('Outcome:');
console.log(evenNumbers);
console.log(oddNumbers);
console.groupEnd();
```

4. Reduce
```
//Using reduce

const sum = (a, b) => a + b;
let numbers = [1, 2, 3];

const numbersSum = numbers.reduce(sum, 0)
console.log(numbersSum);
```