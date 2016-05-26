## Implementing Loops Lab

Codepen: http://codepen.io/billpatrianakos/pen/JGwWaY

#### Starter Code

```html
<main>
  <p>
    Loop over the array of posts and output them to the page using jQuery using 3 types of loops.
  </p>
  <!-- append posts here -->
</main>
```

```css
body {
  background: #f7f7f7;
}
main {
  width: 800px;
  padding: 20px;
  display: block;
  margin: auto;
  background: white;
  border: 1px solid gray;
}
```

```javascript
var posts = [
  {
    id: 1,
    title: 'Donkey Caught Shoplifting',
    author: 'Farmer John',
    publishDate: '2016-02-09',
    body: 'The clepto donkey is at it again, stealing apples from the horses...'
  },
  {
    id: 2,
    title: 'Chicken in a Better Place Now',
    author: 'Farmer Jane',
    publishDate: '2016-02-08',
    body: 'Farmer John and Jane confirm that chicken is now in a better place. A place they call "the stomach". The other farm animals could not confirm when chicken was expected to be back.'
  },
  {
    id: 3,
    title: 'Horse Gets Life in Prison, No Parole',
    author: 'Farmer John',
    publishDate: '2016-02-09',
    body: 'After fatally kicking another young boy over the weekend a Farm House judge threw the book at Horse giving him life in prison. The judge noted Horse was lucky to not be sent to the glue factory.'
  },
  {
    id: 4,
    title: 'Goat Ordered to Pay Restitution to Cows',
    author: 'Farmer John',
    publishDate: '2016-02-09',
    body: 'After a series of unfortunate tipping pranks gone wrong, Goat has been ordered to pay restitution for pain and suffering he caused to the Cow family. Goat could not be Bahhh-thered for a comment.'
  }
];

// Use this in a loop to output the contents of the posts variable in a blog format using any loop of your choosing.
$('main').append(/* Append your data to the DOM here */)
```
