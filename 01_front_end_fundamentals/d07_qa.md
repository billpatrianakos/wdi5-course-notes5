## Q&A: Front End Fundamentals

#### Data Types
* number `3.14`
* string `'yolo'`
* Object `{ hi: 'hello'}`
* function `function makeStuff(materials) { ... }`
* boolean `false`

#### Logic & Control Flow

```js
var stuff = ['backpack', 'phone', 'watch'];
var modifiedStuff = stuff.filter(function(item) {
  return item != null;
});
```

```js
function doesUserHaveAge(num) {
  if (parseInt(num) > 120) {
    return false;
  } else if (num) {
    return true;
  }
  return false;
}
```

#### One Line Conditional

```js
var stuff = false;
if (stuff) console.log('this function worked?');
```

#### prompt()

```js
var userAnswer = prompt('What do you do?');
console.log(userAnswer); // their answer as a String
```


#### What is a REPL?

* Reads input
* Evaluates input
* Processes your input
* Loops back to execute new commands

#### Running a File

* `node myFile.js`
* Runs myFile.js


#### Objects

* Objects have attributes - aka Properties
* Also have abiities - Aka Methods
```js
var donkey = {
    definition: 'a domesticated hoofed mammal of the horse family with long ears and a braying call, used as a beast of burden; an ass.'
};
```

#### Loop Types

* `while()`
* `for (var i = 0....)`
* `for in` (for each)
* `array.forEach(function() { ... })` - *this is the fastest to iterate over something*

#### Comparison Operators!

```js
> 1 == 1
true
> 1 == "1"
true
> 1 === "1"
false
> 1 !== "1"
true
>
```

#### Functions

* void or returns a value!

#### Clean Code

* AirBnb Style Guide:  https://github.com/airbnb/javascript/tree/master/es5

#### HTML / CSS

* :D
