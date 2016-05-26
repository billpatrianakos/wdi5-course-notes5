## Using APIs!

* Using a jQuery boilerplate, you should create **3** Ajax requests to fetch data from:
* [Sweet APIs Spreadsheet](https://docs.google.com/spreadsheets/d/1CTyNpoL7poPd-MxZ89Rw88C0APjCbI8XEVV7J1d2HpU/edit#gid=0)
* Use the `$.ajax` method at least once.
* Use the `$.getJSON` method at least once.
* Use at **least** 2 APIs (3 would be nice).

#### Requests

* Make sure your requests using Ajax render content on the page. This can be done in `getJSON`'s **callback** or in `ajax`'s **success/error** methods.
* Utilize jQuery (or even vanilla JS if you're feeling it) to render **two** or more attributes from each Ajax request.
* Have all of the requests visible on your jQuery/Ajax boilerplate.

#### Teamwork!

* Work in groups of 2-3 on this project.
* It might be a good idea to research the APIs and test them prior to writing code. Some of these APIs could be out of date!
* Make sure everyone writes the code. Practice makes perfect. Repetition is **great**.


#### Bonus

* Before making an Ajax request, find an **Ajax Spinner** image somewhere. Or some text. Either way, indicate to users on your page that data is being loaded.
* Hide the message/image **after** the Ajax request has been completed (inside of `getJSON`'s **Callback** or `ajax`'s **success** or **error** methods).
* This will let users know something is happening... but it isn't finished yet.
