# JavaScript Objects

__*WARNING:* The general concept of objects in general programming is different from what an object is in JavaScript. They share many similarities but they are not 100% the same. You'll understand these differences later and it's not important to know them now. Just know that we'll be discussing two types of objects: JavaScript objects and objects in general.__

## Learning Objectives

- Understand key-value pair storage
- Know 2 ways to access an object's properties
- Iterate over an object's properties
- __BONUS:__ Learn how to run a JavaScript program in your terminal

## Key-Value Pairs

Remember arrays? You access an array's values using its index (which is an automatically assigned number). Objects contain multiple values just like arrays but the way you access those values is different. Object values are accessed by their properties.

Objects contain key-value pairs. An object's key contains a value. These keys are called the object's properties. Indices are to arrays just as properties are to objects.

## Accessing Object Properties

In this example, this is our JavaScript object:

```
var person = {
  name: 'Bill',
  age: new Date().getFullYear() - 1986, //=> Will return the correct age no matter when the code runs
  hairColor: 'brown',
  favoriteFoods: ['Pizza', 'Hot Dogs', 'Pizza-Hotdogs (Pizza Hut used to make them)'],
  spouse: {
    name: 'Lisa',
    age: 31,
    hairColor: 'Brown'
  },
  greet: function(name) {
    if(name) {
      return 'Hello, ' + name;
    } else return 'Hello';
  }
};
```

Our object has attributes (properties) and abilities (methods).

__Properties__ are the values that are stored in the object. In this object `name`, `age`, `hairColor`, `favoriteFoods` are the properties. Properties are always values or expressions that evalutate to a single value.

__Methods__ are functions contained in an object. Our person object has a `greet` method.

To access any of our properties or run a method, we can use either of these two strategies:

```
// #1: Dot Syntax
person.age;  //=> 21
person.name; //=> 'Bill'

// #2: Bracket or String Literal Syntax
person['age']; //=> 21
person['name'] //=> 'Bill'

// #3: Using a method
person.greet(); //=> 'Hello'
person.greet('Jim') //=> 'Hello, Jim'
```

## Iterating Over an Object

We use the `for in` loop for this. Let's iterate over our person:

```
for(var prop in person) {
  console.log(prop + ' is ' + person[prop]);
}
```

## BONUS: Run programs in your terminal

To run JavaScript programs in your terminal you enter this into your terminal:

```
$ node path/to/your/file.js
```

## Your Turn

Play with the objects on your own now. You can run the code samples here by copying them into the Node.js REPL or save the code in a file called `objects.js` and run it using the terminal command listed above.