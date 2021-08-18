---
title: "What have we learned so far? "
date: 2021-08-17T19:40:22-06:00
draft: false
---

So this morning I didn't have a blog and now I have this creaking monstrosity that is hosted on a global source code repository and created using a series of command line tools that I didn't have installed this morning either. Its been a bit of a crazy day but I have accomplished a fair bit. So what do I know now that I didn't know this morning?

**\#1 git**

So I knew *of* git this morning but I didn't have any code in it nor was I using it. I certainly made attempts to use it. There were a few web applications that I used and wanted to help develop but they all used git (as does pretty much everyone at this point) and I really wasn't able to figure out how to use it. I am cheating a bit and using Github Desktop instead of the CLI but I suspect that there are very few people that use git exclusively via the CLI when there are such great GUI applications available.

**\#2 Hugo**

I spent a few days looking at static html generators. I know that Github Pages uses Jekyll and it probably would have been easier to use that but there was something about Hugo that I liked. The heart wants what the heart wants I guess. There was a small learning curve involved but I have changed the site's theme, added some menu items and even figured out how to stop Hugo from listing the [About page][about].

Oddly I didn't want to use Jekyll because I didn't want to have to learn Ruby and its package system at the same time as I was learning Javascript and npm. So the fact that Hugo uses Go was a touch amusing. Happily I don't need to delve too deeply into Go in order to use Hugo but I may have to experiment with it a bit more if I want to tweak the blog any more.

**\#3 Markdown**

I have written more Markdown pages in the last day than I have in the last decade. It is interesting to see just how far Markdown has come since its inception. And just how popular it is. It used to be the format of choice for particular bloggers and writers but it has exploded to become the defacto markup language of the internet. It is a testament to John Gruber's original work that it has survived for close to seventeen years with almost no modification. I suspect that no-one uses his original code but having a format not be supplanted in that amount of time is an impressive feat.

**Now what?**

Now that the blog is up and running I will be getting back to my original goal which was to start writing my own data binding code. I know there are many very good libraries available that [do this very thing][ko] but I want to write my own as an exercise in building Javscript classes and also to try to recreate the type of event driven coding that I did back when I developed applications in Lingo. Lingo had a basic event system built into it but if you wanted anything more elaborate you had to roll your own and I did on many occasions. So it is a event system that I understand quite well. No-one has built anything similar in Javascript and I suspect that there is a good reason for this but I think I need to smack my head against that wall and learn the appropriate lessons.

[about]: {{< ref "/page/about" >}} "About the blog"
[ko]: https://knockoutjs.com/index.html "Like Knockout"