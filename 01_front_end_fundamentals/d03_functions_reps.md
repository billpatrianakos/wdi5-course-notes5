
## Functions

#### Learning Objectives

- Describe a functions
- Defend using a function
- Create and call a function with and without parameters
- Differentiate an anonymous and a named function
- Pass a function... as an argument


#### Class Examples

```javascript
// i liek pieeeee

// 1. We need to gather ingredients!
// This function will return a value.
function gatherIngredients() {
  // declare a return value
  var ingredients = [];

  // magic happens :)
  ingredients.push('eggs', 'flour', 'coconut milk', 'pecans', 'rubarb', 'strawberry', 'unicorn blood');

  // return my return value
  return ingredients;
}
gatherIngredients(); // 'call' or 'invoke' a function
var pieIngredients = gatherIngredients();
console.log(pieIngredients);

// 2. create a function to get utensils
function getUtensils() {
  return ['bowl', 'spoon', 'oven', 'whisker'];
}

// 3. challenge: let's console log out the function
// WITH and WITHOUT invoking it
console.log(getUtensils);
console.log(getUtensils());

// 4. LEGAL PIE DRAMA
function callSaul() {
  return "Hey, this is Saul. What do you need?";
}

function replyToSaul() {
  return "Disney is suing me for making pie. Halppppp plox!@121212121";
}

function saulSays(message) {
  return message;
}

// challenge:
// invoke (or use) these functions to create a conversation.
// you will need to console.log these functions out.
// example: console.log(saySomething('lksjd;klasjklfjasdklfjklasdj'));
console.log(callSaul());
console.log(replyToSaul());
console.log(saulSays('FILE A RESPONSE!!!'));

// 5. VOID FUNCTIONS
function crashYourTerminal() {
  // for (var i = 0; i == 0; i = 0) {
  //   console.log('trolololololololol down the motherfucking halls, lulz <3');
  // }
}

// Void means that a function does not return anything
// it is a jerk
// or is it?
function theVoidTheDarknessConsumesAll() {
  console.log('shhhh, they are coming for you');
}

// #6. create a void conversation using functions
// 4 functions! 2 lines per person
function billCatchesJames() {
  console.log('STOP JAMES');
}
function lolBill() {
  console.log('hahahaahahahah catch me bro');
}
billCatchesJames();
lolBill();
```
