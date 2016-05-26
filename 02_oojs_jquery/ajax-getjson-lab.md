## $.getJSON Lab

* Browse to http://omdbapi.com
* Scroll down to Examples
* Search for your favourite movie
* Follow the URL provided to view the Object (JSON)
* Use `$.getJSON(url, callback(data));` to render the movie's `Title` and another **property** on your page.

#### Lawrence of Arabia Example

```js
// whoa... let's get some JSON!
$.getJSON('http://shakeitspeare.com/api/poem', function(data) {
  console.log(data); // log out the data we want
  $('body').append(data.poem);
});

// how james can haz movie
// $.getJSON(urlToGetFrom, callback(data));
$.getJSON('http://www.omdbapi.com/?t=Lawrence+of+Arabia&y=&plot=short&r=json', function(movie) {
  //console.log(movie);
  //console.log('This movie had ' + movie.Actors + ' in it! It was rated ' + movie.Rated);
  var movieArticle = $('<article></article>'); // <article> or document.createElement('article')
  var movieHeader = $('<h1></h1>'); // <h1> or document.createElement('h1')
  movieHeader.html(movie.Title); // .html in vanilla === .innerHTML
  movieArticle.append(movieHeader); // <article><h1>Lawrence of Arabia</h1></article>
  var moviePlot = $('<p></p>'); // <p> or document.createElement('p');
  moviePlot.html(movie.Plot);
  movieArticle.append(moviePlot);
  $('body').prepend(movieArticle); // append (or add to the end of the page) this <article> with all the contents
});
```
