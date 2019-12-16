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

### Step 1
Create GIT Repo

### Step 2 
Create File Structure
![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/BluNZEnO/Image+2019-12-15+at+5.49.20+PM.png?v=be09ac5b4c445d6208efe3623a6461f3http://)


The views folder contain .erb files what the user would see on the front-end experience.


### Step 3
Create Application Controller and add functionality for User Account to see who is logged in.

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

### Step 4
Create a User controller and inherit attributes from the application controller
```
class User < ActiveRecord::Base
    has_secure_password
    has_many :quotes
end
```


Throughout this process, I did basic google searches that led me to certain GEMS that like TTY Tree.  TTY tree will create a basic structure for projects. I had already created the structure, but I plan on potentially using this in the future.

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/xQu0WvyK/Image+2019-12-15+at+5.44.21+PM.png?v=87bf44f806a9b77caf8a3aec885baab0http://)


### Step 5 Views

Since I have a bit of very basic knowledge with HTML, creating the views was a very fun part of the process for me. 

In the future, I'd like to build a layout file that would create visual consistency.

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/d5ueveDZ/Image+2019-12-15+at+7.14.42+PM.png?v=eae15cc77604745e53da30facd29592chttp://)

# In conlusion: 
Overall, it was really cool to see our Ruby lessons come into play while learning about .ERB files that the user sees. From a development perspective, we can build the VIEWS in HTML within the erb file.

I also noticed that every view had a route and that these views would most likely be items some sort of navigation. Regarding CSS, I used Bootstrap at first. Then I quickly realized that it has fairly heavy load time.

In the future, it may be cool to add a scraping element to this that pulls movies from a site like https://www.moviefone.com/ while combining it with a dish from a site like https://www.allrecipes.com/recipes/

I'm also interested in updating the overall style to be more of a split screen view.
![](https://www.google.com/url?sa=i&source=images&cd=&ved=2ahUKEwjLutuD8bjmAhXiUN8KHV0VB0kQjRx6BAgBEAQ&url=https%3A%2F%2Fuxplanet.org%2Fbest-practices-for-split-screen-design-ad8507d92e66&psig=AOvVaw2vRpM5sasJwqWfcb3_8EOq&ust=1576541509253460http://)

Here is a walkthrough with the current design and implementation.
https://www.dropbox.com/s/onpiyt3zj1uig6m/Sinatra_Movie.mov?dl=0
