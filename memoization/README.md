# Memoization

*Memoization is an optimization technique used primarily to speed up computer programs by storing the results of expensive function calls and returning the cached result when the same inputs occur again*

```
const square = num => {
  if(!square.cache){
    square.cache = {};
  }
  if(!square.cache[num]){
    return square.cache[num] = num * num;
  }
  return square.cache[num];
}


console.log(square(3))
console.log(square.cache)

```
