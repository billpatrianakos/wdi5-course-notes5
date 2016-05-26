## Functions Recap

```js
// scientists figure out what color, flavour, and scent
// to use
function defineJellyBean(colour, flavour, scent) {
  var jellyBean = {
    color: colour,
    flavor: flavour,
    scent: scent
  }
  return jellyBean;
};
// function makeCakeMix(eggs, flour, milk, water) {
//
// }
// call (or EXECUTE) the function
var beth = defineJellyBean('aquamarine', 'elderberry', 'blueberries');
var vic = defineJellyBean('pink-green', 'watermelon', 'watermelon');
var darthVader = defineJellyBean('light/dark green', 'pear', 'pear');
var crazyPerson = defineJellyBean('yellow and white spotted', 'popcorn', 'dry erase marker');
```

#### Real World Example: DOM

```js
// create a '<p>with text</p>'
function createDomElement(tagName, content) {
  var domElement;
  // create an element of type tagName with innerHTML of my content
  domElement = document.createElement(tagName);
  domElement.innerHTML = content;
​
  // add (or append) to the bottom of my page
  return domElement;
}
var fakeNewsArticle = createDomElement('article', 'In news today, Billy Corgan came to WDI and named himself Scott.');

```
