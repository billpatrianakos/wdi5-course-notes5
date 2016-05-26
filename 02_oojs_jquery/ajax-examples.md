## Ajax Examples with Jango Fett & Mewtoo

```js
window.onload = function(evt) {
  console.log('Ready for some AJAX?!?@?!?@?@!@?');

  // regular ajax!
  // http://swapi.co/api/people/69/
  var req = {
    type: 'get',
    dataType: 'json',
    url: 'http://swapi.co/api/people/69/',
    success: function(data) {
      console.log(data);
    },
    error: function(error) {
      console.log(error);
    }
  };
  // use ajax to send my request and wait for a respose
  $.ajax(req);

  // let us find where jango is from....
  var jangoPlanetReq = {
    type: 'get',
    dataType: 'json',
    url: 'http://swapi.co/api/planets/53/',
    success: function(planet) {
      console.log(planet);
    },
    error: function(error) {
      console.log('ERMAGURRRRD ERRRRRRRRRR');
      console.log(error);
    }
  };
  $.ajax(jangoPlanetReq);

  // 3rd time is a charm!!!!! :) :) :) joy joy joy
  // MEWWWWTOOOO
  $.ajax({
    type: 'get',
    dataType: 'json',
    url: 'http://pokeapi.co/api/v2/pokemon/150/',
    success: function(mewtoo) {
      console.log(mewtoo);
      console.log('bow before the ultimate power int he universe, yo');
      $('body').append(mewtoo.name + ' weighs ' + mewtoo.weight);
    },
    error: function(err) {
      $('body').html('THE SYSTEM IS DOWN');
      console.log(err);
    }
  });

}
```
