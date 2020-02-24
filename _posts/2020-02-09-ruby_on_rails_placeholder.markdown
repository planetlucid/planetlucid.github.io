---
layout: post
title:      "Ruby On Rails -  Hero List "
date:       2020-02-09 17:28:51 -0500
permalink:  ruby_on_rails_placeholder
---



**User Journey**

A user signs up to this web app, adds their favorite heroes, types in the hero’s comic appearances, and types in the hero’s team affiliation.  They then, have the ability to view or (possibly filter) by: Hero's name, team and appearances.

Here's what I did.

First I wrote an overall process based on the criteria that needs to pass.


**Breakdown**

Hero - Belongs to Team & title
Comicbook - has many heroes
Team - has many heroes


**Steps**

* Install Rails.

* Set up the Devise gem with Omniauth for GIThub. 
This Gem handles Sign In, Sign Up, and Account


- .Env file - holds git hub ‘Key’ Client ID and ‘Secret’ which is Client Secret 
    - dotenv-rails - makes the .ENV file work by looking for the .ENV file and loading those values in
- Gitignore - add .env to gitignore so you don’t commit the it with the secrets to github.
- ran this
    - bundle exec spring rake routes to get
    user_github_omniauth_authorize GET|POST /users/auth/github


- Ran this to see path of user callbacks: 
    rails routes


- I was curious about something I noticed in examples I found around the web. I thought: "Whats difference between the following" 
    
```
	bundle exec spring rails 
```

and 

```
rails s
```

Spring is a Rails application preloader. It speeds up development by keeping your application running in the background so you don't need to boot it every time you run a test, rake task or migration.

After doing the previous steps, I did the following:

* Set up has_many requirement.

* I wasn't sure what I wanted to be nested so I added this afterwards.
 
* Added an index view of all entries.
 
* Added Destroy and Update.
 
* Added Search.
 
* Added Greeting of actual user name
 


