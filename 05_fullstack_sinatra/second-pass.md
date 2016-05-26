# Week 5 Review (Second Pass Friday)

> A review of all the most important concepts from this week

## MVC With Sinatra

We've been using Sinatra, a bare bones Ruby web framework built on top of Rack (we'll talk about Rack in later lessons). Our GitBook is great for keeping track of what's going on in class but there's no substitute for the docs so __[please also read the Sinatra docs](http://www.sinatrarb.com/intro.html)__. They're very easy to read and understand just like Sinatra.

Sinatra is a simple web framework you can run as a sinngle file or break out into multiple files. It gives you acccess to methods (like `get`, `post`, `before`, `after`, etc.). Most of these Sinatra methods take a block (an anonymous function or "lamda") and will run their code when you hit that URL. Here's an example of a simple single file Sinatra app:

```ruby
##
# app.rb
# ======
# The main app file
#
# Let's suppose our domain name is localhost:9292
# and we're making a todo list app
##

require 'sinatra' # Requires the Sinatra class into your app

##
# GET /
# -----
# Will handle homepage requests
##
get '/' do
  "Hello I am the home page"
end

##
# POST /
# ------
# Will handle POST (form) requests to the homepage
##
post '/' do
  params_sent = params.map do |key, value|
    "#{key} is #{value} <br>"
  end

  params.to_s # will turn that params hash into a string and we can see what was sent to the app through any forms
end

##
# More routes...
# ---------------
# For the rest of these I won't explain what each does.
# Just understand that you can have many routes in one file
##

get '/kittens/?' # What's up with that '?' at the end? That just makes the trailing slash optional because '/kittens' and '/kittens/' are technically different URLs in the eyes of web servers
  # Let's pretend we have a Kitten model all set up
  my_favorite_kitten = Kitten.find 1 # Use ActiveRecord ORM to find the kitten in the DB with ID of '1'
  my_favorite_kitten
end
```

In a single file Sinatra app there's no config.ru needed so we can just run `ruby app.rb` to start our app

## Databases

There are two kinds of database systems out there in the wild: relational and NoSQL. If your data fits naturally into spreadsheets then relational databases should be chosen. If your data doesn't fit neatly into a spreadsheet then NoSQL should be chosen. But we haven't gotten into NoSQL so let's talk about regular, standard relational databases now:

The following are great and common choices for relational databases:

- Postgresql - This database software adheres very strictly to the SQL standard and is what most hip developers choose to use alongside Ruby and Node.js applications. But remember, just because something is popular doesn't mean its better. Postgresql is a bit harder to use on the command line than MySQL
- MySQL - Another open source dataase. This database doesn't adhere to the SQL standard as strictly as Postgres. This usually isn't a problem unless you have a critical need for standards compliance (think: banking/accounting or healthcare). MySQL is used more often on the web than Postgres when developing Ruby, Node.js, and PHP applications. The MySQL CLI program is much more user friendly.
- SQLite - This is  a flat file based relational database. This means that your database files are stored in something similar to text files on your computer. SQLite is most often used in development mode because it's quick and easy to set up. SQLite should not be used on a production (live) website because it performs poorly under heavy load but is great for local development. SQLite is also commonly bundled into other applications that need their own database. Many iOS and Android applications have an SQLite database bundled with them so they can store data locally in a database without having to connect to the internet

A database is basically like a very fast spreadsheet. You have a database (a sheet) that holds multiple tables. Databases are used to store user login information and other application data. Your back-end program (like Sinatra based apps) will use Model classes to communicate with your database.

### SQL

#### CRUD

Before talking about SQL let's talk about CRUD. Most applications are CRUD apps and CRUD is what you'll do with a database. Assuming you have a database with a table full of todos that looks like this:

<table>
  <tr>
    <th>id</th>
    <th>todo</th>
    <th>due_date</th>
  </tr>
  <tr>
    <td>1</td>
    <td>Walk the dog</td>
    <td>2016-03-26-09:00</td>
  </tr>
</table>

(*The table above has a record that basically says remind me to walk the dog on Saturday at 9am*)

We can perform CRUD operations on this data now. We can:

- __Create__ a new todo item
- __Read__ a single row of the database or get multiple rows at once - however many match our SQL query
- __Update__ one or more rows in a table at the same time
- __Delete__ one or more rows in a table at once

#### SQL: An explanation for the query language

SQL stands for Standard Query Language. It is a query language that *all* relational databases use to Create, Read, Update, and Delete data. Some databases stray from the standard *slightly* here or there but if you know SQL then you'll be able to work with data in __any database__ whether it's in a Postgres database, MySQL database, SQLite, or any other relational database. The big practical difference between database applications is how you create databases and users to access the system but as far as running CRUD operations on data in a database, all database software works the same because they all use SQL.

...more to come...
