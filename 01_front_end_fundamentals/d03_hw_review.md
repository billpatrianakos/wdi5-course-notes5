## Homework Review

In the prior evening, we asked you to solve two problems. We discussed solutions to them this morning. Here is the code we created:

```javascript
// #1
var frenchDrinkingAge = 12;
var usersDrinkingAge = parseInt(prompt('Hey, how old are you?'));
if (usersDrinkingAge >= frenchDrinkingAge) {
  alert('yo, get crunk kid');
} else if (conditional) {
  alert('get outa here');
}

// #2
var rubyDevs = new Array() || [];
var jsDevs = new Array() || [];
var pythonDevs = new Array() || [];

function sortDev(name) {

  switch(name.toLowerCase()) {
    case 'james': pythonDevs.push(name);
      break;
    case 'bill': jsDevs.push(name);
      break;
    case 'jim': rubyDevs.push(name);
      break;
  }
}

sortDev(prompt('What is your name?'));

console.log(rubyDevs);
```
