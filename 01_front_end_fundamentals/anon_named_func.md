## Anonymous and Named Functions

```javascript
// anonymous vs named functions
// Named function can be called (or invoked) by its name
// "Beetlejuice(), Beetlejuice(), Beetlejuice()"
// anonymous functions have no name.

// anonymous examples
// checkoutButton.on('click', function() {
//   console.log('ow y u click me asshole');
// });
var dirtyFunction = function() {
  console.log('scrub a dub dub');
};
dirtyFunction();
var isItLunchYet = function() {
  return "soon";
};
isItLunchYet();

// named examples
function getLunch() {
  return "foodz";
}
function getFoodComad() {
  return "zzzZZZZzzz";
}
getLunch();
getFoodComad();


// I CAN SHOW YOU THE WORLD
function poppingBottles() {
  return 'poppin bottles in the club, like a g6';
}
function sailOnMagicCarpet(yourName, yourFriend, makeMagic) {
  console.log('I can show you the world, ' + yourFriend);
  console.log('Would you like to ' + makeMagic() + ' with me?');
  console.log('I am the king of the world, named ' + yourName);
  return 'hell yeah';
}
sailOnMagicCarpet('Jimbo Jones', 'Kevin Dorian', poppingBottles);


// what is the type of a function?
console.log(typeof sailOnMagicCarpet);
```
