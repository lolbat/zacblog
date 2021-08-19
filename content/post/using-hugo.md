---
title: "Using Hugo"
date: 2021-08-19T15:41:15-06:00
draft: false
tags:
    - hugo
    - wordpress
    - nota
---

Hugo is a considerably different writing process than using a CMS like Wordpress[^1]. You can't use Wordpress on a server that isn't configured to serve dynamic content. It is interesting that I have gone from doing work that required a server instance with php or ColdFusion as well as a database to building apps and a CMS that are served from static HTML.

You also lose control over your content with Wordpress even if you run your own server or VPS. The content sits in a database and some of the content, usually the Wordpress shortcodes, is not rendered until the page is served. So if you have image galleries and want to export that page you need to find a way to render it as part of the export process.  With Hugo even if the server turns into a molten heap I still have all my content stored locally in a non-proprietary format. 

I don't expect that I will be using image galleries a lot so the image features in Hugo aren't an issue. I do like how it handles page resources and that was a delight to see when I finally read up on it. In the past when I have been blogging and using images I have had to either use single images when using an app like [MarsEdit][medit] or have to go into the Wordpress CMS itself to create image galleries. Until about a year ago I was actually doing most of my writing in the Wordpress web app. Sadly they continued to make changes to their editor that made it less and less enjoyable to use and made writing a bit of a PITA. 

I went back to using MarsEdit a few months ago and it was an immediate relief to use. It gets out of your way and just lets you write. I decided a few weeks ago to stop writing the blog that I was hosting on Wordpress and so I am not using MarsEdit anymore and it isn't aimed at this type of blogging environment. I mentioned in the About page that I was using Caret to edit these pages but I am actually now using [Nota][notalink] instead. It is by the same authors and I think that they are no longer working on Caret but focusing on Nota.  Nota has a workspace metaphor so I have access to all of the Markdown files that I have written for the blog much like you would in a code editing environment. 

**Blog updates**

Today I added tags to the site and build some pages to display them as well as edited the Hyde theme to display them on the blog posts. It was a much simpler process than I expected it to be. I think part of this is due to the templating system that is used in Hugo as well as the Go language that underpins it. I am getting more familiar with the style of the Hugo docs as well and have been reading through those.

I have also been reading, and working through, the wonderful Hugo tutorials at [Infinite Ink][infinite]. They are exceptionally well-written and very complete and the site has a treasure trove worth of Hugo information.  Do yourself a favour and check it out. 


[^1]: No shit

[medit]: https://redsweater.com/marsedit/ "Try it out, its a great app"
[notalink]: https://nota.md "A very nice editor"
[infinite]: https://www.ii.com "Infinite Ink"