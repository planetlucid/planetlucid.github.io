---
layout: post
title:      "JS Project"
date:       2020-04-07 18:05:39 -0400
permalink:  js_project
---


For my 4th project, I decided to build a Flash Card app. I was inspired by Brainscape and wanted to do a minimal, simple version that focused on programming and associated terminology.

To keep things simple I predetermined 3 languages that an anonymous user would select. The 3 languages I added to the dropdown are Ruby, Javascript, and HTML. I didn’t add CSS because I feel most comfortable with CSS and wanted to focus on process and terms that I want to get to know better.

This project is a single page application where the model relationship is as follows:
languages have many cards and cards belong to languages. To meet the requirements, I used 3 of the 4 CRUD verbs - Create, Read, and Destroy. In my index.js file Fetch requests are mapped to my controllers Post, Get, and Destroy. To show the model relationship, I also added a label to each card that displays the language that it belongs to. 

In a nutshell, when an anonymous user adds card they’d like to study, they first select the language from a dropdown. Next, there are a form fields for them to enter a question, title, and the answer. When they click the submit button, they are then taken to the card they just added. If they delete a card, they’re taken to the next most recent card. Flip reveals the answer. Previous and Next go the previous or next cards.

Since JS is the most recent section we’ve started studying, most of the cards I added were for Javascript . Next, I spent some time on sorting through solutions and realized that a lot has changed a lot since the JS of 2015.  Moreover, when I Googled the solution to various issues, the results would vary between approach based on skill level, whether it was pre/post-2015, and whether or not a framework was in use. The 3rd reason is that Javascript is fundamental to how we experience the web. According Hackernoon, JS was the number one most popular programming language in 2019.

I found it interesting that Javascript has a 2 step process for how it allows users to interact with webpages. In Step 1, the code is read line by line from top to bottom where it focuses on function and variable declarations and creates a note of them in memory. Step 2 is the execution phase where the engine actually calls functions and variables which have already been created in memory.

Overall, when you load any page on the internet your computer sent a folder of files including at least one HTML file. This HTML file is able to load Javascript with something called a script tag that loads the JS from a location in a folder structure. For my project index.html contains a script tag that loads index.js. Index.js performs the actions and communicates with the backend api handled by Ruby on Rails.

This project was an interesting extension into how modern webpages are built. When looking up various approaches to solving problems, I became aware of React, Node and a number of frameworks that allow developers to create more advanced experiences.
