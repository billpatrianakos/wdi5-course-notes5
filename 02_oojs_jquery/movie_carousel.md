## Movie Carousel

```js
var movies = ['Interstellar', 'Empire Strikes Back', "Kill Bill", "Wreck it Ralph"];
// api key.. &apikey=d31f1a94
function MovieElement(movieObject) {

  // create all of my DOM elements and give them attributes/css/etc
  this.domElement = $('<article></article>');
  this.header = $('<h1>' + movieObject.Title + '</h1>');
  this.director = $('<h3>' + movieObject.Director + '</h3>');
  this.image = $('<img src=' + movieObject.Poster + '>');
  this.plot = $('<p>' + movieObject.Plot + '</p>');

  // now I add them together like legos or lincoln logs
  this.domElement.prepend(this.plot);
  this.domElement.prepend(this.image);
  this.domElement.prepend(this.director);
  this.domElement.prepend(this.header);
  console.log(this);
  return this.domElement;

};

function addMovieToPage(url) {
  $.getJSON(url, function(movie) {
    var movieObj = new MovieElement(movie);
    $('#movies').append(movieObj);
  });
}

window.onload = function(evt) {
  console.log('Heyllllloooo');
  // wanna show you my favourite movies
  addMovieToPage('http://www.omdbapi.com/?t=interstellar&y=&plot=short&r=json');
  addMovieToPage('http://www.omdbapi.com/?t=empire+strikes+back&y=&plot=short&r=json');
  addMovieToPage('http://www.omdbapi.com/?t=mean+girls&y=&plot=short&r=json');
  addMovieToPage('http://www.omdbapi.com/?t=almost+famous&y=&plot=short&r=json');
}
```
