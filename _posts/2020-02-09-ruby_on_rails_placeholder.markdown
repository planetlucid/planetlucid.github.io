---
layout: post
title:      "Ruby On Rails -  Hero List "
date:       2020-02-09 17:28:51 -0500
permalink:  ruby_on_rails_placeholder
---

# Request / Response, Routes,  & Params

**What is the Request / Response cycle?**

To answer this, let’s use an example scenario. A user types a url address into their browser. This is a Request from a client (or browser) to a server. The server, which has the code running this address gives a Response to the browser. The browser shows you the response. In the simplest form, the browser asks for a document and then retrieves the document from the server and then shows the document. The server returns the HTML, CSS, and JS to the browser, which formats and displays it as a webpage to the user. 

In a bit more detail, the browser makes a connection to the server and issues a `get` request to literally get the content.

----------

**Rails Router**

So what is the role of routes in the request and response cycle?  In the case of sites with a lot of organized content, a user may want to view a specific item, in a specific category. This is where Rails Router comes in to save the day.

The Rails router looks at URLs and sends them to a controller's action. It generates paths and URLs which helps you code in a DRY manner by avoiding the need to hardcode. Routes live in `config/routes.rb`

To better understand this, let’s use example scenario based on my Rails project.

Here is mine:

![](https://share.getcloudapp.com/mXuq5dDW)

From the example below, when a user types in `/persons/15/comicbooks` , my app (on a hypothetical external server) shows the following:

![](https://share.getcloudapp.com/WnuNl2pZhttp://)

----------

**Rails Router In Action**

 For a user to see this, my app does the following overall actions.


1. It receives an incoming request for: `GET /persons/15/comicbooks`.
2. It asks the router to match it to a controller action. So if the first matching route is:
    `get '/persons/:id', to: 'persons#show' `

then the request is dispatched to the controller's `show` action with `{ id: '15' }` in
`params`.


3. Here is the controller action 
![](https://share.getcloudapp.com/12u1KelK)

4. Here is the corresponding view
![](https://share.getcloudapp.com/z8uX4ER7)

5. Which makes the router generate the path - `/persons/15/comicbooks` for the user to see.

----------


**Role of param as interface w/ browser + controller
**

Here is a look at the Role of `param` as interface with browser and controller. 
I’ll be using specific examples from my Rails project  - Hero List. 

Here we we have a table with Heroes and we can do standard actions like:
`new`, `show`, `edit`, and  `destroy`. 

![](https://share.getcloudapp.com/lluynjlA)

----------

If you go to show for an entry, you can see in the URL it says `persons/15/comicbooks`
What in the name of Krypton is this `15` and where is it coming from? 

This is where params enters. To read this from your application, you have to have access to this ID so you can view person 1, person 2 etc. 

![](https://share.getcloudapp.com/z8uX4EjR)

----------

For this example the id’s are assigned chronologically and automatically. But how? 

Let’s take a look at how we bring this ID number from the URL (ie the `params`) to our application, so we can use it.  Well if you go to your Rails server output, notice there that in this example we can see  `15` for Superman’s `person_id` . This represents parameters or `params` for short. 
![](https://share.getcloudapp.com/GGuN2nYW)



Let’s look at our controller. First, we have something called a before_action that runs before certain listed controller actions.
![](https://share.getcloudapp.com/wbumKZmq)



The `before_action` stops us from needing to rewrite the same line of code over and over in multiple functions. In this particular case, the `before_action` is using a private method called `set_comicbook`, so next let’s see what that does further down the controller. 
What's happening here is that we're asking for for the :id value that comes from `params` 
and `params` comes from the URL. It can also come from other places like when I submit a form.
![](https://share.getcloudapp.com/yAuvZX25)



When we want to show a specific comicbook, we’ll also be using the show method in the controller.
![](https://share.getcloudapp.com/Qwu7bWlO)



So let’s use the edit form. 
![](https://share.getcloudapp.com/BluBQj1j)


As soon as I click the edit link on Superman, my rails console shows that I’m specifically editing an object with the ID of 15
![](https://share.getcloudapp.com/8LuJnGk7)

![](https://share.getcloudapp.com/8LuJnGYE)


Once I actually edit it, we can see Superman has been updated. The parameters we see here now show that the Title for the ID 15 is now “Injustice”.

![](https://share.getcloudapp.com/p9uKrpYo)

---------

**What are some ways we can pass Params?
**

1 - A hidden field tag.

This is a good way to pass through a `param` that is not created by typing in a form.  After a bit of digging I found that it would go in the comicbook form. Then the params would be accessed in the comicbook controller’s index method.

![](https://share.getcloudapp.com/qGuol1Dv)

![](https://share.getcloudapp.com/wbumKAkn)


2 - Inside a link_to

I used this because I needed a way to pass through the parameter without a form.  This passes parameters to another method the controller when a form is unavailable. In this example, there is no form for delete.

![](https://share.getcloudapp.com/v1ur46rO)

--------


**Key Take-Away
**

In the controller, the method below finds the comicbook in the database with whatever `id` we’re passing, in this case `id 15`, or whichever id we’re passing through the form or through manually typing 15 in the URL.

```
def show
  @comicbook = Comicbook.find(comicbook_params[:id])
end
```

--------
Furthermore, `params` also helps us safeguard our apps by acting as a filter. This feature is called `strong_params`. It allows you to whitelist what attributes are allowed to be used and saved into the database.

![](https://share.getcloudapp.com/6quBxO1N)


Those are the basics of `params` . It's a hash-like structure and you can access it with symbols or strings to get the value. It comes from the URL from submitting a form like new or edit.

We produce params and you find it in your rails server output here and you access it from your controllers using params.

--------------------------------------

