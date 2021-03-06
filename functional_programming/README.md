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

**1. High order functions**
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
const letters = new Map();

letters.set('A', 2);
letters.set('B', 22);
letters.set('C', 222);

letters.set('D', 3);
letters.set('E', 33);
letters.set('F', 333);

letters.set('G', 4);
letters.set('H', 44);
letters.set('I', 444);


letters.set('J', 5);
letters.set('K', 55);
letters.set('L', 555);

letters.set('M', 6);
letters.set('N', 66);
letters.set('O', 666);

letters.set('P', 7);
letters.set('Q', 77);
letters.set('R', 777);
letters.set('S', 7777);

letters.set('T', 8);
letters.set('U', 88);
letters.set('V', 888);

letters.set('W', 9);
letters.set('X', 99);
letters.set('Y', 999);
letters.set('Z', 9999);
letters.set(' ', 0);

const retrieve_number_code = letter => letters.get(letter).toString();

const join_all = code => code.join().replace(/,/g, '');


const message = 'ola'.toUpperCase().split('');
let code = message.map(retrieve_number_code)
code = join_all(code)

console.log(code) //6665552
```


**2. Map**
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

**3. Filter**
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

**4. Reduce**
```
//Using reduce

const sum = (a, b) => a + b;
let numbers = [1, 2, 3];

const numbersSum = numbers.reduce(sum, 0)
console.log(numbersSum);
```

**5. Currying**
```
function greeting(greet){
  return function(name){
    console.log(`${greet} ${name}`);
  }
}

const hello = greeting('hello');

hello('william');
hello('ricardo');
```


```
const count = () => {
  let n = 1;

  return () => { 
    console.log(n++);
  }
}

const counterOne = count();
const counterTwo = count();
counterOne() //1
counterOne() //2
counterOne() //3
counterOne() //4
counterTwo() //1
counterTwo() //2
```

**6. Compose**
```
const compose = function(f, g) {
    return function(x) {
        return f(g(x));
    };
};

const toUpperCase = function(x) {
    return x.toUpperCase();
};

const exclaim = function(x) {
    return x + '!';
};

const angry = compose(toUpperCase, exclaim);
angry('ahhh');
```


```
const removeParenthesis = phone => phone.replace(/[()]/g, '');

const removeDash = phone => phone.replace(/-/g, '')

const compose = (fa, fb) => phone => fa(fb(phone));

const clearPhone = compose(removeDash, removeParenthesis);

// one entry
const phone = '(12) 1234-1234'
console.log(clearPhone(phone)) //12 12341234

//or

// multiples entries
const phoneList = ['(12) 1234-1234', '(11) 2341-4334'];
const clearPhoneList = phoneList.map(clearPhone);
console.log(clearPhoneList) //[ '12 12341234', '11 23414334' ]
```


```
let numbers = [3, 12, 2]

const greaterThanSeven = number => number > 7;
const double = number => number * 2;

const compose = (fa, fb) => numbers => numbers.filter(fa).map(fb);

const magic = compose(greaterThanSeven, double);

console.log(magic(numbers));
```

```
const reverseWord = s => s.split('').reverse().join('');

const removeVogals = s => s.replace(/[aeiou]/gi, '')

const compose = (fa, fb) => word => fa(fb(word));

const mess = compose(reverseWord, removeVogals);

mess('anagram'); //mrgn
```

```
const byName = object => object.name
const byAge = object => object.age
const isUnderThirty = object => object.age < 30

const people = [{name: 'william', age: 29}, {name: 'bruna', age: 32}]

const compose = (fa, fb) => people => people.filter(fa).map(fb);

const onlyNamesUnderThirty = compose(isUnderThirty, byName);

console.log(onlyNamesUnderThirty(people))
```

```
const median = array => array[parseInt(array.length/2)];
const isEqual = (value1, value2) => value1===value2;
const compose = (fx, fy) => (arg1, arg2) => fy(fx(arg1), fx(arg2));

const isIntersectionEqual = compose(median, isEqual);

console.log(isIntersectionEqual([2,31,2], [4,4,2,31,1,1,1])) //true
```
