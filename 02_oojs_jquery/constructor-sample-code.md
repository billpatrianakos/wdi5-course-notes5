# Sample Code for Thursday Morning Exercise

This morning we went over Object Oriented JavaScript and constructors specifically. Here's the code we used for this morning's example:

## Step 1: Folder structure

```
cd
cd code
mkdir obj && cd $_
mkdir scripts
touch scripts/app.js
touch index.html
```

## The HTML

Enter this into the HTML file:

```html
<!DOCTYPE html>
<html>
<head>
  <title></title>
</head>
<body>
  <h1>Turtles</h1>
  <ul></ul>

  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="scripts/app.js"></script>
</body>
</html>
```

## The JavaScript

Enter this into your app.js file

```js
function Turtle(color, name, weapon, pizzaTopping) {
  this.color        = color        || 'blue';
  this.name         = name         || 'Leonardo';
  this.weapon       = weapon       || 'Sword';
  this.pizzaTopping = pizzaTopping || 'cheese';
}

var leonardo      = new Turtle('blue', 'Leonardo', 'Katana', 'cheese');
var michaelangelo = new Turtle('orange', 'Michaelangelo', 'nun-jucks', 'sausage');
var randomTurtle  = new Turtle();

// Loop over all the turtles
[leonardo, michaelangelo, randomTurtle].forEach(function(turtle) {
  $('ul').append('<li>' + turtle.name + ': I use a ' + turtle.weapon + ' wear a ' + turtle.color + ' headband and like ' + turtle.pizzaTopping + '</li>');
});
```

## SUPER HARD BONUS

This is stuff we didn't cover - we will in later weeks - but if you get it, you're aweomse:

```js
function Turtle(color, name, weapon, pizzaTopping) {
  this.color        = color        || 'blue';
  this.name         = name         || 'Leonardo';
  this.weapon       = weapon       || 'Sword';
  this.pizzaTopping = pizzaTopping || 'cheese';
}

Turtle.prototype.useWeapon = function() {
  return 'swinging my ' + this.weapon;
}

var lilTurtle = new Turtle();

console.log(lilTurtle.useWeapon());
```
