# Javascript Arrays:
- In this tutorial, we will deep dive into the js arrays.

## Notes:
- mutable array methods:
  - mutuable means changes the original value.
  - Eg: push, unshift, pop, shift
- immutable array methods:
  - immutable means cannot change the original array instead create a new copy of that array.
  - shift, 

## Array:
- js array can contain all types of values inside an array.
```js
const mixedArray = [100, true, "tapascript", {}];
```

## Create an array:
- create an array manually or using new Array method
```js
const salad = ['tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado'];

function Car(model) {
    this.model = model;
}

const bmwCar = new Car("BMX X1");

console.log('bmwCar', bmwCar);

const anotherSalad = new Array('tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado');

console.log('Salad', salad);
console.log('anotherSalad', anotherSalad);

console.log('isEqual', salad === anotherSalad);

const two = new Array(2);
// const two = new Array(1, 2);
console.log('two', two);

for(let i = 0; i <= salad.length - 1; i++) {
    console.log(`Element at index ${i} is ${salad[i]}`);
}
```

## Get elements from an array:
- index = The position of an element in the array is known as its index.
- index starts with 0
- index end with length -1
```js
// const element = array[index];
console.log(salad[0]);
console.log(salad[2]);
console.log(salad[5]);
```

## Add elements from an array:
- push - add an element at the end of the array
```js
const ret = salad.push('peanut');
console.log(ret);
console.log(salad);
```
- unshift - add an element at the start of the array
```js
const unRet = salad.unshift('peanut');
console.log(unRet);
console.log(salad);
```

## Remove elements from an array:
- pop - remove an element at the end of the array
```js
const popRet = salad.pop();
console.log(popRet);
console.log(salad);
```
- shift - remove an element at the start of the array
```js
const shiftRet = salad.shift();
console.log(shiftRet);
console.log(salad);
```

## Copy and Clone an array:
- slice - copy the array value
```js
const salad = ['tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado'];
const saladCopy = salad.slice();
console.log('salad before copy', salad);
console.log('salad after copy', saladCopy);
console.log(salad === saladCopy);
```

## Determine if a value is array:
- determine the value is array or not
```js
Array.isArray(['tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado']); // return true
Array.isArray('tomato'); // return false
Array.isArray({'tomato': 'vegetable'}); // return false
Array.isArray([]); // return true

const arr = [1, 2, 3, 4];
Array.isArray(arr); // return true
```

## Array Destructuring:
- allows extracting multiple values from arrays and assigning them to distinct variables
```js
// getting value with index
const veg1 = salad[0];
const veg2 = salad[1];
const veg3 = salad[6];

// Array destructuring
const [veg1, veg2, veg3] = ['tomato', 'onion', 'carrot'];
console.log(veg1, veg2, veg3);
```

### Assign a default value to a variable:
- assign a default value in an array using array destructuring
```js
const [veg1, veg2 = 'onion'] = ['tomato'];
console.log(veg1);
console.log(veg2);
```

### Skip a value in an array:
- skip a value in an array using array destructuring
```js
const [veg1, , veg3] = ['tomato', 'onion', 'carrot'];
console.log(veg1);
console.log(veg3);
```
### Nested array destructing:
- access elements within nested arrays by specifying the indices of the nested elements
```js
const a = [1, 2, [4, [7, 8, ['q', 'r']]]];

let fruits = ['apple', 'berry', 'cherry', 'duriyan', ['tomato', 'onion', 'carrot']];
const veg = fruits[4];
const carrot = veg[2];

const carrot1 = fruits[4][2]; // --> like matrix, this will also return carrot

let [,,,,[,,carrot]] = ['apple', 'berry', 'cherry', 'duriyan', ['tomato', 'onion', 'carrot']];
const veg = fruits[4];
const carrot = veg[2];
```

