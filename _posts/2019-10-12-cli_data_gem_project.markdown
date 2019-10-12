---
layout: post
title:      "CLI Data Gem Project"
date:       2019-10-12 17:01:01 -0400
permalink:  cli_data_gem_project
---




For my first project, I decided to build an interface that shows a user two articles and gives them the choice between focusing on either. I was nervous and excited to start.

<iframe src="https://giphy.com/embed/FZuRP6WaW5qg" width="480" height="443" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/heavy-breathing-FZuRP6WaW5qg">via GIPHY</a></p>

**Overall
**

For this project - 

I started out with psuedo code. The psuedo code portion makes the most sense to me. Which is also why DRY code takes me a bit longer to undersand at first glance. Repitition enhances my changes or remembering something. So when I see repeating code, I notice it's a pattern that is most likely represented by something within the user experience or display of any app or site.


Most of the time was spent setting up the foundation while paying close attention to this video
https://www.youtube.com/watch?v=_lDExWIhYKI . 

I also revisited many of the labs to revisit the concepts of .each_with_index, scraping, and general syntax.

As embarassing as it is to admit, the areas where I struggled were: forgetting which directory I was in, what should be typed into BASH vs in the actual files. 

**Bugs
**

Specific bugs I encountered were typos which led to hours of frustration, and this one where it says goodbye twice for some reason:

```

	// ♥ ./bin/designer_news
	Today's Designer News:
	Enter the number of the item you'd like to read, type list to see the list, or type exit:
	exit
	See you tomorrow for more articles.
	See you tomorrow for more articles.
```


I have no idea how I fixed it, but i do know that it may have caused another error which shows the 'invalid input' text that prompts the user to type '1', '2', 'list', or 'exit'.... along with 'See you tomorrow....'


Still annoyed that there's something to fix but it's part of the process.

https://media.giphy.com/media/1gEbrbxWanjoIPeTwv/giphy.gif

**Scrape
**

For scraping - I've used inspect element alot at work to give design feedback to developers, however some of the selectors were very hard to find. Once, I found a few of the selectors with the help of a Phyllis, a fellow cohort member, and Jake our cohort lead, it was rather easily to locate the rest.

Initially, Nokogiri was pulling every article

Once I got the hang of finding selectors, I spent the next couple hours revisitng how to select specific items. 
Jake suggested` nth-child`

After experimenting with different iterations of that from https://www.w3schools.com/cssref/sel_nth-child.asp - I recalled that `.first` would pull the top item off the sites I'm scraping.... AND THAT THIS WOULD ALSO MEAN THEY'RE THE HIGHEST VOTED/RANKED.

I only want the best for my app's users so I decided to go with this. In all actuality, it was serendipity that worked in my favor...this time.


**What I did when I saw the links appear after the first scrape
**

https://media.giphy.com/media/l41YfcbSoHyk5quLC/giphy.gif


**Retrospective** 

For the future of this project, I'd love to pull 20 articles which would be 10 from each site. The second site would start at 11 which already has me brainstorming about how to solve that problem.

I'm looking forward to getting better at this.


