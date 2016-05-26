## Sinatra Walkthrough guide

#### Database Design

* We're going to draw out ERD (Entity Reference Diagrams)
* Create a `db\migrations.sql` file.
  - `CREATE DATABASE`
  - `\c db_name`
  - `CREATE TABLE`
* Populate database with test OR production data. We do this with a `db\seed.sql` file.
  - Lots of `INSERT INTO` statements!

#### Creating a Sinatra Application

* We need some files, right?
* `config.ru`, `Gemfile`
* What folders?
* `helpers`, `db,` `models`, `views`, `public`, and `controllers`

#### Adding Models

* Create a model!
* `models\name_of_model.rb`
* Now, require it in our `config.ru`

#### How do we add controllers?

1. Controllers need to be in a `/controllers` folder.
2. Name each controller after the resource it represents (hint: ActiveRecord Model names == Controller names)
3. The controller class should be ResourcenameController
4. `/controllers/resource.rb`
5. Each controller should inherit from ApplicationController
6. In our config.ru, we need to:
  - require the controller - `require './controllers/resource'`
  - require any model (or helpers) the controller needs
  - map a resource (route) to a controller - `map('/resource') { run ResourcenameController }`


#### Videos Reference

* Part One: https://youtu.be/gKg0IpFKtOg
* Part Two: https://youtu.be/dzxzemDg8GY
* Part Three: https://youtu.be/wkwHV6x-UlA