## Rest parameter and spread operator:
- ... are used for rest parameter and spread operator
- Destructing syntax: const [] = [];
- When ... are appeared on the left side, it is rest parameter
- rest parameter always goes with the varaible.
- When ... are appeared on the right side, it is spread oprator
- spread operator always goes on the value.

### Rest parameter:
- allow a function to accept an indefinite number of arguments as an array, providing a way to represent variadic functions in JavaScript
```js
const [tomato, onion, ...rest] = ['tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado'];
console.log(tomato, rest);
```

### Spread operator:
-  expand an iterable (like an array) into more elements
```js
const mySalad = ['tomato', 'onion', 'garlic', 'ginger', 'corn', 'carrot', 'avacado'];
const mySaladCopy = [...mySalad];
console.log(mySalad, mySaladCopy, mySalad === mySaladCopy);
```

### Usecase of array destructuring in js
#### swap variable value
```js
let first = '1';
let second = '2';
console.log(first, second);

[first, second] = [second, first];
console.log(first, second);
```

#### merge array value
```js
const emotions = ['happy', 'sad'];
const veggies = ['onion', 'tomato', 'garlic'];

const emotionalVeggies = [...emotions, ...veggies];
console.log(emotionalVeggies);
```

## length:
- length property gives number of values inside an array
- js array can hold values upto 2 ** 32-1 = 4294967295
```js
const arr1 = [11, 21, 31];
const arr2 = new Array(7);
console.log(arr1.length); // 3
console.log(arr2.length); // 7

arr1.length = 2;
console.log(arr1); // 2
```

## JS array methods:
- How to create, remove, update, and access arrays in js?
  - concat()
  ```js
  const fisrt = [1, 2, 3];
  const second = [4, 5, 6];
  const third = [7, 8, 9];
  const merged = fisrt.concat(second, third);
  console.log(fisrt, second);
  console.log(merged);
  ```

  - join()
  ```js
  const emotions = ['happy', 'sad'];
  const joined = emotions.join(); 
  // or
  // const joined = emotions.join("<=>");
  console.log(joined)

  [].join() // ""
  ```

  - fill()
  ```js
  const colors = ['red', 'blue', 'green'];
  // colors.fill("pink");
  colors.fill("pink", 1, 3);
  console.log(colors);
  ```

  - includes()
  ```js
  const names = ['tom', 'alex', 'bob', 'john'];
  console.log(names.includes('tom'));
  console.log(names.includes('july'));
  console.log(names.includes('Tom'));
  ```

  - indexOf()
  ```js
  const names = ['tom', 'alex', 'bob', 'john'];
  names.indexOf('alex'); // 1
  names.indexOf('rob'); // -1
  ```

  - lastIndexOf()
  ```js
  const names = ['tom', 'alex', 'bob', 'tom'];
  names.indexOf('tom'); // 0
  names.lastIndexOf('tom'); // 3
  ```

  - reserve()
  ```js
  const names = ['tom', 'alex', 'bob', 'tom'];
  names.reverse();
  ```
  - sort()
  - the default sort() method converts the element types into strings
  - the default sorting order is ascending
  ```js
  const names = ['tom', 'alex', 'bob'];
  console.log(names.sort());

  // decending sort
  names.sort(function(a, b){
      return a === b ? 0 : a > b ? -1 : 1;
  })
  console.log('descending sort', names);

  let ages = [2, 1000, 10, 3, 23, 12, 30, 21];
  console.log(ages.sort());
  console.log(ages.sort(function(a, b){
      return a === b ? 0 : a > b ? -1 : 1;
  }));
  console.log(ages.sort(function(a, b){
      return a === b ? 0 : a > b ? 1 : -1;
  }));
  ```

  - splice()
  ```js
  ```

  - at()
  ```js
  
  ```
  - copyWithin()
  ```js
  
  ```
  - flat()
  ```js
  
  ```
  - grouping element in array
  ```js
  
  ```
  - 

## Static array methods in js
- 

```js

```

```js

```