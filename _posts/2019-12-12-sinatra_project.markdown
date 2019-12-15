---
layout: post
title:      "Sinatra Project"
date:       2019-12-12 15:34:25 -0500
permalink:  sinatra_project
---


For my Sinatra Crud Project, I decided to create a web app that called **Movie Dish.**

Here's a sneak peek:

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/E0uEbPN8/Image+2019-12-15+at+5.17.32+PM.png?v=d08cf414b42bcd7e2bb9ac902ef475bfhttp://)


The idea with *Movie Dish* is to pair your favorite movies along with meals 'dishes' that go well the film.
Overall, this is a simple app that follows the basic functionality of many apps used around the web.

The overall requirements of the project are to build an MVC Sinatra Application, with active record, and multiple models. 

In detail, this app also has user accounts, where a person can sign up, sign in, and sign out.
Also, one must be able to validate a user's unique info such as email and password. Once a person logs in, they then have the ability to create, read, update and destroy any entry they create. The acronym for this is CRUD. Furthermore, users can only edit and delete their entries and nothing created by anyone else.

MVC definition:

![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/Z4uwLzRP/Image+2019-12-15+at+5.31.30+PM.png?v=aa60a2be7b5db22ca82f7a35b4f466cfhttp://)

To start this project, referred back to assignments. I realized that I would need to plan out my project a bit. 

The gems: sinatra, require_all, shotgun, pry and byebug.

My overall flow  was as follows:

Step 1 - Create GIT Repo

Step 2 - Create File Structure
![](https://p-066764.f2.n0.cdn.getcloudapp.com/items/BluNZEnO/Image+2019-12-15+at+5.49.20+PM.png?v=be09ac5b4c445d6208efe3623a6461f3http://)


The views folder contain .erb files what the user would se

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


Here is a walkthrough.
https://www.dropbox.com/s/0m5w7f9x01lin78/Sinatra_Movie.mov?dl=0
