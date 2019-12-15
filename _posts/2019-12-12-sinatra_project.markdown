---
layout: post
title:      "Sinatra Project"
date:       2019-12-12 15:34:25 -0500
permalink:  sinatra_project
---


The overall requirements of the project are to build a Model, View, Controller 'MVC' Application, with Sinatra, Active Record, and Multiple models. 

Overall, this is a simple app that follows the basic functionality of many apps used around the web.

In detail, this app also has user accounts, where a person can sign up, sign in, and sign out.
Also, one must be able to validate a user's unique info such as email and password. Once a person logs in, they then have the ability to create, read, update and destroy any entry they create. The acronym for this is CRUD. Furthermore, users can only edit and delete their entries and nothing created by anyone else.

MVC quick look:

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/Z4uwLzRP/Image+2019-12-15+at+5.31.30+PM.png?v=aa60a2be7b5db22ca82f7a35b4f466cfhttp://)

For my particular Sinatra Crud Project, I decided to create a web app called **Movie Dish.**

The idea with *Movie Dish* is to pair your favorite movies along with meals 'dishes' that go well the film. As I add more features over time, this concept could be pretty interesting for theatres that serve actual meals like Arklight in Hollywood, Nitehawk, or Alamo Drafthouse.


Here's a sneak peek:

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/E0uEbPN8/Image+2019-12-15+at+5.17.32+PM.png?v=d08cf414b42bcd7e2bb9ac902ef475bfhttp://)


To start this project, I referred back to assignments and I realized that I would need to plan out my project a bit. 


I created a database.yml file that allowed me to perform migrations that live in the 'db' folder.

```
development:
  adapter: sqlite3
  database: db/quotes.db

```

Then, I installed the following gems.

```
source "https://rubygems.org"

git_source(:github) {|repo_name| "https://github.com/#{repo_name}" }

# gem "rails"
gem 'activerecord', require: 'active_record'
gem 'sinatra-activerecord', require: 'sinatra/activerecord'
gem 'sqlite3'
gem 'rake'
gem 'bcrypt'

group :test, :development do
  gem 'pry'
  gem 'byebug'
  gem 'rubocop'
end
```

My overall flow  was as follows:

Step 1 - Create GIT Repo

Step 2 - Create File Structure
![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/BluNZEnO/Image+2019-12-15+at+5.49.20+PM.png?v=be09ac5b4c445d6208efe3623a6461f3http://)


The views folder contain .erb files what the user would see on the front-end experience.


Step 3 - Create Application Controller and add functionality for User Account to see who is logged in.

```
  helpers do
       
        def logged_in?
            !!current_user
        end

        def redirect_if_not_logged_in
            unless logged_in?
                redirect '/login'
            end
        end
        
        def current_user
            @current_user ||= User.find_by(id: session[:user_id]) if session[:user_id]
        end
    end
```

Step 4 - Create a User controller and inherit attributes from the application controller
```
class User < ActiveRecord::Base
    has_secure_password
    has_many :quotes
end
```


Throughout this process, I did basic google searches that led me to certain GEMS that like TTY Tree.  TTY tree will create a basic structure for projects. I had already created the structure, but I plan on potentially using this in the future.

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/xQu0WvyK/Image+2019-12-15+at+5.44.21+PM.png?v=87bf44f806a9b77caf8a3aec885baab0http://)

Overall, it was really cool to see our ruby lessons come into play while learning about .ERB files that the user sees. On our end, we can build the VIEWS in HTML within the erb file.

I also noticed that every view had a route and that these views would most likely be items some sort of navigation.

Here is a walkthrough.
https://www.dropbox.com/s/0m5w7f9x01lin78/Sinatra_Movie.mov?dl=0
