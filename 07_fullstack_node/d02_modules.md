## Node Modules for Newbies

#### Learning Objectives
* Describe what a **Module** is.
* See a real-world use case of where **Node** saves modules.
* Create your own module and include it in a project.
* Use your own module and be a hero!


#### Password.js

```js
// Password.js
// this module is meant to generate a hash
// from a string...
// say hello to Password.js

// require the BCrypt Module
var bcrypt = require('bcrypt');

// decide what will be exported (aka made public)
// to another developer to use
// we state what can be used
// by saying 'hey module.. export X feature'
// and by feature I mean 'method'
module.exports.sayHi = function() {
  console.log('hey');
}
module.exports.sayGoodbye = function() {
  console.log('goodbye');
}
module.exports.hashPassword = function(str) {
  var pwd = str;
  var salt = bcrypt.genSaltSync(10);
  return bcrypt.hashSync(pwd, salt);
}
module.exports.comparePasswordHash = function(usersAttempedPwd, pwdFromDb) {
  return bcrypt.compareSync(usersAttempedPwd, pwdFromDb); // true OR false
}
// these will now be accessible
```

#### PseudoClass.js

```js
function PseudoClass(argumentsObject) {

  this.props = argumentsObject;

  this.toString = function() {
    var ret = '';
    for (var val in this.props) {
      ret = ret + ", " + val + ": " + this.props[val];
    }
    return ret;
  }

}

module.exports = PseudoClass;
```

#### server.js

```js
// server.js
var Password = require('./Password');
var passwordAttempt = 'giggles89';
var pwdFromDb = 'lolcats';

Password.sayHi();

var hashedPassword = Password.hashPassword(passwordAttempt);

console.log(hashedPassword);

var doesRealPasswordMatch = Password.comparePasswordHash(passwordAttempt, hashedPassword);

var joshHackingAttempt = Password.comparePasswordHash(pwdFromDb, hashedPassword);

console.log(doesRealPasswordMatch);
console.log(joshHackingAttempt);

Password.sayGoodbye();


var PseudoClass = require('./PseudoClass');
var testConstructor = new PseudoClass({
  test: "property",
  junk: 'data',
  sleeping: 'pills'
});
console.log(testConstructor.toString());
```
