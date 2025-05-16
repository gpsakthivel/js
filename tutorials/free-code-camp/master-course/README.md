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
  - for of splice method is add an element in an array, delete an element in an array, modifies an element in an array.
  - start - start is a index from which the array value get changed.  
  - deleteCount - indicates how many elemnt to be delete from the starting position.
  - item - item can go to n length. element gets added begining from the start index.
  - return new array with the element which satisfies the condition.
  - Eg: splice(start, deleteCount, item, item1, item2)

  ```js
  const names = ['tom', 'alex', 'bob'];
  console.log(names.splice(0, 1)); // ['tom']
  console.log(names.splice(0, 1, 'john')); // ['tom']
  console.log(names);

  console.log(names.splice(1, 0, 'zack')); // []
  console.log(names);

  console.log(names.splice(2, 1, 'zack')); // ['bob']
  console.log(names);
  ```

  - at()
  ```js
  const junkFoodILove = ['hotdog', 'burger', 'pizza', 'popcorn']
  junkFoodILove[4]; // 'popcorn'
  junkFoodILove.at(0); // 'hotdog'
  junkFoodILove.at(2); // 'pizza'
  junkFoodILove.at(-1); // 'popcorn'
  junkFoodILove.at(-4); // 'hotdog'
  junkFoodILove.at(10); // undefined
  ```

  - copyWithin()
  - target - it is an index at which copyWithin() will start copying the element
  - start - start to copy form that index
  - end - optional parameter
  - Eg: copyWithin(target, start, end)
  ```js
  const arr = [1, 2, 3, 4, 5, 6, 7];
  arr.copyWithin(0, 3, 6);
  console.log(arr);

  const arr1 = [1, 2, 3, 4, 5, 6, 7];
  arr1.copyWithin(0, 4);
  console.log(arr1);
  ```

  - flat()
  ```js
  const arr1 = [0, 1, 2, [3, 4]];
  console.log(arr1.flat());
  
  const arr2 = [0, 1, [2, [3, [4, 5]]]];
  console.log(arr2.flat(2));
  console.log(arr2.flat(Infinity));
  ```

  - grouping element in array
  ```js
  const employees = [
      { name: 'Bob', dept: 'Engineering', salary: 5000},
      { name: 'Alex', dept: 'HR', salary: 3000},
      { name: 'Ravi', dept: 'Engineering', salary: 7000},
      { name: 'John', dept: 'Engineering', salary: 1000},
      { name: 'Tom', dept: 'Sales', salary: 6000},
  ];

  const groupedByDept = Object.groupBy(employees, ({dept}) => dept);
  console.log(groupedByDept);

  const groupedBySalaryMoreThan5000 = Object.groupBy(employees, ({salary}) => {
      return salary >= 5000 ? 'More than 5k' : 'Less than 5k';
  });
  console.log(groupedBySalaryMoreThan5000);
  ```

## Static array methods in js
  - Array-like
    - We get error because it is not an array. It is an array like.
    - Array like is an object.
    - {key: "value"} is an object.
    - [1, 2, 3] is an array.

  ```js
  const li_tags = document.getElementsByTagName('li');
  console.log(li_tags);

  // li_tags.forEach(() => {
  //     // Do Something
  // })

  const arr_like = { 0: 'I', 1: 'am', 2: 'array-like'};
  console.log(arr_like);
  // arr_like[2]; // 'array-like'
  // arr_like.length; // 3

  console.log('is array_like an object?', Array.isArray(arr_like)); // false
  console.log('is array_like an object?', arr_like instanceof Object); // true

  function checkArgs() {
      console.log('Array like args', arguments);
      // arguments.pop();
      // arguments.forEach((ele) => {
      //   // Do something
      // });
      const argArr = [...arguments];
      console.log('Converted Array args', argArr);
      argArr.forEach((ele) => {
          // Do something
          console.log(ele);
      });
  }
  checkArgs(1, 45);
  ```

  - not working
  - Array.from()
  ```js
  console.log('HTML collections as array like', document.getElementsByTagName('li'));
  const convertedArr = Array.from(document.getElementsByTagName('li'));
  console.log('Converted Array', convertedArr);
  ```

  - not working
  - Array.fromAsync()
  ```js
  console.log('HTML collections as array like', document.getElementsByTagName('li'));
  const collectionPromise = Array.fromAsync(document.getElementsByTagName('li'));
  console.log('Converted Array', collectionPromise);
  collectionPromise.then((value) => console.log(value));

  const ret = Array.fromAsync({
      0: Promise.resolve('tapascript'),
      1: Promise.resolve('google'),
      2: Promise.resolve('apple'),
      length: 3
  })
  .then((val) => console.log(val));
  console.log(ret);
  ```

  - Array.of()
  ```js
  const a = new Array(2, 3, 4); // [2, 3, 4]
  const b = [4, 5, 6];

  const c = Array.of(2, true, 'test', { "name": "Alex"}, [1, 2, 3]);
  console.log(a, b, c);
  ```

