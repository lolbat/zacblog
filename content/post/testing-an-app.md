---
title: "Testing an App"
date: 2021-10-06T10:33:51-06:00
draft: false
tags:
    - conquestofelysium
    - bootstrap
    - jquery
    - datatables
    - jsrender
    - json
---

What a crazy few days it has been. I have caught yet another cold which is a reminder of just how much a toxic germ factory a middle-school is as well as an example of why schools are such a horrible vector for covid infections.

I haven't done a lot in the last few days but on Friday I did post a [test version of a web application](https://coe5alamanc.netlify.app) that I have been working on. It is an interface for viewing data for the game [Conquest of Elysium 5](http://www.illwinter.com/coe5/index.html) by [Illwinter Game Design](http://www.illwinter.com). This is the project that I was working on when I had to [Shut it Down!][shutitdown] and start over.

I am using [JSRender](https://www.jsviews.com/#jsrender) to build all of the content viewed on the page as well as the menu items in the *Modding Tables* section. Everything is coming from a `.json` file and then read in and sent to one of several JSRender templates. There are distinct templates for the Modding Commands, Spells and Rituals table as well as a generic one for the basic HTML tables created for each of the Modding Tables. I think that I am officially never going to build a website without a templating system ever again. The benefits it brings vastly outweighs the minor issues in implementing one. 

![Buttons linking to tables](/zacblog/coeSite.jpg)

I grabbed [Datatables](https://www.datatables.net) to display the more complex tables. I am not sure if I will use it in the long run but I have used it before and it was simple to implement.  will see what people want from the application before determining that.  All of the currently available data for the game has been posted to a [Github repository](https://github.com/lolbat/Conquest-of-Elysium-5-data) in multiple formats along with the tools I built to create the specific `.json` files I needed. 

There are some ugly data definitions in the app that I tried to put into an external file and `import` but since the data was never used at the same context as the import and needed to be available in several locations I had to drop that plan. I am beginning to suspect that `import` and `export` are more suited for component-level development and not the SPAs that I am currently building. 

I may look into options for building generic components for my sites using something like React or a different library not stained by the moral and ethical weight of Facebook. 

In any case, this app is now out for some public testing and comment. I already have noticed that the chat bubble icons need to be bigger on mobile so that will be first on my list to change since I use the site primarily from my iPad. 
 
[shutitdown]:{{< ref "shut_it_down.md" >}}