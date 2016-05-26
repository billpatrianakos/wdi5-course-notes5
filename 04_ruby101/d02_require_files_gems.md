## Requiring & Using Ruby Files + Gems

Github repository: https://github.com/ga-chicago/faking_with_ruby

*Gemfile*
```ruby
source 'https://rubygems.org'

gem 'json'
gem 'httparty'
gem 'faker'
```

*app.rb*
```ruby
require the bundler library
require 'bundler'
Bundler.require

require './user' # load the user.rb file

test_user = User.new # instantiate a new copy of User
p test_user.to_s
```


*user.rb*
```ruby
class User
  require 'faker'
  require 'json'

  def initialize # 0 arguments
    @name = Faker::Name.name # faker is a library designed to fake shit
    @address = Faker::Address.street_address
    @email = Faker::Internet.email
  end

  def to_hash
    return {
      :name => @name,
      :address => @address,
      :email => @email
    }
  end

  def to_json
    self.to_hash.to_json
  end

  def to_s #your job to fix
    return 'nyi'
  end

end
```
#### Challenge

```ruby
class Movie
  #attr_accessor
  # 1. have a constructor that accepts a URL for OMDB
  # 2. The constructor should then use HTTParty.get to get the data\
  # 3. You will then SET instance variables for @title @director @plot
  # 4. Implement a to_s, to_hash, to_json
  # 5. self.method_name == this.methodName() in JS
end
```
