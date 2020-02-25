---
layout: post
title:      "Ruby On Rails -  Hero List "
date:       2020-02-09 17:28:51 -0500
permalink:  ruby_on_rails_placeholder
---



The overall requirements for the Ruby on Rails project are to use MVC structure and build upon the concepts we learned in our Sinatra project.

Another goal for this project is to use, identification, authentication, access policy and authorization while showing while allowing users to create an account with another service like Github.

Lastly, we don't use scaffolding because it does way too much and would prevent us from understanding the  inner-workings if we don't create it ourselves.


To start this project, I did a bit of digging around and found greate resources on sites like Dev.to and youtube in general. I was curious about something... I noticed in examples I found around the web. I thought: "Whats difference between.... 
    
```
	bundle exec spring rails 
```

and 

```
rails s
```

As it turns out, `Spring` is a Rails application preloader that speeds up development. It keeps your application running in the background so you don't need to boot it every time you run a test, rake task or migration.

At this point, I started writing down ideas for what the experience would be.

**User Journey**

A user signs up to this web app, adds their favorite heroes, types in the hero’s comic appearances, and types in the hero’s team affiliation.  They then, have the ability to view or (possibly filter) by: Hero's name, team and comic appearances.

![](<Image Here>http://)

Here's what I did. First I wrote an overall process based on the criteria that needs to pass.

To begin building, I wrote a breakdown that I only deviated from when I needed to install or upate a gem or two. Speaking of which Homebrew sent me down a wild path of installing requirements.

**Breakdown**

Hero - Belongs to Team & title
Comicbook - has many heroes
Team - has many heroes

![](<Image Here>http://)


**First Steps**

* Install Rails.

![](<Image Here>http://)


* Set up the Devise gem with Omniauth for GIThub. This Gem handles Sign In, Sign Up, and Account

![](<Image Here>http://)

* .Env file - holds git hub ‘Key’ Client ID and ‘Secret’ which is Client Secret 

* dotenv-rails - makes the .ENV file work by looking for the .ENV file and loading those values in

* Gitignore - add .env to gitignore so you don’t commit the it with the secrets to github.


* Set up has_many requirement.

![](<Image Here>http://)


* I wasn't sure what I wanted to be nested so I added this afterwards.
 
* Added an index view of all entries.
 
* Added Destroy and Update.
 
* Added Search.
 
* Added Greeting of actual user name

The final step I took was to look for waays I could refactor the code. I wanted a way to give the user the ability to click their entries and display the nested route.
 
![](<Image Here>http://)

