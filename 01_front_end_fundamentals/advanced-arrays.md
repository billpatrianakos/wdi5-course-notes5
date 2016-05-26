# Advanced Arrays and Methods

## Learning Objectives

- Define a method
- Understand what an array is and why they're useful
- Be able to use array methods to:
  - Get the number of items in an array
  - Add or remove items from an array
  - Glue two arrays together
  - Filter arrays
  - Manipulate the values of an array all at once

## Methods

We know by now that objects (and object literals `{}`) can have properties and methods. A method is just a property that holds a function rather than a simple value or expression.

__Example__

```js
var person = {
  name: 'Joey',                         // a simple value
  age: new Date().getFullYear() - 1986, // an expression that returns a simple value
  speak: function(words) {              // METHOD!
    return words;
  }
};
```

Every language comes with a bunch of built in objects. When you first start programming you use these objects and their methods all the time without knowing it. An array is a JavaScript object with built in methods of its own. Every array you create will have these methods without you having to define them.

## Arrays

An array is a list of values. Usually they're related somehow (like a list of blog posts) but they don't have to be. Arrays can hold any data type inside them. All of these are perfectly valid arrays:

```js
var numbers = [5, 300, 420, 9990210];

var junk = [500, 'Hello', true, NaN, undefined, 6.47];

var inception = [
  [1, 2, 3, true],
  'Hello',
  { key: 'value', date: new Date() },
  44
];
```

### Array Methods

#### `Array.length`

`length` is technically a property of an array. It returns the number of items in the array when called.

#### `Array.push` and `Array.shift`

The `.push()` method of an array takes a value as an argument and adds it to the end of the array. The `.shift()` method is exactly the same as `push` except it adds the value to the beginning of the array.

#### `Array.pop` and `Array.unshift`

The `pop` method will remove the last item from the array and return it. `unshift` is exactly the same except it works on the first item in the array instead.

#### Put arrays together

The `concat` method is used on one array and takes another array as an argument. It creates a third array with the items in the selected array added to the end of the original array.

```js
var firstArray  = [1, 2, 3],
    secondArray = [4, 5, 6];

firstArray.concat(secondArray); //=> [1, 2, 3, 4, 5, 6]
```

#### Filter an array

The `filter` method takes a callback (anonymous function) that tests each item in an array for a certain condition. If the condition is met then the item is kept in the array. This method returns a new array with the filtered items removed.

For example, if you had an array of numbers and wanted to only keep even numbers you could filter out odd numbers like this:

(__HINT:__ The `%` symbol, called the modulus operator, returns the remainder of a division problem).

```js
var numbers = [1, 2, 3, 4, 5, 6];

numbers.filter(function(number) {
  return number % 2 === 0;
});

// returns [2, 4, 6]
```

#### Manipulate the values of an array

We use the `.map()` method to loop through an array and change the value of every element. This method returns a brand new array and will not update the original.

```js
var myNumbers = [1, 2, 3, 4, 5];

myNumbers.map(function(number) {
  return myNumber * 2; //=> [2, 4, 6, 8, 10]
});
```