## Array iterator methods in js
  - exapmple array to learn
  ```js
  let customers = [
    {
        'id': 001,
        'f_name': 'tom',
        'l_name': 'jerry',
        'gender': 'M',
        'married': true,
        'age': 23,
        'expense': 100,
        'purchased': ['Stick', 'Blade']
    },
    {
        'id': 002,
        'f_name': 'alex',
        'l_name': 'jerry',
        'gender': 'M',
        'married': true,
        'age': 60,
        'expense': 100,
        'purchased': ['Stick', 'Book']
    },
    {
        'id': 003,
        'f_name': 'bob',
        'l_name': 'jerry',
        'gender': 'M',
        'married': true,
        'age': 80,
        'expense': 100,
        'purchased': ['Toys', 'Book']
    },
    {
        'id': 004,
        'f_name': 'anna',
        'l_name': 'jerry',
        'gender': 'F',
        'married': true,
        'age': 34,
        'expense': 100,
        'purchased': ['Shampoo', 'Book']
    },
    {
        'id': 005,
        'f_name': 'katie',
        'l_name': 'jerry',
        'gender': 'F',
        'married': false,
        'age': 13,
        'expense': 100,
        'purchased': ['Bag', 'Box']
    }
  ];
  ```

  - filter() - this method test each value in the array
  - syntax
  ```js
  const newArray = arr.filter((element, index, array) => {
    // Do something
  })
  ```
  - example
  - get senior citizens by filtering out other customers
  ```js
  const seniorCustomers = customers.filter((customer) => {
      return customer.age >= 60;
  });
  console.log(seniorCustomers);
  ```

  - map() - this method transform each value in the array
  - example - transform to add title and name
  ```js
  const customerWithFullName = customers.map((customer) => {
      let title = "";
      if (customer.gender === 'M') {
          title = "Mr.";
      } else if (customer.gender === 'F' && customer.married) {
          title = "Mrs."
      } else {
          title = "Miss"
      }
      customer['full_name'] = `${title} ${customer.f_name} ${customer.l_name}`
      return customer;
  })
  console.log(customerWithFullName);
  ```

  - reduce() - a reducer function which is also called as callback function to be called on each element of the array.
  - syntax
  ```js
  const newArr = arr.reduce(reducer(accumulator, currentValue, index, array), initialValue);

  // inside the reducer function
  const ret = function reducer(accumulator, currentValue, index, array) {
    // do something with the accumulator and currentValue
    // you get a result
    // you return that result
  }
  ```
  - example
  - the average age of the customers who have purchased the item, 'Book'.
  ```js
  const arr = [1, 2, 3, 4, 5];
  const newArr = arr.reduce((accumulator, currentValue, index, array) => {
    return accumulator + currentValue;
  }, 0);
  console.log(arr, newArr);

  let count = 0;
  const total = customers.reduce((accumulator, customer) => {
      if (customer.purchased.includes('Book')) {
        accumulator = accumulator + customer.age;
        count = count + 1;
      }
      return accumulator;
  }, 0);
  console.log('Cus avg age purchased book:', Math.floor(total/count));
  ```

  - reduceRight() - similar to reduce method
  - unlike reduce method, it iterates the value from right to left.
  ```js
  let number = [100, 40, 15];
  const subsResult = number.reduceRight((accumulator, current) => {
      return accumulator - current;
  })
  console.log(subsResult);
  ```

  - some() - if the specified condition is satisfied atleast one element in an array, we will get true. If not false.
  - syntax
  ```js
  arr.some((element, index, array) => {
    // Do something
  })
  ```
  - example
  - do we have a young customer (age less than 10)
  ```js
  const hasYoungCustomer = customers.some((customer) => {
    return customer.age < 10;
  })
  console.log(hasYoungCustomer);
  ```

  - every() - if the specified condition is satisfied for all the elements in an array, we will get true. If not false.
  - syntax
  ```js
  arr.every((element, index, array) => {
    // Do something
  })
  ```
  - example
  - every customer is married ?
  ```js
  const isAllMArried = customers.every((customer) => {
    return customer.married;
  })
  console.log(isAllMArried);
  ```

  - find() - if the specified condition is satisfied atleast one element in an array, we will get that element.
  - syntax
  ```js
  arr.find((element, index, array) => {
    // Do something
  })
  ```
  - example
  - do we have a youngest customer (age less than 10)
  ```js
  const foundYoungCustomer = customers.find((customer) => {
      return customer.age < 10;
  });
  console.log(foundYoungCustomer);
  ```

  - findIndex() - if the specified condition is satisfied atleast one element in an array, we will get that element's index.
  ```js
  const foundYoungCustomerIndex = customers.findIndex((customer) => {
      return customer.age < 10;
  })
  console.log(foundYoungCustomerIndex);
  ```

  - findLast() - if the specified condition is satisfied atleast one element in an array, we will get that last element.
  ```js
  const foundYoungCustomer = customers.findLast((customer) => {
      return customer.age < 10;
  })
  console.log(foundYoungCustomer);
  ```

  - findLastIndex() - if the specified condition is satisfied atleast one element in an array, we will get that element's last index.
  ```js
  const foundYoungCustomer = customers.findLastIndex((customer) => {
      return customer.age < 10;
  })
  console.log(foundYoungCustomer);
  ```

  - array method chaining
  - use case: get the total amount spend by married customer
  - read the requirement and think what methods to use
  - reduce()
  - map()
  - filter()
  ```js
  // Find all the married customer
  const marriedCustomers = customers.filter((customer) => {
      return customer.married;
  });
  const expenseMapped = marriedCustomers.map((marriedCustomer) => {
      return marriedCustomer.expense;
  }); // [200, 500, 700]
  const totalExpenseMarriedCustomer = expenseMapped.reduce((accum, expense) => {
      return accum + expense;
  }, 0);
  console.log(marriedCustomers, expenseMapped, totalExpenseMarriedCustomer);
  console.log(
      "Total Expense of married customers in INR:",
      totalExpenseMarriedCustomer
  );

  const totalExpense = customers
      .filter((customer) => {
          return customer.married;
      }).map((marriedCustomer) => {
          return marriedCustomer.expense;
      }).reduce((accum, expense) => {
          return accum + expense;
      }, 0);
  console.log(
      "Total Expense of married customers in INR:",
      totalExpense
  );
  ```

  - forEach() - used to iterate over array element and it execute particular function that we provide as a callback to foreach method
  ```js
  const arr = [1, 2, 3, 4, 5];
  let sum = 0;
  arr.forEach((element) => {
      console.log(element);
      sum = sum + element;
  })
  console.log(sum);
  ```

  - entries() - used to iterate an array
  ```js
  const arr = [1, 2, 3, 4, 5];
  const arrayIterators = arr.entries();
  console.log(arrayIterators);
  console.log(arrayIterators.next().value);
  console.log(arrayIterators.next().value);
  console.log(arrayIterators.next().value);
  // for of 
  for(const [index, element] of arrayIterators) {
      console.log(index, element);
  }
  ```

  - values() - similar to entries(), it used to iterate an array
  ```js
  const arr = [1, 2, 3, 4, 5];
  const arrayIterators2 = arr.values();
  console.log(arrayIterators2);
  for(const value of arrayIterators2) {
      console.log(value);
  }
  ```

  - flatMap() - combination of map method and flat method
  ```js
  const arr1 = [1, 2, 3, 4, 5];
  console.log('simple map', arr1.map(item => item * 2));
  console.log('simple flatMap', arr1.flatMap(item => item * 2));

  console.log('complex map', arr1.map(item => [item * 2])); // [[2], [4], [6], ...]
  console.log('complex flatMap', arr1.flatMap(item => [item * 2]));
  ```

## Immutability
  - toReversed()
  ```js
  const items = [1, 2, 3];
  const reversedItems = items.toReversed();
  console.log(items, reversedItems);
  ```

  - toSorted()
  ```js
  const months = ['Mar', 'Jan', 'Feb', 'Dec'];
  const sortedMonths = months.toSorted();
  console.log(months, sortedMonths);
  ```

  - toSpliced()
  ```js
  const months = ['Mar', 'Jan', 'Feb', 'Dec'];
  const months2 = months.toSpliced(1, 0, 'Apr');
  console.log(months, months2);
  ```

  - with()
  ```js
  // with(index, value) 
  
  const numbers = [1, 2, 3, 4, 5];
  // numbers[2] = 6;
  const numbers2 = numbers.with(2, 6);
  console.log(numbers, numbers2);
  
  // numbers[-2] = 8;
  const numbers3 = numbers.with(-2, 8);
  console.log(numbers, numbers3);
  ```
